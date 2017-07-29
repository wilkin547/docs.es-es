---
title: "Comentarios de documentación XML (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.xml
dev_langs:
- CSharp
helpviewer_keywords:
- XML [C#], code comments
- comments [C#], XML
- documentation comments [C#]
- C# source code files
- C# language, XML code comments
- XML documentation comments [C#]
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 408b2de29b15158499067da05dbb2f89eb1ba22f
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="xml-documentation-comments-c-programming-guide"></a>Comentarios de documentación XML (Guía de programación de C#)
En Visual C# puede crear documentación para el código incluyendo elementos XML en campos de comentario especiales (se indica con barras diagonales triples) en el código fuente directamente delante del bloque de código al que hacen referencia los comentarios, por ejemplo:  
  
```  
/// <summary>  
///  This class performs an important function.  
/// </summary>  
public class MyClass{}  
```  
  
 Cuando se compila con la opción [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md), el compilador buscará todas las etiquetas XML en el código fuente y creará un archivo de documentación XML. Para crear la documentación final basada en el archivo generado por el compilador, puede crear una herramienta personalizada o usar una herramienta como [Sandcastle](https://github.com/EWSoftware/SHFB).  
  
 Para hacer referencia a elementos XML (por ejemplo, la función procesa los elementos XML concretos que desea describir en un comentario de documentación XML), puede usar el mecanismo de entrecomillado estándar (`<` y `>`).  Para hacer referencia a identificadores genéricos en elementos de referencia de código (`cref`), puede usar los caracteres de escape (por ejemplo, `cref="List<T>"`) o llaves (`cref="List{T}"`).  Como caso especial, el compilador analiza las llaves como corchetes angulares para que la creación del comentario de documentación resulte menos complicada al hacer referencia a identificadores genéricos.  
  
> [!NOTE]
>  Los comentarios de documentación XML no son metadatos; no se incluyen en el ensamblado compilado y, por tanto, no se puede obtener acceso a ellos mediante reflexión.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)  
  
-   [Procesamiento del archivo XML](../../../csharp/programming-guide/xmldoc/processing-the-xml-file.md)  
  
-   [Delimitadores para etiquetas de documentación](../../../csharp/programming-guide/xmldoc/delimiters-for-documentation-tags.md)  
  
-   [Cómo: Usar las características de la documentación XML](../../../csharp/programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md)  
  
## <a name="related-sections"></a>Secciones relacionadas  
 Para obtener más información, consulte:  
  
-   [/doc (Process Documentation Comments)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) (/doc [Opciones del compilador de C#])  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)

