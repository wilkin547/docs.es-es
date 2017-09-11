---
title: "&lt;include&gt; (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- include
- <include>
dev_langs:
- CSharp
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
caps.latest.revision: 19
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
ms.sourcegitcommit: df0438dd742db802bb0f935d840006236d5d9bf9
ms.openlocfilehash: 0cabcc25c4e35027c600e4af2bccfad7f9db1514
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="ltincludegt-c-programming-guide"></a><span data-ttu-id="63bff-102">&lt;include&gt; (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="63bff-102">&lt;include&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="63bff-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63bff-103">Syntax</span></span>  
  
```xml  
<include file='filename' path='tagpath[@name="id"]' />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63bff-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="63bff-104">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="63bff-105">El nombre del archivo XML que contiene la documentación.</span><span class="sxs-lookup"><span data-stu-id="63bff-105">The name of the XML file containing the documentation.</span></span> <span data-ttu-id="63bff-106">El nombre de archivo se puede calificar con una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="63bff-106">The file name can be qualified with a path.</span></span> <span data-ttu-id="63bff-107">Incluya `filename` entre comillas simples (' ').</span><span class="sxs-lookup"><span data-stu-id="63bff-107">Enclose `filename` in single quotation marks (' ').</span></span>  
  
 `tagpath`  
 <span data-ttu-id="63bff-108">La ruta de acceso de las etiquetas de `filename` que conduce a la etiqueta `name`.</span><span class="sxs-lookup"><span data-stu-id="63bff-108">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="63bff-109">Incluya la ruta de acceso entre comillas simples (' ').</span><span class="sxs-lookup"><span data-stu-id="63bff-109">Enclose the path in single quotation marks (' ').</span></span>  
  
 `name`  
 <span data-ttu-id="63bff-110">El especificador de nombre en la etiqueta que precede a los comentarios; `name` tendrá un `id`.</span><span class="sxs-lookup"><span data-stu-id="63bff-110">The name specifier in the tag that precedes the comments; `name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="63bff-111">El identificador de la etiqueta que precede a los comentarios.</span><span class="sxs-lookup"><span data-stu-id="63bff-111">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="63bff-112">Ponga el identificador entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="63bff-112">Enclose the ID in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63bff-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63bff-113">Remarks</span></span>  
 <span data-ttu-id="63bff-114">La etiqueta \<include> le permite hacer referencia a comentarios colocados en otro archivo que describen los tipos y miembros en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="63bff-114">The \<include> tag lets you refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="63bff-115">Esto es una alternativa a colocar los comentarios de documentación directamente en el archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="63bff-115">This is an alternative to placing documentation comments directly in your source code file.</span></span> <span data-ttu-id="63bff-116">Al colocar la documentación en un archivo independiente, puede aplicar el control de código fuente a la documentación de forma independiente desde el código fuente.</span><span class="sxs-lookup"><span data-stu-id="63bff-116">By putting the documentation in a separate file, you can apply source control to the documentation separately from the source code.</span></span> <span data-ttu-id="63bff-117">Una persona puede tener el archivo de código fuente extraído del repositorio y otra persona puede tener el archivo de documentación extraído del repositorio.</span><span class="sxs-lookup"><span data-stu-id="63bff-117">One person can have the source code file checked out and someone else can have the documentation file checked out.</span></span>  
  
 <span data-ttu-id="63bff-118">La etiqueta \<include> usa la sintaxis de XPath de XML.</span><span class="sxs-lookup"><span data-stu-id="63bff-118">The \<include> tag uses the XML XPath syntax.</span></span> <span data-ttu-id="63bff-119">Consulte la documentación de XPath para ver formas de personalizar el uso de \<include>.</span><span class="sxs-lookup"><span data-stu-id="63bff-119">Refer to XPath documentation for ways to customize your \<include> use.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63bff-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="63bff-120">Example</span></span>  
 <span data-ttu-id="63bff-121">Este es un ejemplo de múltiples archivos.</span><span class="sxs-lookup"><span data-stu-id="63bff-121">This is a multifile example.</span></span> <span data-ttu-id="63bff-122">El primer archivo, que usa \<include>, se menciona a continuación:</span><span class="sxs-lookup"><span data-stu-id="63bff-122">The first file, which uses \<include>, is listed below:</span></span>  
  
 <span data-ttu-id="63bff-123">[!code-cs[csProgGuideDocComments#5](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/include_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="63bff-123">[!code-cs[csProgGuideDocComments#5](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/include_1.cs)]</span></span>  
  
 <span data-ttu-id="63bff-124">El segundo archivo, xml_include_tag.doc, contiene los siguientes comentarios de documentación:</span><span class="sxs-lookup"><span data-stu-id="63bff-124">The second file, xml_include_tag.doc, contains the following documentation comments:</span></span>  
  
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
  
## <a name="program-output"></a><span data-ttu-id="63bff-125">Resultados del programa</span><span class="sxs-lookup"><span data-stu-id="63bff-125">Program Output</span></span>  
 <span data-ttu-id="63bff-126">Se genera el siguiente resultado al compilar las clases Test y Test2 con la siguiente línea de comandos: `/doc:DocFileName.xml.` En Visual Studio, especifique la opción de comentarios de documentación XML en el panel de compilación del Diseñador de proyectos.</span><span class="sxs-lookup"><span data-stu-id="63bff-126">The following output is generated when you compile the Test and Test2 classes with the following command line: `/doc:DocFileName.xml.` In Visual Studio, you specify the XML doc comments option in the Build pane of the Project Designer.</span></span> <span data-ttu-id="63bff-127">Cuando el compilador de C# detecta la etiqueta \<include>, busca los comentarios de documentación en xml_include_tag.doc en lugar del archivo de código fuente actual.</span><span class="sxs-lookup"><span data-stu-id="63bff-127">When the C# compiler sees the \<include> tag, it will search for documentation comments in xml_include_tag.doc instead of the current source file.</span></span> <span data-ttu-id="63bff-128">Después, el compilador genera DocFileName.xml y este es el archivo que usan las herramientas de documentación como [Sandcastle](https://github.com/EWSoftware/SHFB) para generar la documentación final.</span><span class="sxs-lookup"><span data-stu-id="63bff-128">The compiler then generates DocFileName.xml, and this is the file that is consumed by documentation tools such as [Sandcastle](https://github.com/EWSoftware/SHFB) to produce the final documentation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="63bff-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="63bff-129">See Also</span></span>  
 <span data-ttu-id="63bff-130">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="63bff-130">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="63bff-131">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="63bff-131">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

