---
title: BinaryMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
ms.openlocfilehash: e0551e7b4b05151490625912742aa6b26ef0216e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145683"
---
# <a name="binarymessageencodingbindingelement"></a>BinaryMessageEncodingBindingElement
BinaryMessageEncodingBindingElement  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase BinaryMessageEncodingBindingElement no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase BinaryMessageEncodingBindingElement tiene las propiedades siguientes.  
  
## <a name="maxreadpoolsize"></a>MaxReadPoolSize  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 Entero que define cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.  
  
## <a name="maxsessionsize"></a>maxSessionSize  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 Valor que especifica el tamaño, en bytes, del búfer usado para codificar.  
  
## <a name="maxwritepoolsize"></a>MaxWritePoolSize  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 Entero que define cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.  
  
## <a name="readerquotas"></a>ReaderQuotas  
 Tipo de datos: XmlDictionaryReaderQuotas  
  
 Tipo de acceso: De sólo lectura  
  
 Las cuotas de los lectores.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
