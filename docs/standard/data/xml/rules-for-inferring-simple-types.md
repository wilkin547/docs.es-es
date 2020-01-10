---
title: Reglas para deducir tipos simples
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 394624d6-4da0-430a-8a88-46efe40f14de
ms.openlocfilehash: 17429e77f7764873e607a8feaa62da1cc6e014a4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710237"
---
# <a name="rules-for-inferring-simple-types"></a>Reglas para deducir tipos simples
Describe cómo la clase <xref:System.Xml.Schema.XmlSchemaInference> deduce el tipo de datos para atributos y elementos.  
  
 La clase <xref:System.Xml.Schema.XmlSchemaInference> deduce el tipo de datos para atributos y elementos como tipos simples. Esta sección describe los tipos deducidos potenciales, cómo se reconcilian varios valores diferentes en un tipo único y cómo se controlan los atributos de definición de esquema `xsi`.  
  
## <a name="inferred-types"></a>Tipos deducidos  
 La clase <xref:System.Xml.Schema.XmlSchemaInference> deduce valores de elemento y atributo como tipos simples e incluye un atributo de tipo en el esquema resultante. Todos los tipos deducidos son tipos simples. No se incluyen tipos ni facetas base como parte del esquema resultante.  
  
 Los valores se examinan individualmente a medida que se encuentran en el documento XML. El tipo se deduce para un valor en el momento que se examina. Si un tipo ha sido deducido para un atributo o elemento y se encuentra un valor para el atributo o elemento que no coincide con el tipo deducido actual, la clase <xref:System.Xml.Schema.XmlSchemaInference> promueve el tipo de cada conjunto de reglas. Estas reglas se discuten en la sección Promoción de tipos, más adelante en este tema.  
  
 La siguiente tabla enumera los tipos deducidos posibles para el esquema resultante.  
  
|Tipo simple|Descripción|  
|-----------------|-----------------|  
|booleano|True, false, 0, 1.|  
|byte|Enteros en un intervalo de -128 a 127.|  
|unsignedByte|Enteros en un intervalo de 0 a 255.|  
|corto|Enteros en un intervalo de –32768 a 32767.|  
|unsignedShort|Enteros en un intervalo de 0 a 65535.|  
|int|Enteros en un intervalo de –2147483648 a 2147483647.|  
|unsignedInt|Enteros en un intervalo de 0 a 4294967295.|  
|long|Enteros en un intervalo de –9223372036854775808 a 9223372036854775807.|  
|unsignedLong|Enteros en un intervalo de 0 a 18446744073709551615.|  
|enteros|Un número finito de dígitos posiblemente prefijado con "-".|  
|decimal|Valores numéricos que contienen dígitos de precisión del 0 a 28.|  
|flotante|Decimales opcionalmente seguidos por "E" o "e" seguidos de un valor entero representando el exponente. Los valores decimales pueden estar en el intervalo de -16777216 a 16777216. Los valores del exponente pueden estar en el intervalo de –149 a 104.<br /><br /> Float permite que valores especiales representen valores infinitos y no numéricos. Los valores especiales para float son: 0, -0, INF, - INF, NaN.|  
|doble|Lo mismo que float excepto que los valores decimales pueden estar en el intervalo de -9007199254740992 a 9007199254740992, y los valores del exponente pueden estar en el intervalo de –1075 a 970.<br /><br /> Double permite que valores especiales representen valores infinitos y no numéricos. Los valores especiales para float son: 0, -0, INF, - INF, NaN.|  
|duration|El formato de duración W3C.|  
|dateTime|El formato dateTime W3C.|  
|tiempo|El formato time W3C.|  
|date|Los valores de años están restringidos de 0001 a 9999.|  
|gYearMonth|El formato W3C de mes y año gregoriano.|  
|cadena|Uno o más caracteres Unicode.|  
  
## <a name="type-promotion"></a>Promoción de tipos  
 La clase <xref:System.Xml.Schema.XmlSchemaInference> examina los valores de atributo y elemento uno por uno. A medida que se encuentran valores, se deduce el tipo sin signo más restrictivo. Si un tipo ha sido deducido para un atributo o elemento y se encuentra un nuevo valor que no coincide con el tipo deducido actual, el tipo deducido se promueve a un nuevo tipo que se aplica al tipo deducido actualmente y al nuevo valor. La clase <xref:System.Xml.Schema.XmlSchemaInference> considera valores anteriores cuando promueve el tipo deducido.  
  
 Por ejemplo, considere los siguientes fragmentos XML de dos documentos XML:  
  
 `<MyElement1 attr1="12" />`  
  
 `<MyElement1 attr1="52344" />`  
  
 Cuando se encuentra el primer valor `attr1`, el tipo de `attr1` se deduce como `unsignedByte` basado en el valor `12`. Cuando se encuentra el segundo `attr1`, el tipo se promueve a `unsignedShort` basado en el tipo deducido actualmente de `unsignedByte` y el valor actual `52344`.  
  
 A continuación, considere el siguiente XML de dos documentos XML:  
  
 `<MyElement2 attr2="0" />`  
  
 `<MyElement2 attr2="true" />`  
  
 Cuando se encuentra el primer valor `attr2`, el tipo de `attr2` se deduce como `unsignedByte` basado en el valor `0`. Cuando se encuentra el segundo `attr2`, el tipo se promueve a `string` basado en el tipo deducido actualmente de `unsignedByte` y el valor actual `true` ya que la clase <xref:System.Xml.Schema.XmlSchemaInference> tiene en cuenta valores anteriores cuando promueve el tipo deducido. No obstante, si ambas instancias de `attr2` se encuentran en el mismo documento XML y no en dos documentos XML diferentes, tal como se ilustra arriba, `attr2` hubiese sido deducido como `boolean`.  
  
### <a name="ignored-attributes-from-the-httpswwww3org2001xmlschema-instance-namespace"></a>Atributos omitidos del espacio de nombres <https://www.w3.org/2001/XMLSchema-instance>

Los siguientes son atributos que definen el esquema que son omitidos durante la deducción del sistema.  
  
|Attribute|Descripción|  
|---------------|-----------------|  
|`xsi:type`|Si un elemento se encuentra con tipo `xsi:type` especificado, el `xsi:type` es omitido.|  
|`xsi:nil`|Si se encuentra un elemento con un atributo `xsi:nil`, su declaración de elemento en el esquema deducido tiene el valor de `nillable="true"`. Un elemento con un atributo `xsi:nil` establecido en `true` no puede tener elementos secundarios.|  
|`xsi:schemaLocation`|Si se encuentra `xsi:schemaLocation`, se omite.|  
|`xsi:noNamespaceSchemaLocation`|Si se encuentra `xsi:noNamespaceSchemaLocation`, se omite.|  
  
## <a name="see-also"></a>Vea también

- [Modelo de objetos de esquema XML (SOM)](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)
- [Deducción de esquemas a partir de documentos XML](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)
- [Reglas para deducir los tipos de nodo de esquema y estructura](../../../../docs/standard/data/xml/rules-for-inferring-schema-node-types-and-structure.md)
