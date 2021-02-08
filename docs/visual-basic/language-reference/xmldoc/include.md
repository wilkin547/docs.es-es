---
description: 'Más información acerca de: <include> (Visual Basic)'
title: <include>
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: 8207b74ed74bd529f2da865777e287320b23d293
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787466"
---
# <a name="include-visual-basic"></a><span data-ttu-id="09de1-103">\<include> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09de1-103">\<include> (Visual Basic)</span></span>

<span data-ttu-id="09de1-104">Hace referencia a otro archivo que describe los tipos y miembros en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="09de1-104">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09de1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09de1-105">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
## <a name="parameters"></a><span data-ttu-id="09de1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="09de1-106">Parameters</span></span>  

 `filename`  
 <span data-ttu-id="09de1-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="09de1-107">Required.</span></span> <span data-ttu-id="09de1-108">El nombre del archivo que contiene la documentación.</span><span class="sxs-lookup"><span data-stu-id="09de1-108">The name of the file containing the documentation.</span></span> <span data-ttu-id="09de1-109">El nombre de archivo se puede calificar con una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="09de1-109">The file name can be qualified with a path.</span></span> <span data-ttu-id="09de1-110">Escribir `filename` entre comillas dobles ("").</span><span class="sxs-lookup"><span data-stu-id="09de1-110">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="09de1-111">Necesario.</span><span class="sxs-lookup"><span data-stu-id="09de1-111">Required.</span></span> <span data-ttu-id="09de1-112">La ruta de acceso de las etiquetas de `filename` que conduce a la etiqueta `name`.</span><span class="sxs-lookup"><span data-stu-id="09de1-112">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="09de1-113">Escriba la ruta de acceso entre comillas dobles ("").</span><span class="sxs-lookup"><span data-stu-id="09de1-113">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="09de1-114">Necesario.</span><span class="sxs-lookup"><span data-stu-id="09de1-114">Required.</span></span> <span data-ttu-id="09de1-115">Especificador de nombre en la etiqueta que precede a los comentarios.</span><span class="sxs-lookup"><span data-stu-id="09de1-115">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="09de1-116">`Name` tendrá una `id` .</span><span class="sxs-lookup"><span data-stu-id="09de1-116">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="09de1-117">Necesario.</span><span class="sxs-lookup"><span data-stu-id="09de1-117">Required.</span></span> <span data-ttu-id="09de1-118">El identificador de la etiqueta que precede a los comentarios.</span><span class="sxs-lookup"><span data-stu-id="09de1-118">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="09de1-119">Incluya el identificador entre comillas simples (' ').</span><span class="sxs-lookup"><span data-stu-id="09de1-119">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09de1-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="09de1-120">Remarks</span></span>  

 <span data-ttu-id="09de1-121">Use la `<include>` etiqueta para hacer referencia a los comentarios de otro archivo que describen los tipos y miembros en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="09de1-121">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="09de1-122">Esto es una alternativa a colocar los comentarios de documentación directamente en el archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="09de1-122">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="09de1-123">La `<include>` etiqueta usa la recomendación W3C XML Path Language (XPath) versión 1,0.</span><span class="sxs-lookup"><span data-stu-id="09de1-123">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="09de1-124">Para obtener más información acerca de cómo personalizar el `<include>` uso, vea <https://www.w3.org/TR/xpath> .</span><span class="sxs-lookup"><span data-stu-id="09de1-124">For more information about ways to customize your `<include>` use, see <https://www.w3.org/TR/xpath>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09de1-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09de1-125">Example</span></span>  

 <span data-ttu-id="09de1-126">En este ejemplo se usa la `<include>` etiqueta para importar los comentarios de documentación de los miembros de un archivo denominado `commentFile.xml` .</span><span class="sxs-lookup"><span data-stu-id="09de1-126">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#4)]  
  
 <span data-ttu-id="09de1-127">El formato de `commentFile.xml` es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="09de1-127">The format of the `commentFile.xml` is as follows.</span></span>  
  
```xml  
<Docs>  
<Members name="Open">  
<summary>Opens a file.</summary>  
<param name="filename">File name to open.</param>  
</Members>  
<Members name="Close">  
<summary>Closes a file.</summary>  
<param name="filename">File name to close.</param>  
</Members>  
</Docs>  
```  
  
## <a name="see-also"></a><span data-ttu-id="09de1-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="09de1-128">See also</span></span>

- [<span data-ttu-id="09de1-129">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="09de1-129">XML Comment Tags</span></span>](index.md)
