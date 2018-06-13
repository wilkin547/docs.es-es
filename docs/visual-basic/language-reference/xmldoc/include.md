---
title: '&lt;incluir&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: 65bc0439696612cd8331a9c0718efcfee83af574
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602741"
---
# <a name="ltincludegt-visual-basic"></a><span data-ttu-id="1ac8a-102">&lt;incluir&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ac8a-102">&lt;include&gt; (Visual Basic)</span></span>
<span data-ttu-id="1ac8a-103">Hace referencia a otro archivo que describe los tipos y miembros en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="1ac8a-103">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ac8a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ac8a-104">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1ac8a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1ac8a-105">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="1ac8a-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="1ac8a-106">Required.</span></span> <span data-ttu-id="1ac8a-107">El nombre del archivo que contiene la documentación.</span><span class="sxs-lookup"><span data-stu-id="1ac8a-107">The name of the file containing the documentation.</span></span> <span data-ttu-id="1ac8a-108">El nombre de archivo se puede calificar con una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="1ac8a-108">The file name can be qualified with a path.</span></span> <span data-ttu-id="1ac8a-109">Incluya `filename` comillas dobles ("").</span><span class="sxs-lookup"><span data-stu-id="1ac8a-109">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="1ac8a-110">Requerido.</span><span class="sxs-lookup"><span data-stu-id="1ac8a-110">Required.</span></span> <span data-ttu-id="1ac8a-111">La ruta de acceso de las etiquetas de `filename` que conduce a la etiqueta `name`.</span><span class="sxs-lookup"><span data-stu-id="1ac8a-111">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="1ac8a-112">Escriba la ruta de acceso entre comillas dobles ("").</span><span class="sxs-lookup"><span data-stu-id="1ac8a-112">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="1ac8a-113">Requerido.</span><span class="sxs-lookup"><span data-stu-id="1ac8a-113">Required.</span></span> <span data-ttu-id="1ac8a-114">El especificador de nombre en la etiqueta que precede a los comentarios.</span><span class="sxs-lookup"><span data-stu-id="1ac8a-114">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="1ac8a-115">`Name` tendrá un `id`.</span><span class="sxs-lookup"><span data-stu-id="1ac8a-115">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="1ac8a-116">Requerido.</span><span class="sxs-lookup"><span data-stu-id="1ac8a-116">Required.</span></span> <span data-ttu-id="1ac8a-117">El identificador de la etiqueta que precede a los comentarios.</span><span class="sxs-lookup"><span data-stu-id="1ac8a-117">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="1ac8a-118">Incluya el identificador entre comillas simples (' ').</span><span class="sxs-lookup"><span data-stu-id="1ac8a-118">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ac8a-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1ac8a-119">Remarks</span></span>  
 <span data-ttu-id="1ac8a-120">Use la `<include>` etiqueta para hacer referencia a comentarios colocados en otro archivo que describen los tipos y miembros en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="1ac8a-120">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="1ac8a-121">Esto es una alternativa a colocar los comentarios de documentación directamente en el archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="1ac8a-121">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="1ac8a-122">La `<include>` etiqueta utilizará la recomendación de la versión 1.0 de W3C XML Path Language (XPath).</span><span class="sxs-lookup"><span data-stu-id="1ac8a-122">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="1ac8a-123">Para obtener más información para formas de personalizar su `<include>` utilizar está disponible en http://www.w3.org/TR/xpath.</span><span class="sxs-lookup"><span data-stu-id="1ac8a-123">More information for ways to customize your `<include>` use is available at http://www.w3.org/TR/xpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ac8a-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1ac8a-124">Example</span></span>  
 <span data-ttu-id="1ac8a-125">Este ejemplo se utiliza la `<include>` etiqueta que se va a importar los comentarios de documentación de miembro desde un archivo denominado `commentFile.xml`.</span><span class="sxs-lookup"><span data-stu-id="1ac8a-125">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 <span data-ttu-id="1ac8a-126">El formato de la `commentFile.xml` es como sigue.</span><span class="sxs-lookup"><span data-stu-id="1ac8a-126">The format of the `commentFile.xml` is as follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1ac8a-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ac8a-127">See Also</span></span>  
 [<span data-ttu-id="1ac8a-128">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="1ac8a-128">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
