---
title: <xmlSerializer> (Elemento)
description: El elemento <xmlSerializer> especifica si se realiza una comprobación adicional del progreso de XmlSerializer.
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: 6f368880c97a21dc3e9593ecb2319d265a1b8932
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676496"
---
# <a name="xmlserializer-element"></a>\<xmlSerializer> (Elemento)

Especifica si se hace una comprobación adicional de progreso de <xref:System.Xml.Serialization.XmlSerializer>.  
  
 \<configuration>  
\<system.xml.serialization>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true|false" />  
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
|[Elemento \<system.xml.serialization>](system-xml-serialization-element.md)|Contiene la configuración para <xref:System.Xml.Serialization.XmlSerializer> y las clases <xref:System.Xml.Serialization.XmlSchemaImporter>.|  
  
## <a name="remarks"></a>Comentarios  

 De forma predeterminada, <xref:System.Xml.Serialization.XmlSerializer> proporciona una capa adicional de seguridad contra los ataques por denegación de servicio potenciales al deserializar datos que no son de confianza. Actúa de esta modo intentando detectar los bucles sin fin durante la deserialización. Si se detecta este tipo de condición, se inicia una excepción con el siguiente mensaje: "Error interno: la deserialización no ha podido avanzar sobre la secuencia subyacente".  
  
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

- <xref:System.Xml.Serialization.XmlSerializer>
- [Elemento \<system.xml.serialization>](system-xml-serialization-element.md)
- [Serialización SOAP y XML](xml-and-soap-serialization.md)
