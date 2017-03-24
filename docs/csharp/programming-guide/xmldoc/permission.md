---
title: "&lt;permission&gt; (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "permission"
  - "<permission>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<permission> (etiqueta XML) [C#]"
  - "permission (etiqueta XML) [C#]"
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# &lt;permission&gt; (Gu&#237;a de programaci&#243;n de C#)
## Sintaxis  
  
```  
<permission cref="member">description</permission>  
```  
  
#### Parámetros  
 cref \= "`member`"  
 Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.  El compilador comprueba si el elemento de código dado existe y convierte `member` al nombre de elemento canónico en el resultado XML. *member* debe aparecer entre comillas dobles \(" "\).  
  
 Para obtener información sobre cómo crear una referencia de tipo cref a un tipo genérico, vea [\<see\>](../../../csharp/programming-guide/xmldoc/see.md).  
  
 `description`  
 Descripción del acceso al miembro.  
  
## Comentarios  
 La etiqueta \<permission\> permite documentar el acceso de un miembro.  La clase <xref:System.Security.PermissionSet> permite especificar el acceso a un miembro.  
  
 Compile con el parámetro [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.  
  
## Ejemplo  
 [!code-cs[csProgGuideDocComments#8](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/permission_1.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)