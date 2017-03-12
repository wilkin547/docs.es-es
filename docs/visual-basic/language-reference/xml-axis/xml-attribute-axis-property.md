---
title: "Propiedad de eje para atributos XML (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlPropertyAttributeAxis"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "propiedad de eje para atributos [Visual Basic]"
  - "código de Visual Basic, obtener acceso a XML"
  - "XML [Visual Basic], obtener acceso"
  - "propiedad de eje para atributos XML [Visual Basic]"
  - "eje XML [Visual Basic], atributo"
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# Propiedad de eje para atributos XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Proporciona acceso al valor de un atributo para un objeto <xref:System.Xml.Linq.XElement> o al primer elemento de una colección de objetos <xref:System.Xml.Linq.XElement>.  
  
## Sintaxis  
  
```  
  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## Elementos  
 `object`  
 Obligatorio.  Objeto <xref:System.Xml.Linq.XElement> o colección de objetos <xref:System.Xml.Linq.XElement>.  
  
 .@  
 Obligatorio.  Denota el inicio de una propiedad de eje de atributo.  
  
 \<  
 Opcional.  Denota el principio del nombre del atributo cuando `attribute` no es un identificador válido en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 `attribute`  
 Obligatorio.  Nombre del atributo para obtener acceso, con el formato \[`prefix`:\]`name`.  
  
|Parte|Descripción|  
|-----------|-----------------|  
|`prefix`|Opcional.  Prefijo de espacio de nombres XML del atributo.  Debe ser un espacio de nombres XML global definido con una instrucción `Imports`.|  
|`name`|Obligatorio.  Nombre de atributo local.  Vea [Nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Opcional.  Denota el final del nombre del atributo cuando `attribute` no es un identificador válido en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
## Valor devuelto  
 Cadena que contiene el valor de `attribute`.  Si el nombre de atributo no existe, se devuelve `Nothing`.  
  
## Comentarios  
 Puede utilizar una propiedad de eje de atributo XML para tener acceso al valor de un atributo por nombre desde un objeto <xref:System.Xml.Linq.XElement> o desde el primer elemento de una colección de objetos <xref:System.Xml.Linq.XElement>.  Puede recuperar un valor de atributo por nombre o agregar un nuevo atributo a un elemento especificando un nuevo nombre precedido por el identificador @.  
  
 Al hacer referencia al valor de un atributo XML mediante el identificador @, el valor del atributo se devuelve como cadena y no se necesita especificar explícitamente la propiedad <xref:System.Xml.Linq.XAttribute.Value%2A>.  
  
 Las reglas de nomenclatura de los atributos XML difieren de las reglas de nomenclatura de los identificadores de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]. Para tener acceso a un atributo XML que tiene un nombre que no es un identificador válido de Visual Basic, encierre el nombre entre corchetes angulares \(\< y \>\).  
  
## Espacios de nombres XML  
 El nombre en una propiedad de eje de atributo sólo puede utilizar prefijos del espacio de nombres XML declarados globalmente mediante la instrucción `Imports`.  No puede usar prefijos de espacio de nombres XML declarados localmente dentro de los literales de elemento XML.  Para obtener más información, vea [Imports \(Instrucción, Espacio de nombres XML\)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo obtener los valores de los atributos XML denominados `type` a partir de una colección de elementos XML que se denominan `phone`.  
  
 [!code-vb[VbXMLSamples#12](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-attribute-axis-prope_1.vb)]  
  
 Este código muestra el texto siguiente:  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo crear los atributos de un elemento XML tanto mediante declaración, como parte del XML, como dinámicamente agregando un atributo a una instancia de un objeto <xref:System.Xml.Linq.XElement>.  Se crea el atributo `type` mediante declaración y el atributo `owne` dinámicamente.  
  
 [!code-vb[VbXMLSamples#44](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-attribute-axis-prope_2.vb)]  
  
 Este código muestra el texto siguiente:  
  
```  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## Ejemplo  
 El ejemplo siguiente utiliza la sintaxis de corchetes angulares para obtener el valor del atributo XML denominado `number-type`, que no es un identificador válido en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 [!code-vb[VbXMLSamples#13](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-attribute-axis-prope_3.vb)]  
  
 Este código muestra el texto siguiente:  
  
 `Phone type: work`  
  
## Ejemplo  
 En el ejemplo siguiente se declara `ns` como prefijo de espacio de nombres XML.  A continuación, se usa el prefijo del espacio de nombres para crear un literal XML y obtener acceso al primer nodo secundario con el nombre completo "`ns:name`".  
  
 [!code-vb[VbXMLSamples#14](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-attribute-axis-prope_4.vb)]  
  
 Este código muestra el texto siguiente:  
  
 `Phone type: home`  
  
## Vea también  
 <xref:System.Xml.Linq.XElement>   
 [Propiedades de eje XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)