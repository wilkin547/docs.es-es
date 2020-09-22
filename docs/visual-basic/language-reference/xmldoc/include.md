---
title: <include>
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: df8749ca9d6c92cf9ef95f03eea2704812ff495a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872878"
---
# <a name="include-visual-basic"></a><span data-ttu-id="8bc04-101">\<include> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8bc04-101">\<include> (Visual Basic)</span></span>

<span data-ttu-id="8bc04-102">Hace referencia a otro archivo que describe los tipos y miembros en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="8bc04-102">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bc04-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8bc04-103">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bc04-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8bc04-104">Parameters</span></span>  

 `filename`  
 <span data-ttu-id="8bc04-105">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="8bc04-105">Required.</span></span> <span data-ttu-id="8bc04-106">El nombre del archivo que contiene la documentación.</span><span class="sxs-lookup"><span data-stu-id="8bc04-106">The name of the file containing the documentation.</span></span> <span data-ttu-id="8bc04-107">El nombre de archivo se puede calificar con una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="8bc04-107">The file name can be qualified with a path.</span></span> <span data-ttu-id="8bc04-108">Escribir `filename` entre comillas dobles ("").</span><span class="sxs-lookup"><span data-stu-id="8bc04-108">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="8bc04-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="8bc04-109">Required.</span></span> <span data-ttu-id="8bc04-110">La ruta de acceso de las etiquetas de `filename` que conduce a la etiqueta `name`.</span><span class="sxs-lookup"><span data-stu-id="8bc04-110">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="8bc04-111">Escriba la ruta de acceso entre comillas dobles ("").</span><span class="sxs-lookup"><span data-stu-id="8bc04-111">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="8bc04-112">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="8bc04-112">Required.</span></span> <span data-ttu-id="8bc04-113">Especificador de nombre en la etiqueta que precede a los comentarios.</span><span class="sxs-lookup"><span data-stu-id="8bc04-113">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="8bc04-114">`Name` tendrá una `id` .</span><span class="sxs-lookup"><span data-stu-id="8bc04-114">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="8bc04-115">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="8bc04-115">Required.</span></span> <span data-ttu-id="8bc04-116">El identificador de la etiqueta que precede a los comentarios.</span><span class="sxs-lookup"><span data-stu-id="8bc04-116">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="8bc04-117">Incluya el identificador entre comillas simples (' ').</span><span class="sxs-lookup"><span data-stu-id="8bc04-117">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bc04-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8bc04-118">Remarks</span></span>  

 <span data-ttu-id="8bc04-119">Use la `<include>` etiqueta para hacer referencia a los comentarios de otro archivo que describen los tipos y miembros en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="8bc04-119">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="8bc04-120">Esto es una alternativa a colocar los comentarios de documentación directamente en el archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="8bc04-120">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="8bc04-121">La `<include>` etiqueta usa la recomendación W3C XML Path Language (XPath) versión 1,0.</span><span class="sxs-lookup"><span data-stu-id="8bc04-121">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="8bc04-122">Para obtener más información acerca de cómo personalizar el `<include>` uso, vea <https://www.w3.org/TR/xpath> .</span><span class="sxs-lookup"><span data-stu-id="8bc04-122">For more information about ways to customize your `<include>` use, see <https://www.w3.org/TR/xpath>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8bc04-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8bc04-123">Example</span></span>  

 <span data-ttu-id="8bc04-124">En este ejemplo se usa la `<include>` etiqueta para importar los comentarios de documentación de los miembros de un archivo denominado `commentFile.xml` .</span><span class="sxs-lookup"><span data-stu-id="8bc04-124">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#4)]  
  
 <span data-ttu-id="8bc04-125">El formato de `commentFile.xml` es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="8bc04-125">The format of the `commentFile.xml` is as follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8bc04-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8bc04-126">See also</span></span>

- [<span data-ttu-id="8bc04-127">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="8bc04-127">XML Comment Tags</span></span>](index.md)
