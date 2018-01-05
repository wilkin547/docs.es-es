---
title: '&lt;xmlSerializer&gt; (Elemento)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 059fe3661878b51ef27facc2888286ecd1aaa97a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="ltxmlserializergt-element"></a>&lt;xmlSerializer&gt; (Elemento)
Especifica si se hace una comprobación adicional de progreso de <xref:System.Xml.Serialization.XmlSerializer>.  
  
 \<configuration>  
\<system.xml.serialization>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true"|"false" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|**checkDeserializeAdvances**|Especifica si se comprueba el progreso de <xref:System.Xml.Serialization.XmlSerializer>. Establezca el atributo a "verdadero" o "falso." El valor predeterminado es "true".|  
|**useLegacySerializationGeneration**|Especifica si <xref:System.Xml.Serialization.XmlSerializer> usa generación de serialización heredada, que genera ensamblados escribiendo código de C# en un archivo y después compilándolo en un ensamblado. El valor predeterminado es **false**.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[Elemento \<system.xml.serialization>](../../../docs/standard/serialization/system-xml-serialization-element.md)|Contiene la configuración para <xref:System.Xml.Serialization.XmlSerializer> y las clases <xref:System.Xml.Serialization.XmlSchemaImporter>.|  
  
## <a name="remarks"></a>Comentarios  
 De forma predeterminada, <xref:System.Xml.Serialization.XmlSerializer> proporciona una capa adicional de seguridad contra los ataques por denegación de servicio potenciales al deserializar datos que no son de confianza. Actúa de esta modo intentando detectar los bucles sin fin durante la deserialización. Si se detecta este tipo de condición, se produce una excepción con el mensaje siguiente: "Error interno: la deserialización no pudo sobrepasar el flujo subyacente".  
  
 Recibir este mensaje necesariamente no indica que un ataque por denegación de servicio está en curso. En algunas circunstancias raras, el mecanismo de detección de bucle sin fin genera un positivo falso y la excepción se producirá para un mensaje entrante legítimo. Si detecta que en la aplicación concreta esta capa adicional de protección está rechazando los mensajes legítimos, establezca el atributo **checkDeserializeAdvances** en "false".  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se establece el atributo **checkDeserializeAdvances** en "false".  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Serialization.XmlSerializer>  
 [Elemento \<system.xml.serialization>](../../../docs/standard/serialization/system-xml-serialization-element.md)  
 [Serialización SOAP y XML](../../../docs/standard/serialization/xml-and-soap-serialization.md)
