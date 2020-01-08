---
title: 'Comentarios de documentación XML: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.xml
helpviewer_keywords:
- XML [C#], code comments
- comments [C#], XML
- documentation comments [C#]
- C# source code files
- C# language, XML code comments
- XML documentation comments [C#]
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
ms.openlocfilehash: 08357017a29f05c11e316e037497b1ee24d06eff
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634981"
---
# <a name="xml-documentation-comments-c-programming-guide"></a><span data-ttu-id="8c5c8-102">Comentarios de documentación XML (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="8c5c8-102">XML Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="8c5c8-103">En Visual C# puede crear documentación para el código incluyendo elementos XML en campos de comentario especiales (se indica con barras diagonales triples) en el código fuente directamente delante del bloque de código al que hacen referencia los comentarios, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8c5c8-103">In Visual C# you can create documentation for your code by including XML elements in special comment fields (indicated by triple slashes) in the source code directly before the code block to which the comments refer, for example:</span></span>  
  
```csharp  
/// <summary>  
///  This class performs an important function.  
/// </summary>  
public class MyClass {}  
```  
  
 <span data-ttu-id="8c5c8-104">Cuando se compila con la opción [-doc](../../language-reference/compiler-options/doc-compiler-option.md), el compilador buscará todas las etiquetas XML en el código fuente y creará un archivo de documentación XML.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-104">When you compile with the [-doc](../../language-reference/compiler-options/doc-compiler-option.md) option, the compiler will search for all XML tags in the source code and create an XML documentation file.</span></span> <span data-ttu-id="8c5c8-105">Para crear la documentación final basada en el archivo generado por el compilador, puede crear una herramienta personalizada o usar una herramienta como [DocFX](https://dotnet.github.io/docfx/) o [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="8c5c8-105">To create the final documentation based on the compiler-generated file, you can create a custom tool or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="8c5c8-106">Para hacer referencia a elementos XML (por ejemplo, la función procesa los elementos XML concretos que desea describir en un comentario de documentación XML), puede usar el mecanismo de entrecomillado estándar (`<` y `>`).</span><span class="sxs-lookup"><span data-stu-id="8c5c8-106">To refer to XML elements (for example, your function processes specific XML elements that you want to describe in an XML documentation comment), you can use the standard quoting mechanism (`<` and `>`).</span></span>  <span data-ttu-id="8c5c8-107">Para hacer referencia a identificadores genéricos en elementos de referencia de código (`cref`), puede usar los caracteres de escape (por ejemplo, `cref="List&lt;T&gt;"`) o llaves (`cref="List{T}"`).</span><span class="sxs-lookup"><span data-stu-id="8c5c8-107">To refer to generic identifiers in code reference (`cref`) elements, you can use either the escape characters (for example, `cref="List&lt;T&gt;"`) or braces (`cref="List{T}"`).</span></span>  <span data-ttu-id="8c5c8-108">Como caso especial, el compilador analiza las llaves como corchetes angulares para que la creación del comentario de documentación resulte menos complicada al hacer referencia a identificadores genéricos.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-108">As a special case, the compiler parses the braces as angle brackets to make the documentation comment less cumbersome to author when referring to generic identifiers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8c5c8-109">Los comentarios de documentación XML no son metadatos; no se incluyen en el ensamblado compilado y, por tanto, no se puede obtener acceso a ellos mediante reflexión.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-109">The XML documentation comments are not metadata; they are not included in the compiled assembly and therefore they are not accessible through reflection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8c5c8-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8c5c8-110">In This Section</span></span>  
  
- [<span data-ttu-id="8c5c8-111">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="8c5c8-111">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)  
  
- [<span data-ttu-id="8c5c8-112">Procesamiento del archivo XML</span><span class="sxs-lookup"><span data-stu-id="8c5c8-112">Processing the XML File</span></span>](./processing-the-xml-file.md)  
  
- [<span data-ttu-id="8c5c8-113">Delimitadores para etiquetas de documentación</span><span class="sxs-lookup"><span data-stu-id="8c5c8-113">Delimiters for Documentation Tags</span></span>](./delimiters-for-documentation-tags.md)  
  
- [<span data-ttu-id="8c5c8-114">Procedimiento para usar las características de la documentación XML</span><span class="sxs-lookup"><span data-stu-id="8c5c8-114">How to use the XML documentation features</span></span>](./how-to-use-the-xml-documentation-features.md)
  
## <a name="related-sections"></a><span data-ttu-id="8c5c8-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="8c5c8-115">Related Sections</span></span>  
 <span data-ttu-id="8c5c8-116">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="8c5c8-116">For more information, see:</span></span>  
  
- [<span data-ttu-id="8c5c8-117">-doc (Procesamiento de comentarios de documentación)</span><span class="sxs-lookup"><span data-stu-id="8c5c8-117">-doc (Process Documentation Comments)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="8c5c8-118">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="8c5c8-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8c5c8-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c5c8-119">See also</span></span>

- [<span data-ttu-id="8c5c8-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8c5c8-120">C# Programming Guide</span></span>](../index.md)
