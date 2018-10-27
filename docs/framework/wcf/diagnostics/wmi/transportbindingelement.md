---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: 79d8b1f4a5127ca36eb57954cff6ee6a97e55e41
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50182663"
---
# <a name="transportbindingelement"></a>TransportBindingElement
TransportBindingElement  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase TransportBindingElement no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase TransportBindingElement tiene las propiedades siguientes:  
  
### <a name="manualaddressing"></a>ManualAddressing  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor booleano que especifica si el usuario toma el control del direccionamiento de mensajes.  
  
### <a name="maxbufferpoolsize"></a>MaxBufferPoolSize  
 Tipo de datos: sint64  
  
 Tipo de acceso: solo lectura  
  
 El tamaño máximo del grupo de búferes para el enlace.  
  
### <a name="maxreceivedmessagesize"></a>MaxReceivedMessageSize  
 Tipo de datos: sint64  
  
 Tipo de acceso: solo lectura  
  
 El tamaño máximo para un mensaje que es procesado por este enlace.  
  
### <a name="scheme"></a>Scheme  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El esquema URI para el transporte.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Channels.TransportBindingElement>
