# Maîtrise de poste - Day 1

## Self-footprinting

### Host OS

* **Déterminer les principales informations de votre machine**
* Nom de la machine
```
PS C:\Users\hugof> wmic CPU get SystemName
SystemName
LAPTOP-TFP4BO8F.
```

* OS et version 
```
PS C:\Users\hugof> wmic OS get Name
Name
Microsoft Windows 10 Famille|C:\WINDOWS|\Device\Harddisk0\Partition3
```
```
PS C:\Users\hugof> wmic OS get Version
Version
10.0.18362
```

* Architecture processeur
``` 
PS C:\Users\hugof> 
wmic CPU get DataWidth
DataWidth
64
```

* Modèle du processeur 
```
PS C:\Users\hugof> wmic CPU get Name
Name
AMD Ryzen 3 2200U with Radeon Vega Mobile Gfx
```

* Quantité RAM et modèle de la RAM
```
PS C:\Users\hugof> wmic MEMORYCHIP get Capacity
Capacity
4294967296
4294967296
```
```
C:\Users\hugof> wmic MEMORYCHIP get Manufacturer
Manufacturer
Samsung
Samsung
```
### Devices
* **Trouver**
* La marque et le modèle de votre processeur
``` 
PS C:\Users\hugof> wmic CPU get Name
Name
AMD Ryzen 3 2200U with Radeon Vega Mobile Gfx
```

* Identifier le nombre de processeurs, le nombre de coeurs : 4 processeur(s) logique(s), 2 cœur(s)
```
PS C:\Users\hugof> wmic CPU get NumberOfEnabledCore
NumberOfEnabledCore
2
```
```
PS C:\Users\hugof> wmic CPU get NumberOfLogicalProcessors
NumberOfLogicalProcessors
4
```

* La marque et le modèle :
* de votre touchpad/trackpad : Synaptics SMBus TouchPad
* de vos enceintes intégrées : AMD High Definition Audio Device, Realtek High Definition Audio
* de votre disque dur principal : 
```
PS C:\Users\hugof> wmic DISKDRIVE get MODEL
Model
HGST HTS541010B7E610
```

* **Disque dur**
* Identifier les différentes paritions de votre/vos disque(s) dur(s)

### Network
* **Afficher la liste des cartes réseau de votre machine**

```
Carte réseau sans fil Wi-Fi :

   Suffixe DNS propre à la connexion. . . : home
   Adresse IPv6. . . . . . . . . . . . . .: 2a01:cb18:71f:8a00:dcb:e295:cc02:2514
   Adresse IPv6 temporaire . . . . . . . .: 2a01:cb18:71f:8a00:c8b4:77f1:c982:b1a5
   Adresse IPv6 de liaison locale. . . . .: fe80::dcb:e295:cc02:2514%9
   Adresse IPv4. . . . . . . . . . . . . .: 192.168.1.19
   Masque de sous-réseau. . . . . . . . . : 255.255.255.0
   Passerelle par défaut. . . . . . . . . : fe80::3e17:10ff:fe3d:3690%9
                                       192.168.1.1
```

Cette carte réseau me permet de pouvoir me connecter et utilisé tout ce qui est relatif à internet.
* **Lister tous les ports TCP et UDP en utilisation**
    * déterminer quel programme tourne derrière chacun des ports.
    * expliquer la fonction de chacun de ces programmes.

```
PS C:\WINDOWS\system32> netstat -a -b
Connexions actives
  TCP    192.168.1.19:49691     40.67.254.36:https     ESTABLISHED
  WpnService
 [svchost.exe]
  TCP    192.168.1.19:50032     ec2-63-32-245-71:https  ESTABLISHED
 [CoreSync.exe]
  TCP    192.168.1.19:50203     13.107.4.52:http       ESTABLISHED
 [SkypeApp.exe]
  TCP    192.168.1.19:52228     ec2-34-192-16-202:https  ESTABLISHED
 [CoreSync.exe]
  TCP    192.168.1.19:52579     152.199.19.160:https   ESTABLISHED
 [Code.exe]
  TCP    192.168.1.19:52623     ec2-52-196-23-24:https  ESTABLISHED
 [MicrosoftEdgeCP.exe]
  TCP    192.168.1.19:52690     52.178.105.179:http    ESTABLISHED
 [MicrosoftEdgeCP.exe]
  TCP    192.168.1.19:52691     52.178.105.179:http    ESTABLISHED
 [MicrosoftEdgeCP.exe]
  TCP    192.168.1.19:52693     52.178.105.179:https   ESTABLISHED
 [MicrosoftEdgeCP.exe]
  TCP    192.168.1.19:52694     52.178.105.179:https   ESTABLISHED
 [MicrosoftEdgeCP.exe]
  TCP    192.168.1.19:52695     52.178.105.179:https   ESTABLISHED
 [MicrosoftEdgeCP.exe]
  TCP    192.168.1.19:52703     52.178.105.179:https   ESTABLISHED
 [MicrosoftEdgeCP.exe]
  TCP    192.168.1.19:52704     52.178.105.179:https   ESTABLISHED
 [MicrosoftEdgeCP.exe]
  TCP    192.168.1.19:52723     ec2-52-54-178-155:https  ESTABLISHED
 [MicrosoftEdgeCP.exe]
  TCP    192.168.1.19:52724     a-0003:https           ESTABLISHED
 [MicrosoftEdgeCP.exe]
  TCP    192.168.1.19:52737     93.184.220.29:http     ESTABLISHED
 [SearchUI.exe]
  TCP    192.168.1.19:52740     13.107.246.254:https   ESTABLISHED
 [SearchUI.exe]
  TCP    192.168.1.19:52742     13.107.42.254:https    ESTABLISHED
 [SearchUI.exe]
  TCP    192.168.1.19:52743     204.79.197.222:https   ESTABLISHED
 [SearchUI.exe]
  TCP    [2a01:cb18:71f:8a00:695f:678:9d7e:b6f5]:52637  [2603:1026:700:15::2]:https  ESTABLISHED
 [SearchUI.exe]
  TCP    [2a01:cb18:71f:8a00:695f:678:9d7e:b6f5]:52732  [2620:1ec:c11::200]:https  ESTABLISHED
 [SearchUI.exe]
  TCP    [2a01:cb18:71f:8a00:695f:678:9d7e:b6f5]:52733  [2620:1ec:c::11]:https  ESTABLISHED
 [SearchUI.exe]
  TCP    [2a01:cb18:71f:8a00:695f:678:9d7e:b6f5]:52734  text-lb:https          ESTABLISHED
 [SearchUI.exe]
  TCP    [2a01:cb18:71f:8a00:695f:678:9d7e:b6f5]:52735  [2606:4700:90:0:f22e:fbec:5bed:a9b9]:https  ESTABLISHED
 [SearchUI.exe]
  TCP    [2a01:cb18:71f:8a00:695f:678:9d7e:b6f5]:52741  [2620:1ec:8f8::254]:https  ESTABLISHED
 [SearchUI.exe]
  UDP    0.0.0.0:500            *:*
  IKEEXT
 [svchost.exe]
  UDP    0.0.0.0:4500           *:*
  IKEEXT
 [svchost.exe]
  UDP    0.0.0.0:5050           *:*
  CDPSvc
 [svchost.exe]
  UDP    0.0.0.0:5353           *:*
  Dnscache
 [svchost.exe]
  UDP    0.0.0.0:5355           *:*
  Dnscache
 [svchost.exe]
  UDP    0.0.0.0:6646           *:*
 [MMSSHOST.EXE]
  UDP    0.0.0.0:45769          *:*
 [DiscSoftBusServiceUltra.exe]
  UDP    0.0.0.0:54614          *:*
 [mDNSResponder.exe]
  UDP    10.2.1.1:1900          *:*
  SSDPSRV
 [svchost.exe]
  UDP    10.2.1.1:5353          *:*
 [mDNSResponder.exe]
  UDP    10.2.1.1:65514         *:*
  SSDPSRV
 [svchost.exe]
  UDP    10.3.1.1:1900          *:*
  SSDPSRV
 [svchost.exe]
  UDP    10.3.1.1:5353          *:*
 [mDNSResponder.exe]
  UDP    10.3.1.1:65513         *:*
  SSDPSRV
 [svchost.exe]
  UDP    10.3.2.1:1900          *:*
  SSDPSRV
 [svchost.exe]
  UDP    10.3.2.1:5353          *:*
 [mDNSResponder.exe]
  UDP    10.3.2.1:65515         *:*
  SSDPSRV
 [svchost.exe]
  UDP    127.0.0.1:1900         *:*
  SSDPSRV
 [svchost.exe]
  UDP    127.0.0.1:44301        *:*
 [PnkBstrA.exe]
  UDP    127.0.0.1:54613        *:*
  iphlpsvc
 [svchost.exe]
  UDP    127.0.0.1:65519        *:*
  SSDPSRV
 [svchost.exe]
  UDP    192.168.1.19:1900      *:*
  SSDPSRV
 [svchost.exe]
  UDP    192.168.1.19:5353      *:*
 [mDNSResponder.exe]
  UDP    192.168.1.19:65518     *:*
  SSDPSRV
 [svchost.exe]
  UDP    192.168.11.1:1900      *:*
  SSDPSRV
 [svchost.exe]
  UDP    192.168.11.1:5353      *:*
 [mDNSResponder.exe]
  UDP    192.168.11.1:65517     *:*
  SSDPSRV
 [svchost.exe]
  UDP    192.168.56.1:1900      *:*
  SSDPSRV
 [svchost.exe]
  UDP    192.168.56.1:5353      *:*
 [mDNSResponder.exe]
  UDP    192.168.56.1:65512     *:*
  SSDPSRV
 [svchost.exe]
  UDP    192.168.154.1:1900     *:*
  SSDPSRV
 [svchost.exe]
  UDP    192.168.154.1:5353     *:*
 [mDNSResponder.exe]
  UDP    192.168.154.1:65516    *:*
  SSDPSRV
 [svchost.exe]
  UDP    [::]:500               *:*
  IKEEXT
 [svchost.exe]
  UDP    [::]:4500              *:*
  IKEEXT
 [svchost.exe]
  UDP    [::]:5353              *:*
  Dnscache
 [svchost.exe]
  UDP    [::]:5355              *:*
  Dnscache
 [svchost.exe]
  UDP    [::]:54615             *:*
 [mDNSResponder.exe]
  UDP    [::1]:1900             *:*
  SSDPSRV
 [svchost.exe]
  UDP    [::1]:5353             *:*
 [mDNSResponder.exe]
  UDP    [::1]:58398            *:*
  RemoteAccess
 [svchost.exe]
  UDP    [::1]:58399            *:*
  RemoteAccess
 [svchost.exe]
  UDP    [::1]:65511            *:*
  SSDPSRV
 [svchost.exe]
  UDP    [fe80::dcb:e295:cc02:2514%9]:1900  *:*
  SSDPSRV
 [svchost.exe]
  UDP    [fe80::dcb:e295:cc02:2514%9]:65510  *:*
  SSDPSRV
 [svchost.exe]
  UDP    [fe80::24cb:d5d8:8596:8ef7%27]:1900  *:*
  SSDPSRV
 [svchost.exe]
  UDP    [fe80::24cb:d5d8:8596:8ef7%27]:65507  *:*
  SSDPSRV
 [svchost.exe]
  UDP    [fe80::34fc:6f09:522:311a%5]:1900  *:*
  SSDPSRV
 [svchost.exe]
  UDP    [fe80::34fc:6f09:522:311a%5]:65504  *:*
  SSDPSRV
 [svchost.exe]
  UDP    [fe80::48fc:6679:b2c1:bbfd%10]:1900  *:*
  SSDPSRV
 [svchost.exe]
  UDP    [fe80::48fc:6679:b2c1:bbfd%10]:65509  *:*
  SSDPSRV
 [svchost.exe]
  UDP    [fe80::90df:af54:2a07:c83f%13]:1900  *:*
  SSDPSRV
 [svchost.exe]
  UDP    [fe80::90df:af54:2a07:c83f%13]:65506  *:*
  SSDPSRV
 [svchost.exe]
  UDP    [fe80::9d88:ad69:3055:b60b%21]:1900  *:*
  SSDPSRV
 [svchost.exe]
  UDP    [fe80::9d88:ad69:3055:b60b%21]:65505  *:*
  SSDPSRV
 [svchost.exe]
  UDP    [fe80::fdb7:e1f4:8486:cc37%4]:1900  *:*
  SSDPSRV
 [svchost.exe]
  UDP    [fe80::fdb7:e1f4:8486:cc37%4]:65508  *:*
  SSDPSRV
 [svchost.exe]
```

Tout les ports **"TCP"** qui sont en **"ESTABLISHED"** sont soit utiliser pour des programmes, des exécutables, des processus de Windows (SearchUI.exe,svchost.exe,CoreSync.exe,Code.exe) ou alors des applis qui sont en fonctionnement actuellement (SkypeApp.exe,MicrosoftEdgeCP.exe)
Et pour tout les ports **"UDP"** on retrouve que des processus Windows (MMSSHOST.EXE, DiscSoftBusServiceUltra.exe, mDNSResponder.exe, PnkBstrA.exe, svchost.exe).
### Users
* **Déterminer la liste des utilisateurs de la machine**

```
PS C:\WINDOWS\system32> net user

comptes d’utilisateurs de \\LAPTOP-TFP4BO8F

-------------------------------------------------------------------------------
Administrateur           DefaultAccount           hugof
Invité                   WDAGUtilityAccount       YNOV01
YNOV02                   YNOV03                   YNOV04
YNOV05                   YNOV06                   YNOV07
YNOV08                   YNOV09                   YNOV10
YNOV11                   YNOV12                   YNOV13
YNOV14                   YNOV15                   YNOV16
YNOV17                   YNOV18                   YNOV19
YNOV20                   YNOV201                  YNOV202
YNOV203                  YNOV204                  YNOV205
YNOV206                  YNOV207                  YNOV208
YNOV209                  YNOV210                  YNOV211
YNOV212                  YNOV213                  YNOV214
YNOV215                  YNOV216                  YNOV217
YNOV218                  YNOV219                  YNOV220
YNOV301                  YNOV302                  YNOV303
YNOV304                  YNOV305                  YNOV306
YNOV307                  YNOV308                  YNOV309
YNOV310                  YNOV311                  YNOV312
YNOV313                  YNOV314                  YNOV315
YNOV316                  YNOV317                  YNOV318
YNOV319                  YNOV320
La commande s’est terminée correctement.

PS C:\WINDOWS\system32>
```

* **déterminer le nom de l'utilisateur qui est full admin sur la machine**

```
PS C:\WINDOWS\system32> net user hugof
Nom d’utilisateur                              hugof
Nom complet                                    Hugo Ferreira Silva
Commentaire
Commentaires utilisateur
Code du pays ou de la région                   000 (Valeur par défaut du système)
Compte : actif                                 Oui
Le compte expire                               Jamais

Mot de passe : dernier changmt.                ‎29/‎07/‎2018 01:15:48
Le mot de passe expire                         Jamais
Le mot de passe modifiable                     ‎29/‎07/‎2018 01:15:48
Mot de passe exigé                             Oui
L’utilisateur peut changer de mot de passe     Oui

Stations autorisées                            Tout
Script d’ouverture de session
Profil d’utilisateur
Répertoire de base
Dernier accès                                  Jamais

Heures d’accès autorisé                        Tout

Appartient aux groupes locaux                  *Administrateurs
                                               *HelpLibraryUpdaters
                                               *Utilisateurs
                                               *Utilisateurs du journ
Appartient aux groupes globaux                 *Aucun
La commande s’est terminée correctement.

PS C:\WINDOWS\system32>
```

### Processus
* **Déterminer la liste des processus de la machine**

```
PS C:\WINDOWS\system32> tasklist

Nom de l’image                 PID Nom de la sessio Numéro de s Utilisation
========================= ======== ================ =========== ============
System Idle Process              0 Services                   0         8 Ko
System                           4 Services                   0     4 000 Ko
Registry                        96 Services                   0    85 164 Ko
smss.exe                       464 Services                   0     1 088 Ko
csrss.exe                      764 Services                   0     5 484 Ko
wininit.exe                    860 Services                   0     6 140 Ko
csrss.exe                      880 Console                    1     6 348 Ko
winlogon.exe                   968 Console                    1    12 576 Ko
services.exe                  1008 Services                   0     9 940 Ko
lsass.exe                       72 Services                   0    26 540 Ko
svchost.exe                    708 Services                   0     3 620 Ko
fontdrvhost.exe                720 Services                   0     4 716 Ko
fontdrvhost.exe                656 Console                    1     8 416 Ko
svchost.exe                    748 Services                   0    33 888 Ko
WUDFHost.exe                  1036 Services                   0     6 948 Ko
svchost.exe                   1100 Services                   0    17 948 Ko
svchost.exe                   1148 Services                   0     9 636 Ko
dwm.exe                       1236 Console                    1    72 576 Ko
svchost.exe                   1340 Services                   0     8 036 Ko
svchost.exe                   1384 Services                   0     4 748 Ko
svchost.exe                   1392 Services                   0     6 876 Ko
svchost.exe                   1420 Services                   0    10 004 Ko
svchost.exe                   1428 Services                   0     9 836 Ko
svchost.exe                   1444 Services                   0    10 372 Ko
svchost.exe                   1640 Services                   0    10 956 Ko
svchost.exe                   1668 Services                   0    14 656 Ko
svchost.exe                   1760 Services                   0     8 740 Ko
svchost.exe                   1852 Services                   0    11 624 Ko
svchost.exe                   1948 Services                   0     5 772 Ko
svchost.exe                   1996 Services                   0    14 084 Ko
svchost.exe                   1564 Services                   0     7 656 Ko
SynTPEnhService.exe           2112 Services                   0     8 456 Ko
svchost.exe                   2140 Services                   0     5 248 Ko
svchost.exe                   2176 Services                   0    10 600 Ko
svchost.exe                   2232 Services                   0     7 108 Ko
svchost.exe                   2260 Services                   0     7 028 Ko
svchost.exe                   2340 Services                   0     6 092 Ko
svchost.exe                   2416 Services                   0    11 948 Ko
svchost.exe                   2424 Services                   0     9 348 Ko
svchost.exe                   2520 Services                   0    15 964 Ko
atiesrxx.exe                  2560 Services                   0     5 476 Ko
svchost.exe                   2584 Services                   0     7 256 Ko
svchost.exe                   2680 Services                   0     8 148 Ko
svchost.exe                   2792 Services                   0   101 104 Ko
svchost.exe                   2788 Services                   0     5 452 Ko
svchost.exe                   2804 Services                   0     6 332 Ko
atieclxx.exe                  2812 Console                    1    10 276 Ko
svchost.exe                   2896 Services                   0     8 808 Ko
svchost.exe                   2920 Services                   0     7 276 Ko
svchost.exe                   2928 Services                   0    10 264 Ko
Memory Compression            3028 Services                   0   438 232 Ko
svchost.exe                   2768 Services                   0    18 112 Ko
svchost.exe                   3088 Services                   0     7 828 Ko
svchost.exe                   3120 Services                   0    17 800 Ko
RtkAudioService64.exe         3136 Services                   0     7 848 Ko
svchost.exe                   3644 Services                   0     6 188 Ko
svchost.exe                   3688 Services                   0     8 980 Ko
svchost.exe                   3696 Services                   0     6 040 Ko
svchost.exe                   3860 Services                   0     7 368 Ko
svchost.exe                   3940 Services                   0    17 872 Ko
svchost.exe                   4092 Services                   0    13 476 Ko
spoolsv.exe                   3344 Services                   0    11 712 Ko
svchost.exe                   3444 Services                   0    17 148 Ko
wlanext.exe                   3080 Services                   0     6 640 Ko
conhost.exe                   3628 Services                   0     5 092 Ko
svchost.exe                   4500 Services                   0    19 144 Ko
svchost.exe                   4760 Services                   0    29 872 Ko
svchost.exe                   4768 Services                   0    13 520 Ko
svchost.exe                   4776 Services                   0    43 072 Ko
svchost.exe                   4800 Services                   0     7 024 Ko
svchost.exe                   4820 Services                   0    12 096 Ko
svchost.exe                   4948 Services                   0     5 608 Ko
svchost.exe                   4968 Services                   0     6 324 Ko
svchost.exe                   5056 Services                   0     5 160 Ko
svchost.exe                   5088 Services                   0     4 724 Ko
svchost.exe                   5116 Services                   0    18 864 Ko
PnkBstrA.exe                  2080 Services                   0     6 260 Ko
HPWMISVC.exe                  2064 Services                   0     8 088 Ko
vmware-authd.exe              4024 Services                   0    11 564 Ko
BTDevMgr.exe                  4240 Services                   0     6 984 Ko
sqlwriter.exe                 4336 Services                   0     6 932 Ko
vmnat.exe                     4360 Services                   0     6 644 Ko
RtkBtManServ.exe              4272 Services                   0     7 012 Ko
mDNSResponder.exe             1868 Services                   0     5 940 Ko
AdobeUpdateService.exe        1932 Services                   0     8 428 Ko
MsMpEng.exe                   4420 Services                   0   149 416 Ko
mfemms.exe                    1964 Services                   0     7 412 Ko
PEFService.exe                2244 Services                   0     8 520 Ko
ModuleCoreService.exe         4100 Services                   0    38 364 Ko
vmnetdhcp.exe                 4552 Services                   0     4 564 Ko
WildTangentHelperService.     4604 Services                   0    16 136 Ko
OfficeClickToRun.exe          3376 Services                   0    47 388 Ko
vmware-usbarbitrator64.ex     3724 Services                   0    10 788 Ko
AGSService.exe                5128 Services                   0     9 160 Ko
AGMService.exe                5136 Services                   0     9 824 Ko
svchost.exe                   5504 Services                   0     8 236 Ko
MMSSHOST.exe                  5528 Services                   0    34 016 Ko
mfevtps.exe                   5588 Services                   0    10 248 Ko
svchost.exe                   5640 Services                   0    18 660 Ko
ProtectedModuleHost.exe       5720 Services                   0    12 960 Ko
sqlservr.exe                  1608 Services                   0   104 444 Ko
mfefire.exe                   1456 Services                   0     8 356 Ko
sqlservr.exe                  1480 Services                   0   102 424 Ko
sqlservr.exe                  1688 Services                   0   100 896 Ko
ReportingServicesService.     1684 Services                   0    54 200 Ko
ReportingServicesService.     1908 Services                   0    54 744 Ko
ReportingServicesService.     4396 Services                   0    54 168 Ko
dllhost.exe                   6428 Services                   0    10 120 Ko
dllhost.exe                   6996 Services                   0     8 752 Ko
svchost.exe                   4132 Services                   0    10 984 Ko
McCSPServiceHost.exe          4172 Services                   0    16 400 Ko
Microsoft.ReportingServic     5448 Services                   0    52 764 Ko
Microsoft.ReportingServic     5384 Services                   0    53 460 Ko
conhost.exe                   5400 Services                   0     6 888 Ko
conhost.exe                   5428 Services                   0     6 880 Ko
Microsoft.ReportingServic     5540 Services                   0    53 144 Ko
conhost.exe                   4508 Services                   0     6 908 Ko
svchost.exe                   7424 Services                   0    18 948 Ko
svchost.exe                   7480 Services                   0     6 172 Ko
NisSrv.exe                    7556 Services                   0     9 536 Ko
MfeAVSvc.exe                  7840 Services                   0     9 656 Ko
mcshield.exe                  5336 Services                   0     5 996 Ko
Launchpad.exe                 5076 Services                   0    15 812 Ko
Launchpad.exe                 8252 Services                   0    15 816 Ko
SearchIndexer.exe             8320 Services                   0    58 624 Ko
fdlauncher.exe                8328 Services                   0     4 692 Ko
fdhost.exe                    8552 Services                   0     5 720 Ko
conhost.exe                   8604 Services                   0     4 900 Ko
fdlauncher.exe                8852 Services                   0     5 160 Ko
fdlauncher.exe                9196 Services                   0     5 172 Ko
fdhost.exe                    8020 Services                   0     6 268 Ko
WmiPrvSE.exe                  8112 Services                   0     9 744 Ko
conhost.exe                   8612 Services                   0     4 896 Ko
fdhost.exe                    4668 Services                   0     6 268 Ko
svchost.exe                   1504 Services                   0    18 488 Ko
conhost.exe                   9256 Services                   0     4 896 Ko
unsecapp.exe                  9692 Services                   0     6 272 Ko
mfevtps.exe                   3756 Services                   0     5 772 Ko
mcapexe.exe                   8864 Services                   0     1 668 Ko
SynTPEnh.exe                  4424 Console                    1    17 772 Ko
sihost.exe                    9172 Console                    1    30 248 Ko
svchost.exe                   9292 Console                    1    33 092 Ko
svchost.exe                   9284 Console                    1     7 280 Ko
svchost.exe                   8300 Services                   0    14 468 Ko
svchost.exe                   9828 Console                    1    47 708 Ko
svchost.exe                   9204 Services                   0    16 852 Ko
taskhostw.exe                10588 Console                    1    40 968 Ko
svchost.exe                  10996 Services                   0     6 812 Ko
explorer.exe                 11044 Console                    1   141 876 Ko
ctfmon.exe                   11060 Console                    1    22 276 Ko
svchost.exe                   9376 Console                    1    24 944 Ko
ModuleCoreService.exe         1232 Console                    1    16 644 Ko
conhost.exe                   6824 Console                    1     5 528 Ko
dllhost.exe                  10668 Console                    1     7 556 Ko
HPCommRecovery.exe           10496 Services                   0    21 252 Ko
HPJumpStartBridge.exe         8368 Services                   0    25 252 Ko
svchost.exe                  11300 Console                    1    19 204 Ko
HPSupportSolutionsFramewo    11748 Services                   0    36 624 Ko
SgrmBroker.exe               12020 Services                   0     6 280 Ko
svchost.exe                  12104 Services                   0    13 096 Ko
svchost.exe                  11292 Services                   0    11 224 Ko
StartMenuExperienceHost.e    10612 Console                    1    57 852 Ko
svchost.exe                  10392 Services                   0    17 724 Ko
ApplicationFrameHost.exe      3956 Console                    1    36 784 Ko
SkypeApp.exe                 12320 Console                    1    41 312 Ko
SkypeBackgroundHost.exe      12348 Console                    1     8 944 Ko
RuntimeBroker.exe            12576 Console                    1    22 600 Ko
dllhost.exe                  13080 Console                    1    15 736 Ko
RuntimeBroker.exe            12424 Console                    1    41 348 Ko
svchost.exe                  13988 Services                   0    18 708 Ko
YourPhone.exe                14020 Console                    1    31 620 Ko
RuntimeBroker.exe            12656 Console                    1    42 668 Ko
RuntimeBroker.exe            13220 Console                    1    12 960 Ko
svchost.exe                  13716 Services                   0    11 896 Ko
SecurityHealthSystray.exe    12096 Console                    1     7 852 Ko
RtkNGUI64.exe                11208 Console                    1    13 372 Ko
SecurityHealthService.exe    11116 Services                   0    12 804 Ko
RAVBg64.exe                  14168 Console                    1    15 236 Ko
RuntimeBroker.exe            14364 Console                    1    17 952 Ko
OneDrive.exe                 14680 Console                    1    47 368 Ko
svchost.exe                  14724 Services                   0     8 128 Ko
CCXProcess.exe               15100 Console                    1     2 228 Ko
node.exe                     15180 Console                    1    47 756 Ko
conhost.exe                  15200 Console                    1     5 376 Ko
DTAgent.exe                  15268 Console                    1    57 608 Ko
HPMSGSVC.exe                 13176 Console                    1     8 016 Ko
RtlS5Wake.exe                14836 Console                    1    11 920 Ko
jusched.exe                  14872 Console                    1     6 780 Ko
vmware-tray.exe              14960 Console                    1     9 780 Ko
unsecapp.exe                 14980 Console                    1     6 696 Ko
svchost.exe                  13396 Services                   0     4 960 Ko
AdobeIPCBroker.exe           12388 Console                    1    11 160 Ko
SearchUI.exe                 15228 Console                    1    89 932 Ko
DiscSoftBusServiceUltra.e    14412 Services                   0    12 044 Ko
Adobe Desktop Service.exe    11924 Console                    1    97 104 Ko
svchost.exe                  14592 Services                   0     9 384 Ko
ShellExperienceHost.exe      16076 Console                    1    39 672 Ko
RuntimeBroker.exe            15496 Console                    1    15 004 Ko
CoreSync.exe                 13340 Console                    1    31 356 Ko
AdobeNotificationClient.e    16736 Console                    1    14 212 Ko
CCLibrary.exe                13152 Console                    1     2 228 Ko
node.exe                     11940 Console                    1    47 476 Ko
conhost.exe                  16284 Console                    1     5 440 Ko
RuntimeBroker.exe            16928 Console                    1     5 780 Ko
RuntimeBroker.exe            16188 Console                    1    24 240 Ko
Music.UI.exe                 15616 Console                    1       124 Ko
HxOutlook.exe                13052 Console                    1       244 Ko
RuntimeBroker.exe            17040 Console                    1    18 724 Ko
HxTsr.exe                     3828 Console                    1       448 Ko
SystemSettings.exe            4976 Console                    1       124 Ko
svchost.exe                   4612 Services                   0    11 028 Ko
smartscreen.exe              15288 Console                    1    34 204 Ko
WindowsInternal.Composabl     6816 Console                    1    38 832 Ko
Microsoft.Photos.exe         12844 Console                    1    38 544 Ko
Video.UI.exe                  3144 Console                    1     7 504 Ko
RuntimeBroker.exe             7160 Console                    1     8 716 Ko
RuntimeBroker.exe            14908 Console                    1    28 604 Ko
svchost.exe                   8132 Services                   0     8 956 Ko
taskhostw.exe                 3996 Console                    1    16 724 Ko
MicrosoftEdge.exe            16960 Console                    1   145 880 Ko
browser_broker.exe           17672 Console                    1    16 104 Ko
MicrosoftEdgeSH.exe           2656 Console                    1    23 492 Ko
MicrosoftEdgeCP.exe          10972 Console                    1   163 524 Ko
SettingSyncHost.exe          17860 Console                    1     4 972 Ko
svchost.exe                   5200 Services                   0     8 852 Ko
MicrosoftEdgeCP.exe          17792 Console                    1    98 488 Ko
MicrosoftEdgeCP.exe           5308 Console                    1   231 540 Ko
MicrosoftEdgeCP.exe          10596 Console                    1    25 416 Ko
Code.exe                     14288 Console                    1    85 072 Ko
Code.exe                     17676 Console                    1   165 788 Ko
Code.exe                      5956 Console                    1    23 868 Ko
Code.exe                     18620 Console                    1    63 536 Ko
Code.exe                     18936 Console                    1    11 468 Ko
MicrosoftEdgeCP.exe          19092 Console                    1    60 860 Ko
McUICnt.exe                  19028 Console                    1    27 120 Ko
CodeSetup-stable-d69a79b7    17500 Console                    1     6 332 Ko
CodeSetup-stable-d69a79b7    19124 Console                    1    16 536 Ko
DTShellHlp.exe                4688 Console                    1    15 996 Ko
powershell.exe               19868 Console                    1    59 840 Ko
conhost.exe                  19880 Console                    1    13 248 Ko
MicrosoftEdgeCP.exe          18528 Console                    1   290 068 Ko
MicrosoftEdgeCP.exe          19068 Console                    1   562 772 Ko
audiodg.exe                  16312 Services                   0    30 980 Ko
MicrosoftEdgeSH.exe           5340 Console                    1    48 464 Ko
MicrosoftEdgeCP.exe          13688 Console                    1    52 444 Ko
SearchProtocolHost.exe        9024 Console                    1     7 340 Ko
Code.exe                      4184 Console                    1   171 848 Ko
CodeHelper.exe               17644 Console                    1    14 588 Ko
Code.exe                     20336 Console                    1    94 152 Ko
conhost.exe                   2304 Console                    1    11 100 Ko
Code.exe                     11972 Console                    1    35 684 Ko
conhost.exe                  17344 Console                    1    11 136 Ko
vsls-agent.exe                2308 Console                    1    48 248 Ko
MicrosoftEdgeCP.exe          18568 Console                    1   210 772 Ko
MicrosoftEdgeCP.exe          17576 Console                    1   179 804 Ko
SearchProtocolHost.exe       18340 Services                   0     8 804 Ko
svchost.exe                   9824 Services                   0    12 968 Ko
svchost.exe                  17724 Services                   0     9 044 Ko
svchost.exe                   4744 Services                   0    11 984 Ko
svchost.exe                  12848 Services                   0    16 216 Ko
MicrosoftEdgeCP.exe           7780 Console                    1    27 564 Ko
tasklist.exe                 16584 Console                    1    10 108 Ko
WmiPrvSE.exe                 15720 Services                   0     8 888 Ko
PS C:\WINDOWS\system32>
```

* **choisissez 5 services système et expliquer leur utilité**

**svchost.exe** : est un processus générique (generic host process ) pour les services exécutés à partir de bibliothèques dynamiques.Pour faciliter le développement d'applications et la réutilisation de fonctions génériques propres à Windows.

**WmiPrvSE.exe** : Le Service de Fournisseur d'Instrumentation pour la Gestion de Windows est un processus d'hôte pour les services Windows WMI. Il sert à fournir des informations sur la gestion et le contrôle dans un environnement d'entreprise, laissant aux administrateurs du système de pouvoir demander ainsi que de pouvoir changer l'information sur les systèmes de bureaux, dans les applications et dans les composants de réseaux.

**audiodg.exe** : Sert pour tout ce qui l'audio.

**SecurityHealthService.exe** : Sert pour protéger "l'état de santé" de l'ordinateur.

**SgrmBroker.exe** : Sert pour le moniteur.