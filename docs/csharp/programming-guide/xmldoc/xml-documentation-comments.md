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
# <a name="xml-documentation-comments-c-programming-guide"></a><span data-ttu-id="0fdfc-102">Comentarios de documentación XML (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="0fdfc-102">XML Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="0fdfc-103">En Visual C# puede crear documentación para el código incluyendo elementos XML en campos de comentario especiales (se indica con barras diagonales triples) en el código fuente directamente delante del bloque de código al que hacen referencia los comentarios, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0fdfc-103">In Visual C# you can create documentation for your code by including XML elements in special comment fields (indicated by triple slashes) in the source code directly before the code block to which the comments refer, for example:</span></span>  
  
```  
/// <summary>  
///  This class performs an important function.  
/// </summary>  
public class MyClass{}  
```  
  
 <span data-ttu-id="0fdfc-104">Cuando se compila con la opción [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md), el compilador buscará todas las etiquetas XML en el código fuente y creará un archivo de documentación XML.</span><span class="sxs-lookup"><span data-stu-id="0fdfc-104">When you compile with the [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) option, the compiler will search for all XML tags in the source code and create an XML documentation file.</span></span> <span data-ttu-id="0fdfc-105">Para crear la documentación final basada en el archivo generado por el compilador, puede crear una herramienta personalizada o usar una herramienta como [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="0fdfc-105">To create the final documentation based on the compiler-generated file, you can create a custom tool or use a tool such as [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="0fdfc-106">Para hacer referencia a elementos XML (por ejemplo, la función procesa los elementos XML concretos que desea describir en un comentario de documentación XML), puede usar el mecanismo de entrecomillado estándar (`<` y `>`).</span><span class="sxs-lookup"><span data-stu-id="0fdfc-106">To refer to XML elements (for example, your function processes specific XML elements that you want to describe in an XML documentation comment), you can use the standard quoting mechanism (`<` and `>`).</span></span>  <span data-ttu-id="0fdfc-107">Para hacer referencia a identificadores genéricos en elementos de referencia de código (`cref`), puede usar los caracteres de escape (por ejemplo, `cref="List<T>"`) o llaves (`cref="List{T}"`).</span><span class="sxs-lookup"><span data-stu-id="0fdfc-107">To refer to generic identifiers in code reference (`cref`) elements, you can use either the escape characters (for example, `cref="List<T>"`) or braces (`cref="List{T}"`).</span></span>  <span data-ttu-id="0fdfc-108">Como caso especial, el compilador analiza las llaves como corchetes angulares para que la creación del comentario de documentación resulte menos complicada al hacer referencia a identificadores genéricos.</span><span class="sxs-lookup"><span data-stu-id="0fdfc-108">As a special case, the compiler parses the braces as angle brackets to make the documentation comment less cumbersome to author when referring to generic identifiers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fdfc-109">Los comentarios de documentación XML no son metadatos; no se incluyen en el ensamblado compilado y, por tanto, no se puede obtener acceso a ellos mediante reflexión.</span><span class="sxs-lookup"><span data-stu-id="0fdfc-109">The XML documentation comments are not metadata; they are not included in the compiled assembly and therefore they are not accessible through reflection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0fdfc-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0fdfc-110">In This Section</span></span>  
  
-   [<span data-ttu-id="0fdfc-111">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="0fdfc-111">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)  
  
-   [<span data-ttu-id="0fdfc-112">Procesamiento del archivo XML</span><span class="sxs-lookup"><span data-stu-id="0fdfc-112">Processing the XML File</span></span>](../../../csharp/programming-guide/xmldoc/processing-the-xml-file.md)  
  
-   [<span data-ttu-id="0fdfc-113">Delimitadores para etiquetas de documentación</span><span class="sxs-lookup"><span data-stu-id="0fdfc-113">Delimiters for Documentation Tags</span></span>](../../../csharp/programming-guide/xmldoc/delimiters-for-documentation-tags.md)  
  
-   [<span data-ttu-id="0fdfc-114">Cómo: Usar las características de la documentación XML</span><span class="sxs-lookup"><span data-stu-id="0fdfc-114">How to: Use the XML Documentation Features</span></span>](../../../csharp/programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md)  
  
## <a name="related-sections"></a><span data-ttu-id="0fdfc-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="0fdfc-115">Related Sections</span></span>  
 <span data-ttu-id="0fdfc-116">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="0fdfc-116">For more information, see:</span></span>  
  
-   <span data-ttu-id="0fdfc-117">[/doc (Process Documentation Comments)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) (/doc [Opciones del compilador de C#])</span><span class="sxs-lookup"><span data-stu-id="0fdfc-117">[/doc (Process Documentation Comments)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0fdfc-118">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="0fdfc-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0fdfc-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fdfc-119">See Also</span></span>  
 [<span data-ttu-id="0fdfc-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0fdfc-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

