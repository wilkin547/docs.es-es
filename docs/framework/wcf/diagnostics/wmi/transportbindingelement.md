---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: bdb5ca7400a41dd724c2ad7fc76695a82874ded6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112377"
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
  
 Tipo de acceso: De sólo lectura  
  
 Un valor booleano que especifica si el usuario toma el control del direccionamiento de mensajes.  
  
### <a name="maxbufferpoolsize"></a>MaxBufferPoolSize  
 Tipo de datos: sint64  
  
 Tipo de acceso: De sólo lectura  
  
 El tamaño máximo del grupo de búferes para el enlace.  
  
### <a name="maxreceivedmessagesize"></a>MaxReceivedMessageSize  
 Tipo de datos: sint64  
  
 Tipo de acceso: De sólo lectura  
  
 El tamaño máximo para un mensaje que es procesado por este enlace.  
  
### <a name="scheme"></a>Scheme  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 El esquema URI para el transporte.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.TransportBindingElement>
