---
description: 'Más información acerca de: <list> (Visual Basic)'
title: <list>
ms.date: 07/20/2015
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
ms.openlocfilehash: c9e2e8d1c370bfdeefae4a8f19b25acc6a336ecc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787440"
---
# <a name="list-visual-basic"></a><span data-ttu-id="c2f27-103">\<list> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c2f27-103">\<list> (Visual Basic)</span></span>

<span data-ttu-id="c2f27-104">Define una lista o una tabla.</span><span class="sxs-lookup"><span data-stu-id="c2f27-104">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2f27-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2f27-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c2f27-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c2f27-106">Parameters</span></span>  

 `type`  
 <span data-ttu-id="c2f27-107">El tipo de la lista.</span><span class="sxs-lookup"><span data-stu-id="c2f27-107">The type of the list.</span></span> <span data-ttu-id="c2f27-108">Debe ser una "viñeta" para una lista con viñetas, "número" para una lista numerada o "tabla" para una tabla de dos columnas.</span><span class="sxs-lookup"><span data-stu-id="c2f27-108">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="c2f27-109">Solo se utiliza cuando `type` es "Table".</span><span class="sxs-lookup"><span data-stu-id="c2f27-109">Only used when `type` is "table."</span></span> <span data-ttu-id="c2f27-110">Un término para definir, que se define en la etiqueta de descripción.</span><span class="sxs-lookup"><span data-stu-id="c2f27-110">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="c2f27-111">Cuando `type` es "Bullet" o "número", `description` es un elemento de la lista cuando `type` es "Table", `description` es la definición de `term` .</span><span class="sxs-lookup"><span data-stu-id="c2f27-111">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2f27-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c2f27-112">Remarks</span></span>  

 <span data-ttu-id="c2f27-113">El `<listheader>` bloque define el encabezado de una tabla o de una lista de definiciones.</span><span class="sxs-lookup"><span data-stu-id="c2f27-113">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="c2f27-114">Al definir una tabla, solo tiene que proporcionar una entrada para `term` en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="c2f27-114">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="c2f27-115">Cada elemento de la lista se especifica con un bloque `<item>`.</span><span class="sxs-lookup"><span data-stu-id="c2f27-115">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="c2f27-116">Al crear una lista de definiciones, debe especificar `term` y `description` .</span><span class="sxs-lookup"><span data-stu-id="c2f27-116">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="c2f27-117">Sin embargo, para una tabla, una lista con viñetas o una lista numerada, solo tiene que proporcionar una entrada para `description` .</span><span class="sxs-lookup"><span data-stu-id="c2f27-117">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="c2f27-118">Una lista o una tabla pueden tener tantos bloques `<item>` como sean necesarios.</span><span class="sxs-lookup"><span data-stu-id="c2f27-118">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="c2f27-119">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="c2f27-119">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2f27-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2f27-120">Example</span></span>  

 <span data-ttu-id="c2f27-121">En este ejemplo se usa la `<list>` etiqueta para definir una lista con viñetas en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="c2f27-121">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="c2f27-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2f27-122">See also</span></span>

- [<span data-ttu-id="c2f27-123">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="c2f27-123">XML Comment Tags</span></span>](index.md)
