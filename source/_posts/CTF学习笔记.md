---
title: CTF学习笔记
date: 2021-05-27 19:47:32
categories:	CTF
tags: CTF
description: 萌新的入坑记录
sticky:
keywords:
  - 参照表
  - 语法
cover:
copyright:
copyright_author:
copyright_author_href:
copyright_url:
copyright_info:
---
# web

## URL编码

### ASCII 编码参考手册

| 字符  | 来自 Windows-1252 | 来自 UTF-8 |
| :---- | :---------------- | :--------- |
| space | %20               | %20        |
| !     | %21               | %21        |
| "     | %22               | %22        |
| #     | %23               | %23        |
| $     | %24               | %24        |
| %     | %25               | %25        |
| &     | %26               | %26        |
| '     | %27               | %27        |
| (     | %28               | %28        |
| )     | %29               | %29        |
| *     | %2A               | %2A        |
| +     | %2B               | %2B        |
| ,     | %2C               | %2C        |
| -     | %2D               | %2D        |
| .     | %2E               | %2E        |
| /     | %2F               | %2F        |
| 0     | %30               | %30        |
| 1     | %31               | %31        |
| 2     | %32               | %32        |
| 3     | %33               | %33        |
| 4     | %34               | %34        |
| 5     | %35               | %35        |
| 6     | %36               | %36        |
| 7     | %37               | %37        |
| 8     | %38               | %38        |
| 9     | %39               | %39        |
| :     | %3A               | %3A        |
| ;     | %3B               | %3B        |
| <     | %3C               | %3C        |
| =     | %3D               | %3D        |
| >     | %3E               | %3E        |
| ?     | %3F               | %3F        |
| @     | %40               | %40        |
| A     | %41               | %41        |
| B     | %42               | %42        |
| C     | %43               | %43        |
| D     | %44               | %44        |
| E     | %45               | %45        |
| F     | %46               | %46        |
| G     | %47               | %47        |
| H     | %48               | %48        |
| I     | %49               | %49        |
| J     | %4A               | %4A        |
| K     | %4B               | %4B        |
| L     | %4C               | %4C        |
| M     | %4D               | %4D        |
| N     | %4E               | %4E        |
| O     | %4F               | %4F        |
| P     | %50               | %50        |
| Q     | %51               | %51        |
| R     | %52               | %52        |
| S     | %53               | %53        |
| T     | %54               | %54        |
| U     | %55               | %55        |
| V     | %56               | %56        |
| W     | %57               | %57        |
| X     | %58               | %58        |
| Y     | %59               | %59        |
| Z     | %5A               | %5A        |
| [     | %5B               | %5B        |
| \     | %5C               | %5C        |
| ]     | %5D               | %5D        |
| ^     | %5E               | %5E        |
| _     | %5F               | %5F        |
| `     | %60               | %60        |
| a     | %61               | %61        |
| b     | %62               | %62        |
| c     | %63               | %63        |
| d     | %64               | %64        |
| e     | %65               | %65        |
| f     | %66               | %66        |
| g     | %67               | %67        |
| h     | %68               | %68        |
| i     | %69               | %69        |
| j     | %6A               | %6A        |
| k     | %6B               | %6B        |
| l     | %6C               | %6C        |
| m     | %6D               | %6D        |
| n     | %6E               | %6E        |
| o     | %6F               | %6F        |
| p     | %70               | %70        |
| q     | %71               | %71        |
| r     | %72               | %72        |
| s     | %73               | %73        |
| t     | %74               | %74        |
| u     | %75               | %75        |
| v     | %76               | %76        |
| w     | %77               | %77        |
| x     | %78               | %78        |
| y     | %79               | %79        |
| z     | %7A               | %7A        |
| {     | %7B               | %7B        |
| \|    | %7C               | %7C        |
| }     | %7D               | %7D        |
| ~     | %7E               | %7E        |
|       | %7F               | %7F        |
| `     | %80               | %E2%82%AC  |
|       | %81               | %81        |
| ‚     | %82               | %E2%80%9A  |
| ƒ     | %83               | %C6%92     |
| „     | %84               | %E2%80%9E  |
| …     | %85               | %E2%80%A6  |
| †     | %86               | %E2%80%A0  |
| ‡     | %87               | %E2%80%A1  |
| ˆ     | %88               | %CB%86     |
| ‰     | %89               | %E2%80%B0  |
| Š     | %8A               | %C5%A0     |
| ‹     | %8B               | %E2%80%B9  |
| Œ     | %8C               | %C5%92     |
|       | %8D               | %C5%8D     |
| Ž     | %8E               | %C5%BD     |
|       | %8F               | %8F        |
|       | %90               | %C2%90     |
| ‘     | %91               | %E2%80%98  |
| ’     | %92               | %E2%80%99  |
| “     | %93               | %E2%80%9C  |
| ”     | %94               | %E2%80%9D  |
| •     | %95               | %E2%80%A2  |
| –     | %96               | %E2%80%93  |
| —     | %97               | %E2%80%94  |
| ˜     | %98               | %CB%9C     |
| ™     | %99               | %E2%84     |
| š     | %9A               | %C5%A1     |
| ›     | %9B               | %E2%80     |
| œ     | %9C               | %C5%93     |
|       | %9D               | %9D        |
| ž     | %9E               | %C5%BE     |
| Ÿ     | %9F               | %C5%B8     |
|       | %A0               | %C2%A0     |
| ¡     | %A1               | %C2%A1     |
| ¢     | %A2               | %C2%A2     |
| £     | %A3               | %C2%A3     |
| ¤     | %A4               | %C2%A4     |
| ¥     | %A5               | %C2%A5     |
| ¦     | %A6               | %C2%A6     |
| §     | %A7               | %C2%A7     |
| ¨     | %A8               | %C2%A8     |
| ©     | %A9               | %C2%A9     |
| ª     | %AA               | %C2%AA     |
| «     | %AB               | %C2%AB     |
| ¬     | %AC               | %C2%AC     |
| ­     | %AD               | %C2%AD     |
| ®     | %AE               | %C2%AE     |
| ¯     | %AF               | %C2%AF     |
| °     | %B0               | %C2%B0     |
| ±     | %B1               | %C2%B1     |
| ²     | %B2               | %C2%B2     |
| ³     | %B3               | %C2%B3     |
| ´     | %B4               | %C2%B4     |
| µ     | %B5               | %C2%B5     |
| ¶     | %B6               | %C2%B6     |
| ·     | %B7               | %C2%B7     |
| ¸     | %B8               | %C2%B8     |
| ¹     | %B9               | %C2%B9     |
| º     | %BA               | %C2%BA     |
| »     | %BB               | %C2%BB     |
| ¼     | %BC               | %C2%BC     |
| ½     | %BD               | %C2%BD     |
| ¾     | %BE               | %C2%BE     |
| ¿     | %BF               | %C2%BF     |
| À     | %C0               | %C3%80     |
| Á     | %C1               | %C3%81     |
| Â     | %C2               | %C3%82     |
| Ã     | %C3               | %C3%83     |
| Ä     | %C4               | %C3%84     |
| Å     | %C5               | %C3%85     |
| Æ     | %C6               | %C3%86     |
| Ç     | %C7               | %C3%87     |
| È     | %C8               | %C3%88     |
| É     | %C9               | %C3%89     |
| Ê     | %CA               | %C3%8A     |
| Ë     | %CB               | %C3%8B     |
| Ì     | %CC               | %C3%8C     |
| Í     | %CD               | %C3%8D     |
| Î     | %CE               | %C3%8E     |
| Ï     | %CF               | %C3%8F     |
| Ð     | %D0               | %C3%90     |
| Ñ     | %D1               | %C3%91     |
| Ò     | %D2               | %C3%92     |
| Ó     | %D3               | %C3%93     |
| Ô     | %D4               | %C3%94     |
| Õ     | %D5               | %C3%95     |
| Ö     | %D6               | %C3%96     |
| ×     | %D7               | %C3%97     |
| Ø     | %D8               | %C3%98     |
| Ù     | %D9               | %C3%99     |
| Ú     | %DA               | %C3%9A     |
| Û     | %DB               | %C3%9B     |
| Ü     | %DC               | %C3%9C     |
| Ý     | %DD               | %C3%9D     |
| Þ     | %DE               | %C3%9E     |
| ß     | %DF               | %C3%9F     |
| à     | %E0               | %C3%A0     |
| á     | %E1               | %C3%A1     |
| â     | %E2               | %C3%A2     |
| ã     | %E3               | %C3%A3     |
| ä     | %E4               | %C3%A4     |
| å     | %E5               | %C3%A5     |
| æ     | %E6               | %C3%A6     |
| ç     | %E7               | %C3%A7     |
| è     | %E8               | %C3%A8     |
| é     | %E9               | %C3%A9     |
| ê     | %EA               | %C3%AA     |
| ë     | %EB               | %C3%AB     |
| ì     | %EC               | %C3%AC     |
| í     | %ED               | %C3%AD     |
| î     | %EE               | %C3%AE     |
| ï     | %EF               | %C3%AF     |
| ð     | %F0               | %C3%B0     |
| ñ     | %F1               | %C3%B1     |
| ò     | %F2               | %C3%B2     |
| ó     | %F3               | %C3%B3     |
| ô     | %F4               | %C3%B4     |
| õ     | %F5               | %C3%B5     |
| ö     | %F6               | %C3%B6     |
| ÷     | %F7               | %C3%B7     |
| ø     | %F8               | %C3%B8     |
| ù     | %F9               | %C3%B9     |
| ú     | %FA               | %C3%BA     |
| û     | %FB               | %C3%BB     |
| ü     | %FC               | %C3%BC     |
| ý     | %FD               | %C3%BD     |
| þ     | %FE               | %C3%BE     |
| ÿ     | %FF               | %C3%BF     |

## SQL

| 语句            | 作用                 |
| --------------- | -------------------- |
| SELECT          | 从数据库中提取数据   |
| UPDATE          | 更新数据库中的数据   |
| DELETE          | 从数据库中删除数据   |
| INSERT INTO     | 向数据库中插入新数据 |
| CREATE DATABASE | 创建新数据库         |
| ALTER DATABASE  | 修改数据库           |
| CREATE TABLE    | 创建新表             |
| ALTER TABLE     | 变更（改变）数据库表 |
| DROP TABLE      | 删除表               |
| CREATE INDEX    | 创建索引（搜索键）   |
| DROP INDEX      | 删除索引             |

### SQL SELECT

> **SELECT 语句用于从数据库中选取数据**
>
> SELECT 语句用于从数据库中选取数据
>
> 结果被存储在一个结果表中，称为结果集

#### 语法

```sql
SELECT column_name,column_name FROM table_name;
```

> 从表中选取某两列

或

```sql
SELECT * FROM table_name;
```

> 从表中选取所有列

### SQL SELECT DISTINCT

> **SELECT DISTINCT 语句用于返回唯一不同的值**
>
> 在表中，一个列可能会包含多个重复值，有时您也许希望仅仅列出不同（distinct）的值
>
> DISTINCT 关键词用于返回唯一不同的值

#### 语法

```sql
SELECT DISTINCT column_name,column_name FROM table_name;
```



### SQL注入

#### 登录界面
> 登录界面必然会与数据库进行交互，所以是SQL注入的经典位置

常见登陆界面SQL语句`select * from admin where username = '用户输入的用户名' and password = '用户输入的密码'`
万能用户名:`' or 1=1 -- ` 	(`-- `后面有一个空格)
第一个`'`用于闭合SQL语句用户名的单引号，`1=1`永远为真，`-- `用于注释其后的密码语句，从而绕过登录验证 

# misc

## 文件格式

|                          **扩展名**                          | **文件头标识（HEX）**                                        | **文件描述**                                                 |
| :----------------------------------------------------------: | :----------------------------------------------------------- | :----------------------------------------------------------- |
|                             123                              | 00 00 1A 00 05 10 04                                         | Lotus 1-2-3 spreadsheet (v9) file                            |
|                        3gg; 3gp; 3g2                         | 00 00 00 nn 66 74 79 70 33 67 70                             | 3rd Generation Partnership Project 3GPP (nn=0x14)  and 3GPP2 (nn=0x20) multimedia files |
|                              7z                              | 37 7A BC AF 27 1C                                            | 7-ZIP compressed file                                        |
|                             aba                              | 00 01 42 41                                                  | Palm Address Book Archive file                               |
|                             abi                              | 41 4F 4C 49 4E 44 45 58                                      | AOL address book index file                                  |
|                           aby; idx                           | 41 4F 4C 44 42                                               | AOL database files: address book (ABY) and user  configuration data (MAIN.IDX) |
|                            accdb                             | 00 01 00 00 53 74 61 6E 64 61 72 64 20 41 43 45 20  44 42    | Microsoft Access 2007 file                                   |
|                             ACM                              | 4D 5A                                                        | MS audio compression manager driver                          |
|                             ADF                              | 44 4F 53                                                     | Amiga disk file                                              |
|                             adx                              | 03 00 00 00 41 50 50 52                                      | Lotus Approach ADX file                                      |
|                             AIFF                             | 46 4F 52 4D 00                                               | Audio Interchange File                                       |
|                             ain                              | 21 12                                                        | AIN Compressed Archive File                                  |
|                             ami                              | 5B 76 65 72 5D                                               | Lotus Ami Pro                                                |
|                             amr                              | 23 21 41 4D 52                                               | Adaptive Multi-Rate ACELP (Algebraic Code Excited  Linear Prediction) Codec, commonly audio format with GSM cell phones |
|                             ANI                              | 52 49 46 46                                                  |                                                              |
|                             API                              | 4D 5A 90 00 03 00 00 00                                      | Acrobat plug-in                                              |
|                             arc                              | 1A 0x                                                        | LH archive file, old version(where x = 0x2, 0x3,  0x4, 0x8 or 0x9 for types 1-5, respectively) |
|                             arc                              | 41 72 43 01                                                  | FreeArc compressed file                                      |
|                             arj                              | 60 EA                                                        | ARJ Compressed Archive                                       |
|                             ARJ                              | 60 EA 27                                                     |                                                              |
|                             ART                              | 4A 47 03 0E 00 00 00                                         | AOL ART file                                                 |
|                             ART                              | 4A 47 04 0E 00 00 00                                         | AOL ART file                                                 |
|                             asf                              | 30 26 B2 75 8E 66 CF 11                                      | Windows Media                                                |
|                        asf; wma; wmv                         | 30 26 B2 75 8E 66 CF 11 A6 D9 00 AA 00 62 CE 6C              | Microsoft Windows Media Audio/Video File(Advanced  Streaming Format) |
|                             asx                              | 3C                                                           | Advanced Stream redirector file                              |
|                              au                              | 2E 73 6E 64                                                  | SoundMachine Audio FileNeXT/Sun Microsystems μ-Law audio file |
|                             avi                              | 41 56 49 20                                                  | Audio Video Interleave (AVI)                                 |
|                              AX                              | 4D 5A                                                        | Library cache file                                           |
|                              AX                              | 4D 5A 90 00 03 00 00 00                                      | DirectShow filter                                            |
|                             bag                              | 41 4F 4C 20 46 65 65 64 62 61 67                             | AOL and AIM buddy list file                                  |
|                             BAS                              | 20 20 20                                                     |                                                              |
|                             bin                              | 42 4C 49 32 32 33 51                                         | Thomson Speedtouch series WLAN router firmware               |
|                             bmp                              | 42 4D                                                        | Windows Bitmap                                               |
|                             BMP                              | 42 4D 3E                                                     |                                                              |
|                           bz; bz2                            | 42 5A 68                                                     | BZIP Archive                                                 |
|                   BZ2; TAR.BZ2; TBZ2; TB2                    | 42 5A 68                                                     | bzip2 compressed archive                                     |
|                             CAB                              | 49 53 63                                                     |                                                              |
|                           CAB; HDR                           | 49 53 63 28                                                  | Install Shield v5.x or 6.x compressed file                   |
|                             CAB                              | 4D 53 43 46                                                  | Microsoft CAB File Format                                    |
|                             cat                              | 30                                                           | Microsoft security catalog file                              |
|                             CBD                              | 43 42 46 49 4C 45                                            | WordPerfect dictionary file (unconfirmed)                    |
|                             CCD                              | 5B 43 6C                                                     |                                                              |
|                             cdr                              | CDR                                                          | Corel Draw                                                   |
|                             CDR                              | 45 4C 49 54 45 20 43 6F 6D 6D 61 6E 64 65 72 20              | Elite Plus Commander saved game file                         |
|                           CDR, DVF                           | 4D 53 5F 56 4F 49 43 45                                      | Sony Compressed Voice File                                   |
|                           CHI; CHM                           | 49 54 53 46                                                  | Microsoft Compiled HTML Help File                            |
|                             CHM                              | 49 54 53                                                     |                                                              |
|                             CLB                              | 43 4D 58 31                                                  | Corel Binary metafile                                        |
|                             CLB                              | 43 4F 4D 2B                                                  | COM+ Catalog file                                            |
|                             cnt                              | 3A 42 61 73 65                                               |                                                              |
|            COM, DLL, DRV, EXE, PIF, QTS, QTX, SYS            | 4D 5A                                                        | Windows/DOS executable file                                  |
|                             COM                              | 4D 5A EE                                                     |                                                              |
|                             COM                              | E9 3B 03                                                     |                                                              |
|                             CPE                              | 46 41 58 43 4F 56 45 52 2D 56 45 52                          | Microsoft Fax Cover Sheet                                    |
|                             CPL                              | 4D 5A                                                        | Control panel application                                    |
|                             CPT                              | 43 50 54 37 46 49 4C 45                                      | Corel Photopaint file                                        |
|                             CPT                              | 43 50 54 46 49 4C 45                                         | Corel Photopaint file                                        |
|                             CPX                              | 5B 57 69                                                     |                                                              |
|                          cru; crush                          | 43 52 55 53 48                                               | CRUSH Archive File                                           |
|                             CRU                              | 43 52 55 53 48 20 76                                         | Crush compressed archive                                     |
|                             CRW                              | 49 49 1A 00 00 00 48 45 41 50 43 43 44 52 02 00              | Canon digital camera RAW file                                |
|                             CTF                              | 43 61 74 61 6C 6F 67 20 33 2E 30 30 00                       | WhereIsIt Catalog file                                       |
|                             CUR                              | 00 00 02 00 01 00 20 20                                      | Windows cursor file                                          |
|                             dat                              | 03                                                           | MapInfo Native Data Format                                   |
|                             dat                              | 1A 52 54 53 20 43 4F 4D 50 52 45 53 53 45 44 20 49  4D 41 47 45 20 56 31 2E 30 1A | Runtime Software disk image                                  |
|                             dat                              | 41 56 47 36 5F 49 6E 74 65 67 72 69 74 79 5F 44 61  74 61 62 61 73 65 | AVG6 Integrity database file                                 |
|                             DAT                              | 43 52 45 47                                                  | Windows 9x registry hive                                     |
|                             DAT                              | 43 6C 69 65 6E 74 20 55 72 6C 43 61 63 68 65 20 4D  4D 46 20 56 65 72 20 | IE History DAT file                                          |
|                             DAT                              | 45 52 46 53 53 41 56 45 44 41 54 41 46 49 4C 45              | Kroll EasyRecovery Saved Recovery State file                 |
|                             DAT                              | 49 6E 6E 6F 20 53 65 74 75 70 20 55 6E 69 6E 73 74  61 6C 6C 20 4C 6F 67 20 28 62 29 | Inno Setup Uninstall Log file                                |
|                              db                              | 00 06 15 61 00 00 00 02 00 00 04 D2 00 00 10 00              | Netscape Navigator (v4) database file                        |
|                              DB                              | 44 42 46 48                                                  | Palm Zire photo database                                     |
|                              db                              | 08                                                           | dBASE IV or dBFast configuration file                        |
|                             db3                              | 03                                                           | dBASE III file                                               |
|                             db4                              | 04                                                           | dBASE IV data file                                           |
|                             dba                              | 00 01 42 44                                                  | Palm DateBook Archive file                                   |
|                             dbx                              | CF AD 12 FE                                                  |                                                              |
|                             dbx                              | CF AD 12 FE C5 FD 74 6F                                      | Outlook Express                                              |
|                             dci                              | 3C 21 64 6F 63 74 79 70                                      | AOL HTML mail file                                           |
|                             dcx                              | 3A DE 68 B1                                                  | DCX Graphic File                                             |
|                             DDB                              | 00 01 00                                                     |                                                              |
|                             dib                              | 42 4D                                                        | device-independent bitmap image                              |
|                             DLL                              | 4D 5A 90                                                     |                                                              |
|                             DMP                              | 4D 44 4D 50 93 A7                                            | Windows minidump file                                        |
|                             DMS                              | 44 4D 53 21                                                  | Amiga DiskMasher compressed archive                          |
|                             doc                              | 0D 44 4F 43                                                  | DeskMate Document file                                       |
|                             doc                              | 12 34 56 78 90 FF                                            | MS Word 6.0                                                  |
|                             doc                              | 31 BE 00 00 00 AB 00 00                                      | MS Word for DOS 6.0                                          |
|                             doc                              | 7F FE 34 0A                                                  | MS Word                                                      |
|          dot; ppt; xla; ppa; pps; pot; msi; sdw; db          | D0 CF 11 E0                                                  | MS Office/OLE2                                               |
| doc; dot; xls; xlt; xla; ppt; apr ;ppa; pps; pot; msi;  sdw; db | D0 CF 11 E0 A1 B1 1A E1                                      | MS Compound Document v1 or Lotus Approach APR file           |
|                             DPL                              | 4D 5A 50                                                     |                                                              |
|                             DRV                              | 4D 5A 16                                                     |                                                              |
|                             drw                              | 07                                                           | A common signature and file extension for many  drawing programs. |
|                             drw                              | 01 FF 02 04 03 02                                            | Micrografx vector graphic file                               |
|                             ds4                              | 4D 47 58 20 69 74 70 64                                      | Micrografix Designer 4                                       |
|                             DSN                              | 4D 56                                                        | CD Stomper Pro label file                                    |
|                             dsp                              | 23 20 4D 69 63 72 6F 73 6F 66 74 20 44 65 76 6 56C  6F 70 65 72 20 53 74 75 64 69 6F | Microsoft Developer Studio project file                      |
|                             dss                              | 02 64 73 73                                                  | Digital Speech Standard (Olympus, Grundig, &  Phillips)      |
|                             dtd                              | 07 64 74 32 64 64 74 64                                      | DesignTools 2D Design file                                   |
|                             dtd                              | 3C 21 45 4E 54 49 54 59                                      | XML DTD                                                      |
|                             DVR                              | 44 56 44                                                     | DVR-Studio stream file                                       |
|                             dwg                              | 41 43 31                                                     |                                                              |
|                             dwg                              | 41 43 31 30                                                  | Generic AutoCAD drawingNOTES on AutoCAD file headers: The 0x41-43-31-30  (AC10) is a generic header, occupying the first four bytes in the file. The  next two bytes give further indication about the version or subtype:0x30-32 (02) — AutoCAD R2.50x30-33 (03) — AutoCAD R2.60x30-34 (04) — AutoCAD R90x30-36 (06) — AutoCAD R100x30-39 (09) — AutoCAD R11/R120x31-30 (10) — AutoCAD R13 (subtype 10)0x31-31 (11) — AutoCAD R13 (subtype 11)0x31-32 (12) — AutoCAD R13 (subtype 12)0x31-33 (13) — AutoCAD R14 (subtype 13)0x31-34 (14) — AutoCAD R14 (subtype 14)0x31-35 (15) — AutoCAD R20000x31-38 (18) — AutoCAD R20040x32-31 (21) — AutoCAD R2007 |
|                  Enn (where nn are numbers)                  | 45 56 46                                                     | EnCase evidence file                                         |
|                             ECO                              | 2A 50 52                                                     |                                                              |
|                             elf                              | 7F 45 4C 46 01 01 01 00                                      | ELF Executable                                               |
|                             emf                              | 01 00 00 00 58 00 00 00                                      | Extended (Enhanced) Windows Metafile Format, printer  spool file |
|                             eml                              | 44 65 6C 69 76 65 72 79 2D 64 61 74 65 3A                    | Email                                                        |
|                             EML                              | 46 72 6F 6D 20 20 20                                         | A commmon file extension for e-mail files.  Signatures shown here are for Netscape, Eudora, and a generic signature,  respectively. EML is also used by Outlook Express and QuickMail. |
|                             EML                              | 46 72 6F 6D 20 3F 3F 3F                                      | A commmon file extension for e-mail files.  Signatures shown here are for Netscape, Eudora, and a generic signature,  respectively. EML is also used by Outlook Express and QuickMail. |
|                             EML                              | 46 72 6F 6D 3A 20                                            | A commmon file extension for e-mail files.  Signatures shown here are for Netscape, Eudora, and a generic signature,  respectively. EML is also used by Outlook Express and QuickMail. |
|                             EML                              | 52 65 63                                                     |                                                              |
|                             enc                              | 00 5C 41 B1 FF                                               | Mujahideen Secrets 2 encrypted file                          |
|                             enl                              | [32 byte offset] 40 40 40 20 00 00 40 40 40 40               | EndNote Library File                                         |
|                             eps                              | 25 21 50 53                                                  | Adobe EPS File                                               |
|                             eps                              | 25 21 50 53 2D 41 64 6F 62 65                                | Postscript                                                   |
|                             eps                              | 25 21 50 53 2D 41 64 6F 62 65 2D 33 2E 30 20 45 50  53 46 2D 33 20 30 | Adobe encapsulated PostScript file (If this  signature is not at the immediate beginning of the file, it will occur early in  the file, commonly at byte offset 30) |
|                             EPS                              | C5 D0 D3                                                     |                                                              |
|                             eth                              | 1A 35 01 00                                                  | GN Nettest WinPharoah capture file                           |
|                             evt                              | 30 00 00 00 4C 66 4C 65                                      | Windows Event Viewer file                                    |
|                             evt                              | 03 00 00 00 C4 66 C4 56                                      |                                                              |
|                             EVTX                             | 45 6C 66 46 69 6C 65 00                                      | Windows Vista event log file                                 |
|              exe; dll; drv; vxd; sys; ocx; vbx               | 4D 5A                                                        | Win32 Executable                                             |
|              exe; dll; drv; vxd; sys; ocx; vbx               | 4D 5A                                                        | Win16 Executable                                             |
| exe; com; 386; ax; acm; sys; dll; drv; flt; fon; ocx;  scr; lrc; vxd; cpl; x32 | 4D 5A                                                        | Executable File                                              |
|                 EXE, DLL, OCX, OLB, IMM, IME                 | 4D 5A 90                                                     |                                                              |
|                             fli                              | 00 11 AF                                                     | FLIC Animation file                                          |
|                             flt                              | 00 01 01                                                     | OpenFlight 3D file                                           |
|                             FLT                              | 4D 5A 90 00 03 00 00 00                                      | Audition graphic filter file (Adobe)                         |
|                             FLV                              | 46 4C 56 01                                                  | Flash video file                                             |
|                              fm                              | 3C 4D 61 6B 65 72 46 69 6C 65 20                             | Adobe FrameMaker file                                        |
|                             fm3                              | 00 00 1A 00 07 80 01 00                                      | Lotus 123 v3 FMT file                                        |
|                             fmt                              | 20 00 68 00 20 0                                             | Lotus 123 v4 FMT file                                        |
|                             FNT                              | 43 48 41                                                     |                                                              |
|                             FON                              | 4D 5A                                                        | Font file                                                    |
|                             GBC                              | 87 F5 3E                                                     |                                                              |
|                             gid                              | 3F 5F 03 00                                                  | Windows Help Index File                                      |
|                             GID                              | 4C 4E 02 00                                                  | Windows Help index file                                      |
|                             GIF                              | 47 49 46 38                                                  |                                                              |
|                             gif                              | 47 49 46 38 37 61                                            | Graphics interchange format file (GIF 87A)                   |
|                             gif                              | 47 49 46 38 39 61                                            | Graphics interchange format file (GIF89A)                    |
|                             GTD                              | 7B 50 72                                                     |                                                              |
|                             GX2                              | 47 58 32                                                     | Show Partner graphics file (not confirmed)                   |
|                         gz; tar; tgz                         | 1F 8B                                                        | Gzip Archive File                                            |
|                           gz; tgz                            | 1F 8B 08                                                     | GZ Compressed File                                           |
|                             hap                              | 91 33 48 46                                                  | HAP Archive File                                             |
|                             HDMP                             | 4D 44 4D 50 93 A7                                            | Windows heap dump file                                       |
|                             hdr                              | 23 3F 52 41 44 49 41 4E 43 45 0A                             | adiance High Dynamic Range image file                        |
|                             HLP                              | 3F 5F 03                                                     |                                                              |
|                             hlp                              | 3F 5F 03 00                                                  | Windows Help file                                            |
|                             HLP                              | 4C 4E 02 00                                                  | Windows Help file                                            |
|                             hlp                              | [7 byte offset] 00 00 FF FF FF FF                            | Windows Help file                                            |
|                             hqx                              | 28 54 68 69 73 20 66 69 6C 65                                | Macintosh BinHex 4 Compressed Archive                        |
|                             hqx                              | 28 54 68 69 73 20 66 69 6C 65 20 6D 75 73 74 20 62  65 20 63 6F 6E 76 65 72 74 65 64 20 77 69 74 68 20 42 69 6E 48 65 78 20 | Macintosh BinHex 4 Compressed Archive                        |
|                             HTM                              | 3C 21 44                                                     |                                                              |
|                          htm; html                           | 3C 21 44 4F 43 54                                            | HyperText Markup Language 3                                  |
|                          htm; html                           | 3C 48 54 4D 4C 3E                                            | HyperText Markup Language 2                                  |
|                          htm; html                           | 3C 68 74 6D 6C 3E                                            | HyperText Markup Language 1                                  |
|                             html                             | 68 74 6D 6C 3E                                               | HTML                                                         |
|                             ico                              | 00 00 01 00 00                                               | Icon File                                                    |
|                             ico                              | 00 00 01 00 01 00 20 20                                      | Icon File                                                    |
|                             IFF                              | 46 4F 52 4D                                                  |                                                              |
|                             IFO                              | 44 56 44                                                     | DVD info file                                                |
|                             IME                              | 4D 5A 90                                                     |                                                              |
|                             img                              | 00 01 00 08 00 01 00 01 01                                   | Ventura Publisher/GEM VDI Image Format Bitmap file           |
|                             IMG                              | 00 FF FF                                                     |                                                              |
|                             IMM                              | 4D 5A 90                                                     |                                                              |
|                             ind                              | 41 4F 4C 49 44 58                                            | AOL client preferences/settings file (MAIN.IND)              |
|                             ISO                              | 43 44 30 30 31                                               | ISO-9660 CD Disc Image (This signature usually  occurs at byte 8001, 8801, or 9001.) |
|                             ivr                              | 2E 52 45 43                                                  | RealPlayer video file (V11 and later)                        |
|                             JAR                              | 4A 41 52 43 53 00                                            | JARCS compressed archive                                     |
|                             jar                              | 5F 27 A8 89                                                  | JAR Archive File                                             |
|                          jpg; jpeg                           | FF D8 FF                                                     |                                                              |
|                        jpg; jpe; jpeg                        | FF D8 FF E0 00                                               | JPG Graphic File                                             |
|                        jpg; jpe; jpeg                        | FF D8 FF FE 00                                               | JPG Graphic File                                             |
|                             KGB                              | 4B 47 42 5F 61 72 63 68 20 2D                                | KGB archive                                                  |
|                             KOZ                              | 49 44 33 03 00 00 00                                         | Sprint Music Store audio file (for mobile devices)           |
|                             LDB                              | 42 49 4C                                                     |                                                              |
|                             lha                              | 2D 6C 68 35 2D                                               | LHA Compressed                                               |
|                           lha; lzh                           | [2 byte offset] 2D 6C 68                                     | Compressed archive file                                      |
|                             LHP                              | 3F 5F 03                                                     |                                                              |
|                             lhp                              | 3F 5F 03 00                                                  | Windows Help File                                            |
|                             lib                              | 21 3C 61 72 63 68 3E 0A                                      | Unix archiver (ar) files and Microsoft Program  Library Common Object File Format (COFF) |
|                             LIB                              | 2A 24 20                                                     |                                                              |
|                             LIT                              | 49 54 4F 4C 49 54 4C 53                                      | Microsoft Reader eBook file                                  |
|                             LNK                              | 4C 00 00                                                     |                                                              |
|                             lnk                              | 4C 00 00 00                                                  | Windows Shortcut (Link File)                                 |
|                             lnk                              | 4C 00 00 00 01 14 02                                         | Windows Link File                                            |
|                             LNK                              | 4C 00 00 00 01 14 02 00                                      | Windows shortcut file                                        |
|                             log                              | 2A 2A 2A 20 20 49 6E 73 74 61 6C 6C 61 74 69 6F 6E  20 53 74 61 72 74 65 64 20 | Symantec Wise Installer log file                             |
|                             lzh                              | lh                                                           | Lz compression file                                          |
|                             lwp                              | 57 6F 72 64 50 72 6F                                         | Lotus WordPro v9                                             |
|                             m3u                              | 23 45 58                                                     |                                                              |
|                             m4a                              | 00 00 00 20 66 74 79 70 4D 34 41 20 00 00 00 00              | Apple Lossless Audio Codec file                              |
|                           m4a; m4v                           | 00 00 00 20 66 74 79 70 4D 34 41 20 00 00 00 00              | QuickTime M4A/M4V file                                       |
|                           manifest                           | 3C 3F 78 6D 6C 20 76 65 72 73 69 6F 6E 3D                    | Windows Visual Stylesheet XML file                           |
|                             MAR                              | 4D 41 52 31 00                                               | Mozilla archive                                              |
|                             MAR                              | 4D 41 52 43                                                  | Microsoft/MSN MARC archive                                   |
|                             MAR                              | 4D 41 72 30 00                                               | MAr compressed archive                                       |
|                             max                              | D0 CF 11                                                     |                                                              |
|                             mdb                              | 00 01 00 00 53 74 61 6E 64 61 72 64 20 4A 65 74 20  44 42    | Microsoft Access file                                        |
|                      mdb; mda; mde; mdt                      | 53 74 61 6E 64 61 72 64 20 4A                                | MS Access                                                    |
|                             MDF                              | 00 FF FF                                                     |                                                              |
|                             mdf                              | 00 FF FF FF FF FF FF FF FF FF FF 00 00 02 00 01              | Alcohol 120% CD image                                        |
|                             mdf                              | 01 0F 00 00                                                  | Microsoft SQL Server 2000 database                           |
|                             MDI                              | 45 50                                                        | Microsoft Document Imaging file                              |
|                             MDS                              | 4D 45 44                                                     |                                                              |
|                          MID; MIDI                           | 4D 54 68 64                                                  | Musical Instrument Digital Interface (MIDI) sound  file      |
|                             mkv                              | 1A 45 DF A3 93 42 82 88 6D 61 74 72 6F 73 6B 61              | Matroska stream file                                         |
|                             MLS                              | 4D 49 4C 45 53                                               | Milestones v1.0 project management and scheduling  software (Also see "MV2C" and "MV214" signatures) |
|                             MLS                              | 4D 4C 53 57                                                  | Skype localization data file                                 |
|                             MLS                              | 4D 56 32 31 34                                               | Milestones v2.1b project management and scheduling  software (Also see "MILES" and "MV2C" signatures) |
|                             MLS                              | 4D 56 32 43                                                  | Milestones v2.1a project management and scheduling  software (Also see "MILES" and "MV214" signatures) |
|                             MMF                              | 4D 4D 4D 44 00 00                                            | Yamaha Corp. Synthetic music Mobile Application  Format (SMAF) for multimedia files that can be played on hand-held devices. |
|                             mny                              | 00 01 00 00 4D 53 49 53 41 4D 20 44 61 74 61 62 61  73 65    | Microsoft Money file                                         |
|                             MOV                              | 00 00 0F                                                     |                                                              |
|                             MOV                              | 00 00 77                                                     |                                                              |
|                             mov                              | 6D 6F 6F 76                                                  | Quicktime                                                    |
|                             mov                              | 6D 64 61 74                                                  | QuickTime Movie                                              |
|                              mp                              | 0C ED                                                        | Monochrome Picture TIFF bitmap file (unconfirmed)            |
|                             MP3                              | 49 44 33                                                     | MPEG-1 Audio Layer 3 (MP3) audio file                        |
|                             MP3                              | FF FB 50                                                     |                                                              |
|                             mp4                              | 00 00 00 18 66 74 79 70 33 67 70 35                          | MPEG-4 video files                                           |
|                             MPA                              | 00 00 01                                                     |                                                              |
|                          mpg; mpeg                           | 00 00 01 B3                                                  | MPEG Movie                                                   |
|                             mpg                              | 00 00 01 BA                                                  | MPEG                                                         |
|                             MSC                              | 3C 3F 78                                                     |                                                              |
|                             msc                              | 3C 3F 78 6D 6C 20 76 65 72 73 69 6F 6E 3D 22 31 2E  30 22 3F 3E 0D 0A 3C 4D 4D 43 5F 43 6F 6E 73 6F 6C 65 46 69 6C 65 20 43 6F 6E  73 6F 6C 65 56 65 72 73 69 6F 6E 3D 22 | Microsoft Management Console Snap-in Control file            |
|                             msi                              | 23 20                                                        | Cerius2 file                                                 |
|                             MSV                              | 4D 53 5F 56 4F 49 43 45                                      | Sony Memory Stick Compressed Voice file                      |
|                             NES                              | 4E 45 53                                                     |                                                              |
|                             NLS                              | C2 20 20                                                     |                                                              |
|                             nri                              | 0E 4E 65 72 6F 49 53 4F                                      | Nero CD Compilation                                          |
|                             ntf                              | 1A 00 00                                                     | Lotus Notes database template                                |
|                           nsf; ntf                           | 1A 00 00 03 00 00                                            | Lotus Notes Database/Template                                |
|                             nsf                              | 1A 00 00 03 00 00 11 00                                      | Notes Database                                               |
|                             nsf                              | 1A 00 00 04 00 00                                            | Lotus Notes database                                         |
|                             ntf                              | 30 31 4F 52 44 4E 41 4E 43 45 20 53 55 52 56 45 59  20 20 20 20 20 20 20 | National Transfer Format Map File                            |
|                             obj                              | 4C 01                                                        | Microsoft Common Object File Format (COFF)  relocatable object code file for an Intel 386 or later/compatible processors |
|                             OCX                              | 4D 5A                                                        | ActiveX or OLE Custom Control                                |
|                             OCX                              | 4D 5A 90                                                     |                                                              |
|                             OLB                              | 4D 5A                                                        | OLE object library                                           |
|                             OLB                              | 4D 5A 90                                                     |                                                              |
|                           org; pfc                           | 41 4F 4C 56 4D 31 30 30                                      | AOL personal file cabinet (PFC) file                         |
|                             pak                              | 1A 0B                                                        | Compressed archive file                                      |
|                             PAT                              | 47 46 31 50 41 54 43 48                                      | Advanced Gravis Ultrasound patch file                        |
|                             PAT                              | 47 50 41 54                                                  | GIMP (GNU Image Manipulation Program) pattern file           |
|                             PBK                              | 5B 41 44                                                     |                                                              |
|                             PCB                              | 17 A1 50                                                     |                                                              |
|                             PCS                              | 0A 05 01                                                     |                                                              |
|                             pcx                              | 0A nn 01 01                                                  | ZSOFT Paintbrush file(where nn = 0x02, 0x03, or  0x05)       |
|                             pcx                              | 0A 05 01 08                                                  | PC Paintbrush(often associated with Quake Engine  games)     |
|                             pdb                              | [11 byte offset] 00 00 00 00 00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00 00 00 00 00 | Palmpilot Database/Document File                             |
|                             PDF                              | 25 50 44                                                     |                                                              |
|                           pdf; fdf                           | 25 50 44 46                                                  | Adobe Portable Document Format and Forms Document  file      |
|                             pdf                              | 25 50 44 46 2D 31 2E                                         | Adobe Acrobat                                                |
|                             PDG                              | 48 48 02                                                     |                                                              |
|                              pf                              | 11 00 00 00 53 43 43 41                                      | Windows prefetch file                                        |
|                             pic                              | 01 00 00 00 01                                               | Unknown type picture file                                    |
|                             PJT                              | 00 00 07                                                     |                                                              |
|                             PLL                              | 24 53 6F                                                     |                                                              |
|                             PNG                              | 89 50 4E                                                     |                                                              |
|                             PNG                              | 89 50 4E 47                                                  |                                                              |
|                             png                              | 89 50 4E 47 0D 0A                                            | PNG Image File                                               |
|                             png                              | 89 50 4E 47 0D 0A 1A 0A                                      | PNG Image File                                               |
|                             PPC                              | 52 65 63                                                     |                                                              |
|                             PPT                              | D0 CF 11                                                     |                                                              |
|                             ppt                              | [512 byte offset] 00 6E 1E F0                                | PowerPoint presentation subheader (MS Office)                |
|                             ppt                              | [512 byte offset] 0F 00 E8 03                                | PowerPoint presentation subheader (MS Office)                |
|                             PPZ                              | 4D 53 43 46                                                  | Powerpoint Packaged Presentation                             |
|                             prc                              | 42 4F 4F 4B 4D 4F 42 49                                      | Palmpilot resource file                                      |
|                             PRG                              | 23 44 45                                                     |                                                              |
|                              ps                              | 25 21 50 53 2D 41 64 6F 62 65                                | Postscript                                                   |
|                             PSD                              | 38 42 50                                                     |                                                              |
|                             psd                              | 38 42 50 53                                                  | Adobe Photoshop image file                                   |
|                             psp                              | 7E 42 4B 00                                                  | PaintShop Pro Image File                                     |
|                             pst                              | 21 42 44 4E                                                  | Microsoft Outlook Personal Folder file                       |
|                             pwl                              | E3 82 85 96                                                  | Windows Password                                             |
|                             qbb                              | 45 86 00 00 06 00                                            | Intuit QuickBooks Backup file                                |
|                             qdf                              | AC 9E BD 8F                                                  | Quicken                                                      |
|                             qph                              | 03 00 00 00                                                  | Quicken price history file                                   |
|                              qt                              | 6D 64 61 74                                                  | Quicktime Movie File                                         |
|                             qxd                              | 00 00 49 49 58 50 52                                         | Quark Express document (Intel & Motorola,  respectively)     |
|                             qxd                              | 00 00 4D 4D 58 50 52                                         |                                                              |
|                              ra                              | 2E 52 4D 46 00 00 00 12 00                                   | Real Audio file                                              |
|                           ra; ram                            | 2E 72 61 FD                                                  | Real Audio File                                              |
|                              ra                              | 2E 72 61 FD 00                                               | RealAudio streaming media file                               |
|                             RAR                              | 52 61 72                                                     |                                                              |
|                             rar                              | 52 61 72 21                                                  | RAR Archive File                                             |
|                             RAW                              | 06 05 00                                                     |                                                              |
|                             reg                              | 52 45 47 45 44 49 54 34                                      |                                                              |
|                             rgb                              | 01 DA 01 01 00 03                                            | Silicon Graphics RGB Bitmap                                  |
|                              RM                              | 2E 52 4D                                                     |                                                              |
|                           rm; rmvb                           | 2E 52 4D 46                                                  | Real Media streaming media file                              |
|                             rpm                              | ED AB EE DB                                                  | RPM Archive File                                             |
|                             RTD                              | 43 23 2B 44 A4 43 4D A5 48 64 72                             | RagTime document file                                        |
|                             RTF                              | 7B 5C 72                                                     |                                                              |
|                             rtf                              | 7B 5C 72 74 66                                               | Rich Text Format File                                        |
|                             sav                              | 24 46 4C 32 40 28 23 29 20 53 50 53 53 20 44 41 54  41 20 46 49 4C 45 | SPSS Data file                                               |
|                             SBV                              | 46 45 44 46                                                  | (Unknown file type)                                          |
|                             SCH                              | 2A 76 65                                                     |                                                              |
|                             scm                              | 80 53 43                                                     |                                                              |
|                             SH3                              | 48 48 47 42 31                                               | Harvard Graphics presentation file                           |
|                             SHD                              | 4B 49 00 00                                                  | Windows 9x printer spool file                                |
|                             sit                              | 53 49 54 21                                                  | Stuffit v1 Archive File                                      |
|                             sit                              | 53 74 75 66 66 49 74                                         | Stuffit v5 Archive File                                      |
|                             sle                              | 3A 56 45 52 53 49 4F 4E                                      | Surfplan kite project file                                   |
|                             sle                              | 41 43 76                                                     | teganos Security Suite virtual secure drive                  |
|                        sly; srt; slt                         | 53 52 01 00                                                  | Sage sly.or.srt.or.slt                                       |
|                             SMD                              | 00 FF FF                                                     |                                                              |
|                             snm                              | 00 1E 84 90 00 00 00 00                                      | Netscape Communicator (v4) mail folder                       |
|                             SNP                              | 4D 53 43 46                                                  | Microsoft Access Snapshot Viewer file                        |
|                             sol                              | 00 BF                                                        | Adobe Flash shared object file (e.g., Flash cookies)         |
|                             spl                              | 00 00 01 00                                                  | Windows NT/2000/XP printer spool file                        |
|                             SCR                              | 4D 5A                                                        | Screen saver                                                 |
|                             SUB                              | FF FF FF                                                     |                                                              |
|                             SWF                              | 43 57 53                                                     | Shockwave Flash file (v5+)                                   |
|                             SWF                              | 46 57 53                                                     | Macromedia Shockwave Flash player file                       |
|                             sxc                              | calc                                                         | OpenOffice Calc                                              |
|                             sxd                              | draw                                                         | OpenOffice Draw                                              |
|                             sxi                              | impress                                                      | OpenOffice Impress                                           |
|                             sxm                              | math                                                         | OpenOffice Math                                              |
|                             sxw                              | writer                                                       | OpenOffice Writer                                            |
|                             syw                              | 41 4D 59 4F                                                  | Harvard Graphics symbol graphic                              |
|                             TAG                              | 00 00 02                                                     |                                                              |
|                          tar; cpio                           | 30 37 30 37 30 37                                            | CPIO Archive File                                            |
|                            tar.z                             | 1F 9D 90                                                     | Compressed tape archive file                                 |
|                             tga                              | 00 00 10 00 00                                               | RLE压缩的前5字节                                             |
|                             TGA                              | 00 00 02                                                     |                                                              |
|                             tga                              | 00 00 02 00 00                                               | 未压缩的前5字节                                              |
|                          TIF; TIFF                           | 49 20 49                                                     | Tagged Image File Format file                                |
|                          tif; tiff                           | 49 49 2A                                                     | TIFF (Intel)                                                 |
|                          tif; tiff                           | 49 49 2A 00                                                  | Tagged Image File Format file (little endian, i.e.,  LSB first in the byte; Intel) |
|                          TIF; TIFF                           | 4D 4D 00 2A                                                  | Tagged Image File Format file (big endian, i.e., LSB  last in the byte; Motorola) |
|                          tif; tiff                           | 4D 4D 2A                                                     | TIFF (Motorola)                                              |
|                          TIF; TIFF                           | 4D 4D 00 2B                                                  | BigTIFF files; Tagged Image File Format files  4  GB         |
|                             TLB                              | 4D 53 46 54 02 00 01 00                                      | OLE, SPSS, or Visual C++ type library file                   |
|                             tr1                              | 01 10                                                        | Novell LANalyzer capture file                                |
|                             TST                              | 00 01 00                                                     |                                                              |
|                             TTF                              | 00 01 00                                                     |                                                              |
|                             ufa                              | 55 46 41                                                     | UFA Archive File                                             |
|                             VBX                              | 4D 5A                                                        | VisualBASIC application                                      |
|                             VCD                              | 45 4E 54 52 59 56 43 44 02 00 00 01 02 00 18 58              | VideoVCD (GNU VCDImager) file                                |
|                             vcf                              | 42 45 47 49 4E 3A 56 43 41 52 44 0D 0A                       | vCard file                                                   |
|                             vob                              | 00 00 01 BA                                                  | DVD Video Movie File (video/dvd, video/mpeg)                 |
|                           VXD, 386                           | 4D 5A                                                        | Windows virtual device drivers                               |
|                             WAV                              | 52 49 46                                                     |                                                              |
|                             wav                              | 57 41 56 45                                                  | Wave                                                         |
|                             wav                              | 57 41 56 45 66 6D 74                                         | Wave Files                                                   |
|                             wb2                              | 00 00 02 00                                                  | QuattroPro for Windows Spreadsheet file                      |
|                             wb3                              | [24 byte offset] 3E 00 03 00 FE FF 09 00 06                  | Quatro Pro for Windows 7.0 Notebook file                     |
|                           wk1; wks                           | 20 00 60 40 60                                               | Lotus 123 v1 Worksheet                                       |
|                             wk1                              | 00 00 02 00 06 04 06 00 08 00 00 00 00 00                    | Lotus 1-2-3 spreadsheet (v1) file                            |
|                             wk3                              | 00 00 1A 00 00 10 04 00                                      | Lotus 123 spreadsheet (v3) file                              |
|                           wk4; wk5                           | 00 00 1A 00 02 10 04 00                                      | Lotus 1-2-3 spreadsheet (v4, v5) file                        |
|                             wks                              | 0E 57 4B 53                                                  | DeskMate Worksheet                                           |
|                             WMA                              | 30 26 B2                                                     |                                                              |
|                             wmf                              | 01 00 09 00                                                  | Graphics Metafile                                            |
|                             wmf                              | 01 00 09 00 00 03                                            | Windows Metadata file (Win 3.x format)                       |
|                             wmf                              | 02 00 09 00                                                  | Graphics Metafile                                            |
|                             wmf                              | D7 CD C6 9A                                                  | Windows Meta File                                            |
|                             WMV                              | 30 26 B2                                                     |                                                              |
|                              wp                              | FF 57 50 43                                                  | WordPerfect v5 or v6                                         |
|                             wpd                              | FF 57 50 43                                                  | WordPerfect                                                  |
|                             wpg                              | FF 57 50 47                                                  | WordPerfect Graphics                                         |
|                             wri                              | 31 BE                                                        | Microsoft Write file                                         |
|                             WRI                              | 31 BE 00                                                     |                                                              |
|                             wri                              | 32 BE                                                        | Microsoft Write file                                         |
|                              ws                              | 1D 7D                                                        | WordStar Version 5.0/6.0 document                            |
|                             XBE                              | 58 42 45                                                     |                                                              |
|                             xdr                              | 3C                                                           | BizTalk XML-Data Reduced Schema file                         |
|                             xls                              | 09 02 06 00 00 00 10 00 B9 04 5C 00                          | MS Excel v2                                                  |
|                             xls                              | 09 04 06 00 00 00 10 00 F6 05 5C 00                          | MS Excel v4                                                  |
|                             XLS                              | D0 CF 11                                                     |                                                              |
|                             xls                              | D0 CF 11 E0                                                  | MS Excel                                                     |
|                             xls                              | [512 byte offset]  09 08 10 00 00 06 05 00                   | Excel spreadsheet subheader (MS Office)                      |
|                             XML                              | 3C 3F 78                                                     |                                                              |
|                             xml                              | 3C 3F 78 6D 6C                                               | XML Document                                                 |
|                             xml                              | FF FE 3C 00 52 00 4F 00 4F 00 54 00 53 00 54 00 55 00  42 00 | XML Document (ROOTSTUB)                                      |
|                             XMV                              | 00 50 01                                                     |                                                              |
|                             XSL                              | FF FE 3C                                                     |                                                              |
|                             xul                              | 72 73 69 6F 6E 3D 22 31 3C 3F 78 6D 6C 20 76 65 2E  30 22 3F 3E | XML User Interface Language file                             |
|                              z                               | 1F 9D                                                        | TAR Compressed Archive File                                  |
|                              Z                               | 1F 9D 8C                                                     |                                                              |
|                             ZIP                              | 50 4B 03                                                     |                                                              |
|                        zip; jar; zipx                        | 50 4B 03 04                                                  | ZIP Archive                                                  |
|                             zip                              | 50 4B 30 30                                                  | ZIP Archive (outdated)                                       |
|                             Zip                              | 50 4B 30 30 50 4B 03 04                                      | WINZIP Compressed                                            |
|                             zoo                              | 5A 4F 4F 20                                                  | ZOO Archive File                                             |

> [参考链接](https://blog.csdn.net/u011611925/article/details/83780916)
