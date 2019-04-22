---
title: <include> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: d9c1c1a50f0e3530c842a6058e288b8d2be15f95
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832546"
---
# <a name="include-visual-basic"></a><span data-ttu-id="1f49a-102">\<Incluir > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f49a-102">\<include> (Visual Basic)</span></span>
<span data-ttu-id="1f49a-103">Hace referencia a otro archivo que se describe los tipos y miembros en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="1f49a-103">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f49a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f49a-104">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f49a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1f49a-105">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="1f49a-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1f49a-106">Required.</span></span> <span data-ttu-id="1f49a-107">El nombre del archivo que contiene la documentación.</span><span class="sxs-lookup"><span data-stu-id="1f49a-107">The name of the file containing the documentation.</span></span> <span data-ttu-id="1f49a-108">El nombre de archivo se puede calificar con una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="1f49a-108">The file name can be qualified with a path.</span></span> <span data-ttu-id="1f49a-109">Incluya `filename` comillas dobles ("").</span><span class="sxs-lookup"><span data-stu-id="1f49a-109">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="1f49a-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1f49a-110">Required.</span></span> <span data-ttu-id="1f49a-111">La ruta de acceso de las etiquetas de `filename` que conduce a la etiqueta `name`.</span><span class="sxs-lookup"><span data-stu-id="1f49a-111">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="1f49a-112">Incluya la ruta de acceso entre comillas dobles ("").</span><span class="sxs-lookup"><span data-stu-id="1f49a-112">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="1f49a-113">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1f49a-113">Required.</span></span> <span data-ttu-id="1f49a-114">El especificador de nombre en la etiqueta que precede a los comentarios.</span><span class="sxs-lookup"><span data-stu-id="1f49a-114">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="1f49a-115">`Name` tendrá un `id`.</span><span class="sxs-lookup"><span data-stu-id="1f49a-115">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="1f49a-116">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1f49a-116">Required.</span></span> <span data-ttu-id="1f49a-117">El identificador de la etiqueta que precede a los comentarios.</span><span class="sxs-lookup"><span data-stu-id="1f49a-117">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="1f49a-118">Ponga el identificador entre comillas simples (' ').</span><span class="sxs-lookup"><span data-stu-id="1f49a-118">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f49a-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1f49a-119">Remarks</span></span>  
 <span data-ttu-id="1f49a-120">Use la `<include>` etiqueta para hacer referencia a los comentarios de otro archivo que describen los tipos y miembros en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="1f49a-120">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="1f49a-121">Esto es una alternativa a colocar los comentarios de documentación directamente en el archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="1f49a-121">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="1f49a-122">El `<include>` etiqueta usa la recomendación versión 1.0 de W3C XML Path Language (XPath).</span><span class="sxs-lookup"><span data-stu-id="1f49a-122">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="1f49a-123">Para obtener más información acerca de las formas de personalizar su `<include>` , consulte <https://www.w3.org/TR/xpath>.</span><span class="sxs-lookup"><span data-stu-id="1f49a-123">For more information about ways to customize your `<include>` use, see <https://www.w3.org/TR/xpath>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f49a-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f49a-124">Example</span></span>  
 <span data-ttu-id="1f49a-125">Este ejemplo se usa el `<include>` etiqueta para importar los comentarios de documentación de miembro de un archivo denominado `commentFile.xml`.</span><span class="sxs-lookup"><span data-stu-id="1f49a-125">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#4)]  
  
 <span data-ttu-id="1f49a-126">El formato de la `commentFile.xml` es como sigue.</span><span class="sxs-lookup"><span data-stu-id="1f49a-126">The format of the `commentFile.xml` is as follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1f49a-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f49a-127">See also</span></span>

- [<span data-ttu-id="1f49a-128">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="1f49a-128">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
