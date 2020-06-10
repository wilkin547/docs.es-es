---
title: <summary> - Guía de programación de C#
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: e1a8c9d61e61eae7ba6bf7f0c1b9d2a8dc8a4171
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287212"
---
# <a name="summary-c-programming-guide"></a><span data-ttu-id="a75a6-102">\<summary> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="a75a6-102">\<summary> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="a75a6-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a75a6-103">Syntax</span></span>

```xml
<summary>description</summary>
```

## <a name="parameters"></a><span data-ttu-id="a75a6-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a75a6-104">Parameters</span></span>

- `description`

  <span data-ttu-id="a75a6-105">Resumen del objeto.</span><span class="sxs-lookup"><span data-stu-id="a75a6-105">A summary of the object.</span></span>

## <a name="remarks"></a><span data-ttu-id="a75a6-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a75a6-106">Remarks</span></span>

<span data-ttu-id="a75a6-107">La etiqueta `<summary>` debe usarse para describir un tipo o un miembro de tipo.</span><span class="sxs-lookup"><span data-stu-id="a75a6-107">The `<summary>` tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="a75a6-108">Use [\<remarks>](./remarks.md) para agregar información adicional a una descripción de tipo.</span><span class="sxs-lookup"><span data-stu-id="a75a6-108">Use [\<remarks>](./remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="a75a6-109">Use el [atributo cref](./cref-attribute.md) para permitir que herramientas de documentación como [DocFX](https://dotnet.github.io/docfx/) y [Sandcastle](https://github.com/EWSoftware/SHFB) creen hipervínculos internos a las páginas de documentación de los elementos de código.</span><span class="sxs-lookup"><span data-stu-id="a75a6-109">Use the [cref Attribute](./cref-attribute.md) to enable documentation tools such as [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>

<span data-ttu-id="a75a6-110">El texto de la etiqueta `<summary>` es la única fuente de información sobre el tipo en IntelliSense y también se muestra en la ventana Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="a75a6-110">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>

<span data-ttu-id="a75a6-111">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="a75a6-111">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span> <span data-ttu-id="a75a6-112">Para crear la documentación final basada en el archivo generado por el compilador, puede crear una herramienta personalizada o usar una herramienta como [DocFX](https://dotnet.github.io/docfx/) o [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="a75a6-112">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

## <a name="example"></a><span data-ttu-id="a75a6-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a75a6-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

<span data-ttu-id="a75a6-114">En el ejemplo anterior se genera el siguiente archivo XML.</span><span class="sxs-lookup"><span data-stu-id="a75a6-114">The previous example produces the following XML file.</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>YourNamespace</name>
    </assembly>
    <members>
        <member name="T:TestClass">
            text for class TestClass
        </member>
        <member name="M:TestClass.DoWork(System.Int32)">
            <summary>DoWork is a method in the TestClass class.
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>
            <seealso cref="M:TestClass.Main"/>
            </summary>
        </member>
        <member name="M:TestClass.Main">
            text for Main
        </member>
    </members>
</doc>
```

## <a name="example"></a><span data-ttu-id="a75a6-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a75a6-115">Example</span></span>

<span data-ttu-id="a75a6-116">En el ejemplo siguiente se muestra cómo hacer una referencia `cref` a un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="a75a6-116">The following example shows how to make a `cref` reference to a generic type.</span></span>

[!code-csharp[csProgGuideDocComments#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#11)]

<span data-ttu-id="a75a6-117">En el ejemplo anterior se genera el siguiente archivo XML.</span><span class="sxs-lookup"><span data-stu-id="a75a6-117">The previous example produces the following XML file.</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>CRefTest</name>
    </assembly>
    <members>
        <member name="T:A">
            <summary cref="T:C`1">
            </summary>
        </member>
        <member name="T:B">
            <summary cref="T:C`1">
            </summary>
        </member>
        <member name="T:C`1">
            <summary cref="T:A">
            </summary>
            <typeparam name="T"></typeparam>
        </member>
    </members>
</doc>
```

## <a name="see-also"></a><span data-ttu-id="a75a6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a75a6-118">See also</span></span>

- [<span data-ttu-id="a75a6-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a75a6-119">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="a75a6-120">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="a75a6-120">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
