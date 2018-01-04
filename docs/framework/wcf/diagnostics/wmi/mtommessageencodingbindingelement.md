---
title: MtomMessageEncodingBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3cc36d7daed1a2cfaf050cbfe9661951117ff66d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="mtommessageencodingbindingelement"></a>MtomMessageEncodingBindingElement
MtomMessageEncodingBindingElement  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase MtomMessageEncodingBindingElement no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase MtomMessageEncodingBindingElement tiene las propiedades siguientes:  
  
### <a name="encoding"></a>Codificación  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.  
  
### <a name="maxreadpoolsize"></a>MaxReadPoolSize  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 Entero que define cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.  
  
### <a name="maxwritepoolsize"></a>MaxWritePoolSize  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 Entero que define cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.  
  
### <a name="readerquotas"></a>ReaderQuotas  
 Tipo de datos: XmlDictionaryReaderQuotas  
  
 Tipo de acceso: solo lectura  
  
 Las cuotas de los lectores.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
