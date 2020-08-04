---
title: 'Comentarios de documentación XML: Guía de programación de C#'
description: Obtenga información sobre los comentarios de documentación XML. Puede crear documentación para el código mediante la inserción de elementos XML en campos de comentario especiales.
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
ms.openlocfilehash: fbdeb53331d9fc63d24a3322ea13863d7c0a3630
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381884"
---
# <a name="xml-documentation-comments-c-programming-guide"></a><span data-ttu-id="c2aec-104">Comentarios de documentación XML (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="c2aec-104">XML documentation comments (C# programming guide)</span></span>

<span data-ttu-id="c2aec-105">En C#, puede crear documentación para el código incluyendo elementos XML en campos de comentario especiales (se indica con barras diagonales triples) en el código fuente directamente delante del bloque de código al que hacen referencia los comentarios, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c2aec-105">In C#, you can create documentation for your code by including XML elements in special comment fields (indicated by triple slashes) in the source code directly before the code block to which the comments refer, for example.</span></span>

```csharp
/// <summary>
///  This class performs an important function.
/// </summary>
public class MyClass {}
```

<span data-ttu-id="c2aec-106">Cuando se compila con la opción [-doc](../../language-reference/compiler-options/doc-compiler-option.md), el compilador buscará todas las etiquetas XML en el código fuente y creará un archivo de documentación XML.</span><span class="sxs-lookup"><span data-stu-id="c2aec-106">When you compile with the [-doc](../../language-reference/compiler-options/doc-compiler-option.md) option, the compiler will search for all XML tags in the source code and create an XML documentation file.</span></span> <span data-ttu-id="c2aec-107">Para crear la documentación final basada en el archivo generado por el compilador, puede crear una herramienta personalizada o usar una herramienta como [DocFX](https://dotnet.github.io/docfx/) o [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="c2aec-107">To create the final documentation based on the compiler-generated file, you can create a custom tool or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

<span data-ttu-id="c2aec-108">Para hacer referencia a elementos XML (por ejemplo, la función procesa los elementos XML concretos que desea describir en un comentario de documentación XML), puede usar el mecanismo de entrecomillado estándar (`<` y `>`).</span><span class="sxs-lookup"><span data-stu-id="c2aec-108">To refer to XML elements (for example, your function processes specific XML elements that you want to describe in an XML documentation comment), you can use the standard quoting mechanism (`<` and `>`).</span></span>  <span data-ttu-id="c2aec-109">Para hacer referencia a identificadores genéricos en elementos de referencia de código (`cref`), puede usar los caracteres de escape (por ejemplo, `cref="List&lt;T&gt;"`) o llaves (`cref="List{T}"`).</span><span class="sxs-lookup"><span data-stu-id="c2aec-109">To refer to generic identifiers in code reference (`cref`) elements, you can use either the escape characters (for example, `cref="List&lt;T&gt;"`) or braces (`cref="List{T}"`).</span></span>  <span data-ttu-id="c2aec-110">Como caso especial, el compilador analiza las llaves como corchetes angulares para que la creación del comentario de documentación resulte menos complicada al hacer referencia a identificadores genéricos.</span><span class="sxs-lookup"><span data-stu-id="c2aec-110">As a special case, the compiler parses the braces as angle brackets to make the documentation comment less cumbersome to author when referring to generic identifiers.</span></span>

> [!NOTE]
> <span data-ttu-id="c2aec-111">Los comentarios de documentación XML no son metadatos; no se incluyen en el ensamblado compilado y, por tanto, no se puede obtener acceso a ellos mediante reflexión.</span><span class="sxs-lookup"><span data-stu-id="c2aec-111">The XML documentation comments are not metadata; they are not included in the compiled assembly and therefore they are not accessible through reflection.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c2aec-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c2aec-112">In this section</span></span>

- [<span data-ttu-id="c2aec-113">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="c2aec-113">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)

- [<span data-ttu-id="c2aec-114">Procesamiento del archivo XML</span><span class="sxs-lookup"><span data-stu-id="c2aec-114">Processing the XML file</span></span>](./processing-the-xml-file.md)

- [<span data-ttu-id="c2aec-115">Delimitadores para etiquetas de documentación</span><span class="sxs-lookup"><span data-stu-id="c2aec-115">Delimiters for documentation tags</span></span>](./delimiters-for-documentation-tags.md)

- [<span data-ttu-id="c2aec-116">Procedimiento para usar las características de la documentación XML</span><span class="sxs-lookup"><span data-stu-id="c2aec-116">How to use the XML documentation features</span></span>](./how-to-use-the-xml-documentation-features.md)

## <a name="related-sections"></a><span data-ttu-id="c2aec-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="c2aec-117">Related sections</span></span>

<span data-ttu-id="c2aec-118">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="c2aec-118">For more information, see:</span></span>

- [<span data-ttu-id="c2aec-119">-doc (Procesamiento de comentarios de documentación)</span><span class="sxs-lookup"><span data-stu-id="c2aec-119">-doc (Process Documentation Comments)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)

## <a name="c-language-specification"></a><span data-ttu-id="c2aec-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c2aec-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c2aec-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2aec-121">See also</span></span>

- [<span data-ttu-id="c2aec-122">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c2aec-122">C# Programming Guide</span></span>](../index.md)
