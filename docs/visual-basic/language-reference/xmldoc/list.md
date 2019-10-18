---
title: <list> (Visual Basic)
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
ms.openlocfilehash: 5d4295d485611e75e8b6c8d8f95e079654f0cfa3
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524752"
---
# <a name="list-visual-basic"></a><span data-ttu-id="4ae49-102">\<list > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ae49-102">\<list> (Visual Basic)</span></span>
<span data-ttu-id="4ae49-103">Define una lista o una tabla.</span><span class="sxs-lookup"><span data-stu-id="4ae49-103">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ae49-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ae49-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="4ae49-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4ae49-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="4ae49-106">El tipo de la lista.</span><span class="sxs-lookup"><span data-stu-id="4ae49-106">The type of the list.</span></span> <span data-ttu-id="4ae49-107">Debe ser una "viñeta" para una lista con viñetas, "número" para una lista numerada o "tabla" para una tabla de dos columnas.</span><span class="sxs-lookup"><span data-stu-id="4ae49-107">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="4ae49-108">Solo se usa cuando `type` es "Table".</span><span class="sxs-lookup"><span data-stu-id="4ae49-108">Only used when `type` is "table."</span></span> <span data-ttu-id="4ae49-109">Un término para definir, que se define en la etiqueta de descripción.</span><span class="sxs-lookup"><span data-stu-id="4ae49-109">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="4ae49-110">Cuando `type` es "Bullet" o "Number", `description` es un elemento de la lista cuando `type` es "Table" `description` es la definición de `term`.</span><span class="sxs-lookup"><span data-stu-id="4ae49-110">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ae49-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4ae49-111">Remarks</span></span>  
 <span data-ttu-id="4ae49-112">El bloque `<listheader>` define el encabezado de una tabla o de una lista de definiciones.</span><span class="sxs-lookup"><span data-stu-id="4ae49-112">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="4ae49-113">Al definir una tabla, solo tiene que proporcionar una entrada para `term` en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="4ae49-113">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="4ae49-114">Cada elemento de la lista se especifica con un bloque `<item>`.</span><span class="sxs-lookup"><span data-stu-id="4ae49-114">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="4ae49-115">Al crear una lista de definiciones, debe especificar `term` y `description`.</span><span class="sxs-lookup"><span data-stu-id="4ae49-115">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="4ae49-116">Sin embargo, para una tabla, una lista con viñetas o una lista numerada, solo tiene que proporcionar una entrada para `description`.</span><span class="sxs-lookup"><span data-stu-id="4ae49-116">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="4ae49-117">Una lista o una tabla puede tener tantos bloques de `<item>` como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="4ae49-117">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="4ae49-118">Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="4ae49-118">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ae49-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4ae49-119">Example</span></span>  
 <span data-ttu-id="4ae49-120">En este ejemplo se usa la etiqueta `<list>` para definir una lista con viñetas en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="4ae49-120">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="4ae49-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ae49-121">See also</span></span>

- [<span data-ttu-id="4ae49-122">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="4ae49-122">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
