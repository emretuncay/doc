# **1. ZAD Haberleşme Mimarisi**

<div align="center">

```plantuml
@startuml

frame "VEHICLE" as VEHICLE #lightyellow{
    frame AUTOPILOT {
    rectangle ACU #lightgreen
    rectangle APBB #lightgreen
    }
rectangle "MISSION COMPUTER" as MISSIONCOMPUTER #lightgreen
}

frame "GROUND STATION" as GS #lightyellow{
rectangle "DCP SERVER" as DCPSERVER #lightblue
rectangle "GS CONTROLLER" as GSCONTROLLER #lightgreen
rectangle "CHARGER CONTROLLER" as CHARGERCONTROLLER #lightgreen
}


rectangle GCS #lightgreen

ACU<-down->APBB
GCS<-down->DCPSERVER
ACU<-down->MISSIONCOMPUTER
DCPSERVER<-right->ACU
DCPSERVER<-left->GSCONTROLLER
DCPSERVER<-down->CHARGERCONTROLLER

@enduml
```
</div>


# **2. ZAD Telemetri ve Komut Mesajları**
<div align="center">

|          **Mesaj İsmi**         | **Mesaj ID** | **Kaynak** | **Durak** | **Veri Boyutu** | **Frekans** |
|:-------------------------------:|:------------:|:----------:|:---------:|:---------------:|:-----------:|
| [UAV Heartbeat](#uav-heartbeat) |    0x1000    |     UAV    |    GCS    |      4byte      |     10Hz    |
| [GCS Heartbeat](#gcs-heartbeat) |    0x1001    |     GCS    |    UAV    |      4byte      |     10Hz    |

</div>

## **UAV Heartbeat**

## **GCS Heartbeat**
