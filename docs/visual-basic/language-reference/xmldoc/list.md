---
title: "&lt;list&gt; (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "<description> (etiqueta XML)"
  - "<item> (etiqueta XML)"
  - "<list> (etiqueta XML)"
  - "<listheader> (etiqueta XML)"
  - "<term> (etiqueta XML)"
  - "description (etiqueta XML)"
  - "item (etiqueta XML)"
  - "list (etiqueta XML)"
  - "listheader (etiqueta XML)"
  - "term (etiqueta XML)"
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# &lt;list&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Define una lista o una tabla.  
  
## Sintaxis  
  
```  
<list type="type">  
   <listheader>  
      <term>term</term>  
      <description>description</description>  
   </listheader>  
   <item>  
      <term>term</term>  
      <description>description</description>  
   </item>  
</list>  
```  
  
#### Parámetros  
 `type`  
 El tipo de la lista.  Debe ser "bullet" para una lista con viñetas, "number" para una lista numerada o "table" para una tabla de dos columnas.  
  
 `term`  
 Sólo se usa cuando `type` es "table". El término que se define, que lo hace en la etiqueta descripción.  
  
 `description`  
 Cuando `type` es "bullet" o "number", `description` es un elemento de la lista. Cuando `type` es "table", `description` es la definición de `term`.  
  
## Comentarios  
 El bloque `<listheader>` define el encabezado de una tabla o de una lista de definiciones.  Cuando se define una tabla, se debe suministrar únicamente una entrada para `term` en el encabezado.  
  
 Cada elemento de la lista se especifica con un bloque `<item>`.  Cuando se crea una lista de definiciones, se debe especificar tanto `term` como `description`.  Sin embargo, para una tabla, lista con viñetas o lista numerada, se debe suministrar únicamente una entrada para `description`.  
  
 Una lista o una tabla pueden tener tantos bloques `<item>` como sean necesarios.  
  
 Compile con [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.  
  
## Ejemplo  
 Este ejemplo utiliza la etiqueta `<list>` para definir una lista con viñetas en la sección de comentarios.  
  
 [!code-vb[VbVbcnXmlDocComments#5](../../../visual-basic/language-reference/xmldoc/codesnippet/visualbasic/list_1.vb)]  
  
## Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)