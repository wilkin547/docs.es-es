---
title: <include> - Guía de programación de C#
ms.date: 07/20/2015
f1_keywords:
- include
- <include>
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
ms.openlocfilehash: 125ab9476507babae9a707a6c42d24adda632267
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75696563"
---
# <a name="include-c-programming-guide"></a><span data-ttu-id="3ad1d-102">\<include> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="3ad1d-102">\<include> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="3ad1d-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ad1d-103">Syntax</span></span>  
  
```xml  
<include file='filename' path='tagpath[@name="id"]' />  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ad1d-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3ad1d-104">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="3ad1d-105">El nombre del archivo XML que contiene la documentación.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-105">The name of the XML file containing the documentation.</span></span> <span data-ttu-id="3ad1d-106">El nombre de archivo se puede calificar con una ruta de acceso relativa al archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-106">The file name can be qualified with a path relative to the source code file.</span></span> <span data-ttu-id="3ad1d-107">Incluya `filename` entre comillas simples (' ').</span><span class="sxs-lookup"><span data-stu-id="3ad1d-107">Enclose `filename` in single quotation marks (' ').</span></span>  
  
 `tagpath`  
 <span data-ttu-id="3ad1d-108">La ruta de acceso de las etiquetas de `filename` que conduce a la etiqueta `name`.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-108">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="3ad1d-109">Incluya la ruta de acceso entre comillas simples (' ').</span><span class="sxs-lookup"><span data-stu-id="3ad1d-109">Enclose the path in single quotation marks (' ').</span></span>  
  
 `name`  
 <span data-ttu-id="3ad1d-110">El especificador de nombre en la etiqueta que precede a los comentarios; `name` tendrá un `id`.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-110">The name specifier in the tag that precedes the comments; `name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="3ad1d-111">El identificador de la etiqueta que precede a los comentarios.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-111">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="3ad1d-112">Ponga el identificador entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="3ad1d-112">Enclose the ID in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ad1d-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3ad1d-113">Remarks</span></span>  
 <span data-ttu-id="3ad1d-114">La etiqueta \<include> le permite hacer referencia a comentarios colocados en otro archivo que describen los tipos y miembros en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-114">The \<include> tag lets you refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="3ad1d-115">Esto es una alternativa a colocar los comentarios de documentación directamente en el archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-115">This is an alternative to placing documentation comments directly in your source code file.</span></span> <span data-ttu-id="3ad1d-116">Al colocar la documentación en un archivo independiente, puede aplicar el control de código fuente a la documentación de forma independiente desde el código fuente.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-116">By putting the documentation in a separate file, you can apply source control to the documentation separately from the source code.</span></span> <span data-ttu-id="3ad1d-117">Una persona puede tener el archivo de código fuente extraído del repositorio y otra persona puede tener el archivo de documentación extraído del repositorio.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-117">One person can have the source code file checked out and someone else can have the documentation file checked out.</span></span>  
  
 <span data-ttu-id="3ad1d-118">La etiqueta \<include> usa la sintaxis de XPath de XML.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-118">The \<include> tag uses the XML XPath syntax.</span></span> <span data-ttu-id="3ad1d-119">Consulte la documentación de XPath para ver formas de personalizar el uso de \<include>.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-119">Refer to XPath documentation for ways to customize your \<include> use.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ad1d-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3ad1d-120">Example</span></span>  
 <span data-ttu-id="3ad1d-121">Este es un ejemplo de múltiples archivos.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-121">This is a multifile example.</span></span> <span data-ttu-id="3ad1d-122">El primer archivo, que usa \<include>, se menciona a continuación:</span><span class="sxs-lookup"><span data-stu-id="3ad1d-122">The first file, which uses \<include>, is listed below:</span></span>  
  
 [!code-csharp[csProgGuideDocComments#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#5)]  
  
 <span data-ttu-id="3ad1d-123">El segundo archivo, xml_include_tag.doc, contiene los siguientes comentarios de documentación:</span><span class="sxs-lookup"><span data-stu-id="3ad1d-123">The second file, xml_include_tag.doc, contains the following documentation comments:</span></span>  
  
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
  
## <a name="program-output"></a><span data-ttu-id="3ad1d-124">Resultados del programa</span><span class="sxs-lookup"><span data-stu-id="3ad1d-124">Program Output</span></span>  
 <span data-ttu-id="3ad1d-125">El siguiente resultado se genera al compilar las clases Test y Test2 con la siguiente línea de comandos: `/doc:DocFileName.xml.` En Visual Studio, especifica la opción de comentarios de documentación XML en el panel Compilar del Diseñador de proyectos.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-125">The following output is generated when you compile the Test and Test2 classes with the following command line: `/doc:DocFileName.xml.` In Visual Studio, you specify the XML doc comments option in the Build pane of the Project Designer.</span></span> <span data-ttu-id="3ad1d-126">Cuando el compilador de C# detecta la etiqueta \<include>, busca los comentarios de documentación en xml_include_tag.doc en lugar del archivo de código fuente actual.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-126">When the C# compiler sees the \<include> tag, it will search for documentation comments in xml_include_tag.doc instead of the current source file.</span></span> <span data-ttu-id="3ad1d-127">Después, el compilador genera DocFileName.xml y este es el archivo que usan las herramientas de documentación como [DocFX](https://dotnet.github.io/docfx/) y [Sandcastle](https://github.com/EWSoftware/SHFB) para generar la documentación final.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-127">The compiler then generates DocFileName.xml, and this is the file that is consumed by documentation tools such as [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to produce the final documentation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3ad1d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ad1d-128">See also</span></span>

- [<span data-ttu-id="3ad1d-129">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3ad1d-129">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3ad1d-130">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="3ad1d-130">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
