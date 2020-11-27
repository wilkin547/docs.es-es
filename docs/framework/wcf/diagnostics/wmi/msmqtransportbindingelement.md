---
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: 6590c5188e4e1758987a75fbd007099703ea6bc5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250429"
---
# <a name="msmqtransportbindingelement"></a>MsmqTransportBindingElement

MsmqTransportBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a>Métodos  

 La clase MsmqTransportBindingElement no define ningún método.  
  
## <a name="properties"></a>Propiedades  

 La clase MsmqTransportBindingElement tiene las propiedades siguientes:  
  
### <a name="maxpoolsize"></a>MaxPoolSize  

 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El tamaño máximo del grupo que contiene los objetos de mensaje de MSMQ internos.  
  
### <a name="queuetransferprotocol"></a>QueueTransferProtocol  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Un valor de enumeración que indica el transporte del canal de comunicación en cola que este enlace utiliza.  
  
### <a name="useactivedirectory"></a>UseActiveDirectory  

 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Devuelve un valor booleano que indica si las direcciones de la cola deberían convertirse utilizando Active Directory.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
