---
title: Servicio
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: aa4eecbcc8a2ef818cd99d777b0e3c2f1f222e46
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273287"
---
# <a name="service"></a>Servicio

Servicio  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## <a name="methods"></a>Métodos  

 La clase Service no define ningún método.  
  
## <a name="properties"></a>Propiedades  

 La clase Service posee las siguientes propiedades:  
  
### <a name="baseaddresses"></a>BaseAddresses  

 Tipo de datos: matriz de cadenas  
  
 Tipo de acceso: solo lectura  
  
 Las direcciones base utilizadas por el servicio.  
  
### <a name="behaviors"></a>Comportamientos  

 Tipo de datos: matriz de comportamientos  
  
 Tipo de acceso: solo lectura  
  
 Los comportamientos asociados a este servicio.  
  
### <a name="configurationname"></a>ConfigurationName  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 ServiceElement_BehaviorConfiguration  
  
### <a name="counterinstancename"></a>CounterInstanceName  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Nombre de la instancia de los contadores de rendimiento del servicio.  
  
### <a name="distinguishedname"></a>DistinguishedName  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Nombre de servicio en la dirección.  
  
### <a name="extensions"></a>Extensiones  

 Tipo de datos: matriz de cadenas  
  
 Tipo de acceso: solo lectura  
  
 Los contextos de instancia para las extensiones de la instancia de servicio.  
  
### <a name="metadata"></a>Metadatos  

 Tipo de datos: matriz de cadenas  
  
 Tipo de acceso: solo lectura  
  
 Los valores de metadatos de servicio.  
  
### <a name="name"></a>NOMBRE  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El nombre único de este servicio.  
  
### <a name="namespace"></a>Espacio de nombres  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El espacio de nombres del servicio.  
  
### <a name="opened"></a>Abierto  

 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El momento en el que se abrió el servicio.  
  
### <a name="outgoingchannels"></a>OutgoingChannels  

 Tipo de datos: matriz de canal  
  
 Tipo de acceso: solo lectura  
  
 Los canales que salen de la instancia del servicio.  
  
### <a name="processid"></a>ProcessId  

 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El id. de proceso que hospeda el servicio.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|
