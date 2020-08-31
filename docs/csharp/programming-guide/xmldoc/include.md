---
title: <include> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML. <include> . Esta etiqueta le permite hacer referencia a comentarios de otro archivo que describen los tipos y miembros en el código fuente.
ms.date: 07/20/2015
f1_keywords:
- include
- <include>
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
ms.openlocfilehash: d2de8fea17850685668766bc4ec6e64b1be77cce
ms.sourcegitcommit: 2560a355c76b0a04cba0d34da870df9ad94ceca3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2020
ms.locfileid: "89053196"
---
# <a name="include-c-programming-guide"></a><span data-ttu-id="47090-105">\<include> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="47090-105">\<include> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="47090-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47090-106">Syntax</span></span>

```xml
<include file='filename' path='tagpath[@name="id"]' />
```

## <a name="parameters"></a><span data-ttu-id="47090-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47090-107">Parameters</span></span>

- `filename`

  <span data-ttu-id="47090-108">El nombre del archivo XML que contiene la documentación.</span><span class="sxs-lookup"><span data-stu-id="47090-108">The name of the XML file containing the documentation.</span></span> <span data-ttu-id="47090-109">El nombre de archivo se puede calificar con una ruta de acceso relativa al archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="47090-109">The file name can be qualified with a path relative to the source code file.</span></span> <span data-ttu-id="47090-110">Incluya `filename` entre comillas simples (' ').</span><span class="sxs-lookup"><span data-stu-id="47090-110">Enclose `filename` in single quotation marks (' ').</span></span>

- `tagpath`

  <span data-ttu-id="47090-111">La ruta de acceso de las etiquetas de `filename` que conduce a la etiqueta `name`.</span><span class="sxs-lookup"><span data-stu-id="47090-111">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="47090-112">Incluya la ruta de acceso entre comillas simples (' ').</span><span class="sxs-lookup"><span data-stu-id="47090-112">Enclose the path in single quotation marks (' ').</span></span>

- `name`

  <span data-ttu-id="47090-113">El especificador de nombre en la etiqueta que precede a los comentarios; `name` tendrá un `id`.</span><span class="sxs-lookup"><span data-stu-id="47090-113">The name specifier in the tag that precedes the comments; `name` will have an `id`.</span></span>

- `id`

  <span data-ttu-id="47090-114">El identificador de la etiqueta que precede a los comentarios.</span><span class="sxs-lookup"><span data-stu-id="47090-114">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="47090-115">Ponga el identificador entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="47090-115">Enclose the ID in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="47090-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="47090-116">Remarks</span></span>

<span data-ttu-id="47090-117">La etiqueta `<include>` le permite hacer referencia a comentarios colocados en otro archivo que describen los tipos y miembros en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="47090-117">The `<include>` tag lets you refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="47090-118">Esto es una alternativa a colocar los comentarios de documentación directamente en el archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="47090-118">This is an alternative to placing documentation comments directly in your source code file.</span></span> <span data-ttu-id="47090-119">Al colocar la documentación en un archivo independiente, puede aplicar el control de código fuente a la documentación de forma independiente desde el código fuente.</span><span class="sxs-lookup"><span data-stu-id="47090-119">By putting the documentation in a separate file, you can apply source control to the documentation separately from the source code.</span></span> <span data-ttu-id="47090-120">Una persona puede tener el archivo de código fuente extraído del repositorio y otra persona puede tener el archivo de documentación extraído del repositorio.</span><span class="sxs-lookup"><span data-stu-id="47090-120">One person can have the source code file checked out and someone else can have the documentation file checked out.</span></span>

<span data-ttu-id="47090-121">La etiqueta `<include>` usa la sintaxis de XPath de XML.</span><span class="sxs-lookup"><span data-stu-id="47090-121">The `<include>` tag uses the XML XPath syntax.</span></span> <span data-ttu-id="47090-122">Consulte la documentación de XPath para ver formas de personalizar el uso de `<include>`.</span><span class="sxs-lookup"><span data-stu-id="47090-122">Refer to XPath documentation for ways to customize your `<include>` use.</span></span>

## <a name="example"></a><span data-ttu-id="47090-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47090-123">Example</span></span>

<span data-ttu-id="47090-124">Este es un ejemplo de múltiples archivos.</span><span class="sxs-lookup"><span data-stu-id="47090-124">This is a multifile example.</span></span> <span data-ttu-id="47090-125">El siguiente es el primer archivo, que usa `<include>`.</span><span class="sxs-lookup"><span data-stu-id="47090-125">The following is the first file, which uses `<include>`.</span></span>

[!code-csharp[csProgGuideDocComments#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#5)]

<span data-ttu-id="47090-126">El segundo archivo, *xml_include_tag.doc*, contiene los comentarios de documentación siguientes.</span><span class="sxs-lookup"><span data-stu-id="47090-126">The second file, *xml_include_tag.doc*, contains the following documentation comments.</span></span>

```xml
<MyDocs>

<MyMembers name="test">
<summary>
The summary for this type.
</summary>
</MyMembers>

<MyMembers name="test2">
<summary>
The summary for this other type.
</summary>
</MyMembers>

</MyDocs>
```

## <a name="program-output"></a><span data-ttu-id="47090-127">Salida del programa</span><span class="sxs-lookup"><span data-stu-id="47090-127">Program output</span></span>

<span data-ttu-id="47090-128">El siguiente resultado se genera al compilar las clases Test y Test2 con la siguiente línea de comandos: `-doc:DocFileName.xml.` En Visual Studio, especifica la opción de comentarios de documentación XML en el panel Compilar del Diseñador de proyectos.</span><span class="sxs-lookup"><span data-stu-id="47090-128">The following output is generated when you compile the Test and Test2 classes with the following command line: `-doc:DocFileName.xml.` In Visual Studio, you specify the XML doc comments option in the Build pane of the Project Designer.</span></span> <span data-ttu-id="47090-129">Cuando el compilador de C# ve la etiqueta `<include>`, busca los comentarios de documentación en *xml_include_tag.doc* en lugar del archivo de código fuente actual.</span><span class="sxs-lookup"><span data-stu-id="47090-129">When the C# compiler sees the `<include>` tag, it searches for documentation comments in *xml_include_tag.doc* instead of the current source file.</span></span> <span data-ttu-id="47090-130">Después, el compilador genera *DocFileName.xml* y este es el archivo que usan las herramientas de documentación como [Sandcastle](https://github.com/EWSoftware/SHFB) para generar la documentación final.</span><span class="sxs-lookup"><span data-stu-id="47090-130">The compiler then generates *DocFileName.xml*, and this is the file that is consumed by documentation tools such as [Sandcastle](https://github.com/EWSoftware/SHFB) to produce the final documentation.</span></span>  
  
```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>xml_include_tag</name>
    </assembly>
    <members>
        <member name="T:Test">
            <summary>
The summary for this type.
</summary>
        </member>
        <member name="T:Test2">
            <summary>
The summary for this other type.
</summary>
        </member>
    </members>
</doc>
```  
  
## <a name="see-also"></a><span data-ttu-id="47090-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="47090-131">See also</span></span>

- [<span data-ttu-id="47090-132">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="47090-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="47090-133">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="47090-133">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
