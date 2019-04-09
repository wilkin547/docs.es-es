---
title: TextMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
ms.openlocfilehash: 67c1083daa9acfd204d4de50d4e9178b25aafcf0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097491"
---
# <a name="textmessageencodingbindingelement"></a>TextMessageEncodingBindingElement
TextMessageEncodingBindingElement  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase TextMessageEncodingBindingElement no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase TextMessageEncodingBindingElement tiene las propiedades siguientes:  
  
### <a name="encoding"></a>Codificación  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 El codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.  
  
### <a name="maxreadpoolsize"></a>MaxReadPoolSize  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 Entero que define cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.  
  
### <a name="maxwritepoolsize"></a>MaxWritePoolSize  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 Entero que define cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.  
  
### <a name="readerquotas"></a>ReaderQuotas  
 Tipo de datos: XmlDictionaryReaderQuotas  
  
 Tipo de acceso: De sólo lectura  
  
 Las cuotas de los lectores.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
