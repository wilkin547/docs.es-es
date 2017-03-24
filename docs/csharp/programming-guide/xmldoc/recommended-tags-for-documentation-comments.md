---
title: "Etiquetas recomendadas para comentarios de documentaci&#243;n (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "XML [C#], etiquetas"
  - "documentación XML [C#], etiquetas"
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# Etiquetas recomendadas para comentarios de documentaci&#243;n (Gu&#237;a de programaci&#243;n de C#)
El compilador de C\# procesa los comentarios de documentación del código y les da formato de código XML en un archivo cuyo nombre se especifica en la opción de la línea de comandos **\/doc**.  Para crear la documentación final basada en el archivo compilador\- generado, puede crear una herramienta personalizada, o utilice una herramienta como. [Castillo de arena](http://shfb.codeplex.com/)  
  
 Las etiquetas se procesan sobre construcciones de código, tales como tipos y miembros de tipos.  
  
> [!NOTE]
>  Los comentarios de documentación no se pueden aplicar a un espacio de nombres.  
  
 El compilador procesará cualquier etiqueta válida en XML.  Las siguientes etiquetas proporcionan funcionalidad de uso general en la documentación de usuario.  
  
## Etiquetas  
  
||||  
|-|-|-|  
|[\<c\>](../../../csharp/programming-guide/xmldoc/code-inline.md)|[\<para\>](../../../csharp/programming-guide/xmldoc/para.md)|[\<see\>](../../../csharp/programming-guide/xmldoc/see.md)\*|  
|[\<code\>](../../../csharp/programming-guide/xmldoc/code.md)|[\<param\>](../../../csharp/programming-guide/xmldoc/param.md)\*|[\<seealso\>](../../../csharp/programming-guide/xmldoc/seealso.md)\*|  
|[\<example\>](../../../csharp/programming-guide/xmldoc/example.md)|[\<paramref\>](../../../csharp/programming-guide/xmldoc/paramref.md)|[\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md)|  
|[\<exception\>](../../../csharp/programming-guide/xmldoc/exception.md)\*|[\<permission\>](../../../csharp/programming-guide/xmldoc/permission.md)\*|[\<typeparam\>](../../../csharp/programming-guide/xmldoc/typeparam.md)\*|  
|[\<include\>](../../../csharp/programming-guide/xmldoc/include.md)\*|[\<remarks\>](../../../csharp/programming-guide/xmldoc/remarks.md)|[\<typeparamref\>](../../../csharp/programming-guide/xmldoc/typeparamref.md)|  
|[\<list\>](../../../csharp/programming-guide/xmldoc/list.md)|[\<returns\>](../../../csharp/programming-guide/xmldoc/returns.md)|[\<value\>](../../../csharp/programming-guide/xmldoc/value.md)|  
  
 \(\* indica que el compilador comprueba la sintaxis.\)  
  
 Si desea que aparezcan corchetes angulares en el texto de un comentario de documentación, utilice `<` y `>`, como se muestra en el ejemplo siguiente.  
  
```xml  
/// <summary cref="C < T >">  
/// </summary>  
```  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [\/doc \(Process Documentation Comments\)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)   
 [Comentarios de documentación XML](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)