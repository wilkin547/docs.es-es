---
title: web de Office
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: 0cfeb178e26f6c93e29210accf5d7866cc1fca02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487152"
---
# <a name="service"></a>web de Office
web de Office  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
  
### <a name="behaviors"></a>comportamientos  
 Tipo de datos: matriz de comportamientos  
  
 Tipo de acceso: solo lectura  
  
 Los comportamientos asociados a este servicio.  
  
### <a name="configurationname"></a>ConfigurationName  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 ServiceElement_BehaviorConfiguration  
  
### <a name="counterinstancename"></a>CounterInstanceName  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Nombre de la instancia de los contadores de rendimiento del servicio.  
  
### <a name="distinguishedname"></a>DistinguishedName  
 Tipo de datos: cadena  
  
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
  
### <a name="name"></a>nombre  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El nombre único de este servicio.  
  
### <a name="namespace"></a>Espacio de nombres  
 Tipo de datos: cadena  
  
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
