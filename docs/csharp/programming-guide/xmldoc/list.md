---
title: "&lt;list&gt; (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "list"
  - "<list>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<item> (etiqueta XML) [C#]"
  - "<list> (etiqueta XML) [C#]"
  - "<listheader> (etiqueta XML) [C#]"
  - "item (etiqueta XML) [C#]"
  - "list (etiqueta XML) [C#]"
  - "listheader (etiqueta XML) [C#]"
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# &lt;list&gt; (Gu&#237;a de programaci&#243;n de C#)
## Sintaxis  
  
```  
<list type="bullet" | "number" | "table">  
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
 `term`  
 Término que se define en `description`.  
  
 `description`  
 Elemento de una lista numerada o con viñetas, o definición de un `term`.  
  
## Comentarios  
 El bloque \<listheader\> se utiliza para definir la fila de encabezado de una tabla o de una lista de definiciones.  Cuando se define una tabla, sólo es necesario suministrar una entrada para un término en el encabezado.  
  
 Cada elemento de la lista se especifica con un bloque \<item\>.  Cuando se crea una lista de definiciones, se deberán especificar tanto `term` como `description`.  Sin embargo, para una tabla, lista con viñetas o lista numerada, sólo es necesario suministrar una entrada para `description`.  
  
 Una lista o una tabla pueden tener tantos bloques \<item\> como sean necesarios.  
  
 Compile con el parámetro [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.  
  
## Ejemplo  
 [!code-cs[csProgGuideDocComments#6](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/list_1.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)