---
title: MsmqTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c0c2c5d54050216c91a318a407341c4ffb9cb687
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="msmqtransportbindingelement"></a>MsmqTransportBindingElement
MsmqTransportBindingElement  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
 Tipo de datos: cadena  
  
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
 <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
