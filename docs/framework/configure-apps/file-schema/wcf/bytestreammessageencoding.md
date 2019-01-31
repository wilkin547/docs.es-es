---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: b1215f864822de7c2df181ff92858cb73700c0d7
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286278"
---
# <a name="bytestreammessageencoding"></a>\<byteStreamMessageEncoding>
Especifica la codificación de mensajes como un flujo de bytes, con la opción especificar la codificación de caracteres.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<binaryMessageEncoding>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|messageVersion|Especifica la versión SOAP de los mensajes enviados utilizando el enlace. Esta propiedad solo se puede establecer en el valor de la versión del mensaje de <xref:System.ServiceModel.Channels.MessageVersion.None%2A>. El codificador de mensajes de flujo de bytes no admite ninguna otra versión del mensaje.<br /><br /> Este atributo es del tipo <xref:System.ServiceModel.Channels.MessageVersion>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<readerQuotas>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace. Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [Codificación de mensajes](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [Elección de un codificador de mensajes](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [Enlaces](../../../../../docs/framework/wcf/bindings.md)
- [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
