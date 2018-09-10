---
title: '&lt;incluir&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: da7a6c15c558fc56dbc6a874d4a28c4434f67668
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44272480"
---
# <a name="ltincludegt-visual-basic"></a><span data-ttu-id="96b56-102">&lt;incluir&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96b56-102">&lt;include&gt; (Visual Basic)</span></span>
<span data-ttu-id="96b56-103">Hace referencia a otro archivo que se describe los tipos y miembros en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="96b56-103">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96b56-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96b56-104">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96b56-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="96b56-105">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="96b56-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="96b56-106">Required.</span></span> <span data-ttu-id="96b56-107">El nombre del archivo que contiene la documentación.</span><span class="sxs-lookup"><span data-stu-id="96b56-107">The name of the file containing the documentation.</span></span> <span data-ttu-id="96b56-108">El nombre de archivo se puede calificar con una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="96b56-108">The file name can be qualified with a path.</span></span> <span data-ttu-id="96b56-109">Incluya `filename` comillas dobles ("").</span><span class="sxs-lookup"><span data-stu-id="96b56-109">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="96b56-110">Requerido.</span><span class="sxs-lookup"><span data-stu-id="96b56-110">Required.</span></span> <span data-ttu-id="96b56-111">La ruta de acceso de las etiquetas de `filename` que conduce a la etiqueta `name`.</span><span class="sxs-lookup"><span data-stu-id="96b56-111">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="96b56-112">Incluya la ruta de acceso entre comillas dobles ("").</span><span class="sxs-lookup"><span data-stu-id="96b56-112">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="96b56-113">Requerido.</span><span class="sxs-lookup"><span data-stu-id="96b56-113">Required.</span></span> <span data-ttu-id="96b56-114">El especificador de nombre en la etiqueta que precede a los comentarios.</span><span class="sxs-lookup"><span data-stu-id="96b56-114">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="96b56-115">`Name` tendrá un `id`.</span><span class="sxs-lookup"><span data-stu-id="96b56-115">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="96b56-116">Requerido.</span><span class="sxs-lookup"><span data-stu-id="96b56-116">Required.</span></span> <span data-ttu-id="96b56-117">El identificador de la etiqueta que precede a los comentarios.</span><span class="sxs-lookup"><span data-stu-id="96b56-117">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="96b56-118">Ponga el identificador entre comillas simples (' ').</span><span class="sxs-lookup"><span data-stu-id="96b56-118">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96b56-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="96b56-119">Remarks</span></span>  
 <span data-ttu-id="96b56-120">Use la `<include>` etiqueta para hacer referencia a los comentarios de otro archivo que describen los tipos y miembros en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="96b56-120">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="96b56-121">Esto es una alternativa a colocar los comentarios de documentación directamente en el archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="96b56-121">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="96b56-122">El `<include>` etiqueta usa la recomendación versión 1.0 de W3C XML Path Language (XPath).</span><span class="sxs-lookup"><span data-stu-id="96b56-122">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="96b56-123">Para obtener más información sobre cómo personalizar su `<include>` uso está disponible en http://www.w3.org/TR/xpath.</span><span class="sxs-lookup"><span data-stu-id="96b56-123">More information for ways to customize your `<include>` use is available at http://www.w3.org/TR/xpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96b56-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="96b56-124">Example</span></span>  
 <span data-ttu-id="96b56-125">Este ejemplo se usa el `<include>` etiqueta para importar los comentarios de documentación de miembro de un archivo denominado `commentFile.xml`.</span><span class="sxs-lookup"><span data-stu-id="96b56-125">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 <span data-ttu-id="96b56-126">El formato de la `commentFile.xml` es como sigue.</span><span class="sxs-lookup"><span data-stu-id="96b56-126">The format of the `commentFile.xml` is as follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="96b56-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="96b56-127">See Also</span></span>  
 [<span data-ttu-id="96b56-128">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="96b56-128">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
