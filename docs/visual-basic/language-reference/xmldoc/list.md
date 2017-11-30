---
title: '&lt;lista&gt; (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- listheader XML tag
- <item> XML tag
- <list> XML tag
- <listheader> XML tag
- term XML tag
- list XML tag
- <description> XML tag
- description XML tag
- item XML tag
- <term> XML tag
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 34347df88f1bc3097db0020526ec99943c8f7bd4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltlistgt-visual-basic"></a><span data-ttu-id="65810-102">&lt;lista&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65810-102">&lt;list&gt; (Visual Basic)</span></span>
<span data-ttu-id="65810-103">Define una lista o tabla.</span><span class="sxs-lookup"><span data-stu-id="65810-103">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65810-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65810-104">Syntax</span></span>  
  
```xml  
<list type="type">  
   <listheader>  
      <term>term</term>  
      <description>description</description>  
   </listheader>  
   <item>  
      <term>term</term>  
      <description>description</description>  
   </item>  
</list>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65810-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="65810-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="65810-106">El tipo de la lista.</span><span class="sxs-lookup"><span data-stu-id="65810-106">The type of the list.</span></span> <span data-ttu-id="65810-107">Debe ser "bullet" para una lista con viñetas, "number" para una lista numerada o "table" para una tabla de dos columnas.</span><span class="sxs-lookup"><span data-stu-id="65810-107">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="65810-108">Sólo se utiliza cuando `type` es "table".</span><span class="sxs-lookup"><span data-stu-id="65810-108">Only used when `type` is "table."</span></span> <span data-ttu-id="65810-109">Término que se define en la etiqueta de descripción.</span><span class="sxs-lookup"><span data-stu-id="65810-109">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="65810-110">Cuando `type` es "bullet" o "número", `description` es un elemento de la lista cuando `type` es "table", `description` es la definición de `term`.</span><span class="sxs-lookup"><span data-stu-id="65810-110">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65810-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="65810-111">Remarks</span></span>  
 <span data-ttu-id="65810-112">El `<listheader>` bloque define el encabezado de una tabla o una definición de lista.</span><span class="sxs-lookup"><span data-stu-id="65810-112">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="65810-113">Cuando se define una tabla, solo tiene que suministrar una entrada para `term` en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="65810-113">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="65810-114">Cada elemento de la lista se especifica con un `<item>` bloque.</span><span class="sxs-lookup"><span data-stu-id="65810-114">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="65810-115">Al crear una lista de definiciones, debe especificar tanto `term` y `description`.</span><span class="sxs-lookup"><span data-stu-id="65810-115">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="65810-116">Sin embargo, para una tabla, una lista con viñetas o una lista numerada, solo tienes que proporcionar una entrada para `description`.</span><span class="sxs-lookup"><span data-stu-id="65810-116">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="65810-117">Una lista o una tabla puede tener tantos `<item>` bloquea según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="65810-117">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="65810-118">Compile con el parámetro [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación y generar un archivo con ellos.</span><span class="sxs-lookup"><span data-stu-id="65810-118">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65810-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="65810-119">Example</span></span>  
 <span data-ttu-id="65810-120">Este ejemplo se utiliza la `<list>` etiqueta para definir una lista con viñetas en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="65810-120">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/list_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="65810-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="65810-121">See Also</span></span>  
 [<span data-ttu-id="65810-122">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="65810-122">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
