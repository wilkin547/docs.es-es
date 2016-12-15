---
title: "Comentarios de documentaci&#243;n XML (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cs.xml"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, comentarios en código XML"
  - "archivos de código fuente de C#"
  - "comentarios [C#], XML"
  - "comentarios de documentación [C#]"
  - "XML [C#], comentarios en código"
  - "comentarios de documentación XML [C#]"
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Comentarios de documentaci&#243;n XML (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En Visual C\# puede crear documentación para el código incluyendo elementos XML en campos de comentario especiales \(se indica con barras diagonales triples\) en el código fuente directamente delante del bloque de código al que hacen referencia los comentarios, por ejemplo:  
  
```  
/// <summary>  
///  This class performs an important function.  
/// </summary>  
public class MyClass{}  
```  
  
 Cuando se compila con la opción [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md), el compilador buscará todas las etiquetas XML en el código fuente y creará un archivo de documentación XML.  Para crear la documentación final basada en el archivo generado por el compilador, puede crear una herramienta personalizada o usar una herramienta como [Sandcastle](http://go.microsoft.com/fwlink/?LinkId=124061).  
  
 Para hacer referencia a elementos XML \(por ejemplo, la función procesa los elementos XML concretos que desea describir en un comentario de documentación XML\), puede usar el mecanismo de entrecomillado estándar \(`<` y `>`\).  Para hacer referencia a identificadores genéricos en elementos de referencia de código \(`cref`\), puede usar los caracteres de escape \(por ejemplo, `cref=”List<T>”`\) o llaves \(`cref=”List{T}”`\).  Como caso especial, el compilador analiza las llaves como corchetes angulares para que la creación del comentario de documentación resulte menos complicada al hacer referencia a identificadores genéricos.  
  
> [!NOTE]
>  Los comentarios de documentación XML no son metadatos; no se incluyen en el ensamblado compilado y, por tanto, no se puede obtener acceso a ellos mediante reflexión.  
  
## En esta sección  
  
-   [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)  
  
-   [Procesar el archivo XML](../../../csharp/programming-guide/xmldoc/processing-the-xml-file.md)  
  
-   [Delimitadores para etiquetas de documentación](../../../csharp/programming-guide/xmldoc/delimiters-for-documentation-tags.md)  
  
-   [Cómo: Usar las características de la documentación XML](../../../csharp/programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md)  
  
## Secciones relacionadas  
 Para obtener más información, vea:  
  
-   [\/doc \(procesar comentarios de documentación\)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)