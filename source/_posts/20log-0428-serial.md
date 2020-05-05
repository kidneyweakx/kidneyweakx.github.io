---
title: C# 用VID和PID自動連線serialport
tags:
  - 程式筆記
  - C#
date: '2020-04-28 13:30:00'
---

原本C#的serial port function[官方範例](https://docs.microsoft.com/zh-tw/dotnet/api/system.io.ports.serialport?view=dotnet-plat-ext-3.1)，是類似這樣的
``` C#
streamport = new SerialPort("COM3", bauadrate);
```
<!-- more -->
這種方法每次開啟都還要再去跟改port相當的麻煩，所以就找了別人針對windows寫的function，再返回靜態的port string給`SerialPort`，效果相當好。

``` C#
// 有錯誤可能是你沒有 using Microsoft.Win32;或其他lib
 public static List<string> ComPortNames(String VID, String PID)
    {
        // 讀取PID和VID
        String pattern = String.Format("^VID_{0}.PID_{1}", VID, PID);
        Regex _rx = new Regex(pattern, RegexOptions.IgnoreCase);
        List<string> comports = new List<string>();
        RegistryKey rk1 = Registry.LocalMachine;
        RegistryKey rk2 = rk1.OpenSubKey("SYSTEM\\CurrentControlSet\\Enum");
        foreach (String s3 in rk2.GetSubKeyNames())
        {
            RegistryKey rk3 = rk2.OpenSubKey(s3);
            foreach (String s in rk3.GetSubKeyNames())
            {
                if (_rx.Match(s).Success)
                {
                    RegistryKey rk4 = rk3.OpenSubKey(s);
                    foreach (String s2 in rk4.GetSubKeyNames())
                    {
                        RegistryKey rk5 = rk4.OpenSubKey(s2);
                        RegistryKey rk6 = rk5.OpenSubKey("Device Parameters");
                        comports.Add((string)rk6.GetValue("PortName"));
                        // 獲取port name，如有多個相同設備，加入comports array
                    }
                }
            }
        }
        return comports;
    }
```
完整內容可參照下方連結😁
[code來源](https://www.codeproject.com/Tips/349002/Select-a-USB-Serial-Device-via-its-VID-PID)
