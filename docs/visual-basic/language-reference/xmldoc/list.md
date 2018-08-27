---
title: '&lt;lista&gt; (Visual Basic)'
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
ms.openlocfilehash: 98c3b8bd809ac550468a5d80e01e6fd16e6d96ea
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2018
ms.locfileid: "42924939"
---
# <a name="ltlistgt-visual-basic"></a><span data-ttu-id="02489-102">&lt;lista&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02489-102">&lt;list&gt; (Visual Basic)</span></span>
<span data-ttu-id="02489-103">Define una lista o tabla.</span><span class="sxs-lookup"><span data-stu-id="02489-103">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02489-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02489-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="02489-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="02489-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="02489-106">El tipo de la lista.</span><span class="sxs-lookup"><span data-stu-id="02489-106">The type of the list.</span></span> <span data-ttu-id="02489-107">Debe ser un "bullet" para una lista con viñetas, "number" para una lista numerada o "table" para una tabla de dos columnas.</span><span class="sxs-lookup"><span data-stu-id="02489-107">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="02489-108">Solo se emplea para `type` es "table".</span><span class="sxs-lookup"><span data-stu-id="02489-108">Only used when `type` is "table."</span></span> <span data-ttu-id="02489-109">Término que se define en la etiqueta de descripción.</span><span class="sxs-lookup"><span data-stu-id="02489-109">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="02489-110">Cuando `type` es "bullet" o "number", `description` es un elemento de la lista cuando `type` es "table"," `description` es la definición de `term`.</span><span class="sxs-lookup"><span data-stu-id="02489-110">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02489-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="02489-111">Remarks</span></span>  
 <span data-ttu-id="02489-112">El `<listheader>` bloque define el encabezado de una tabla o una definición de lista.</span><span class="sxs-lookup"><span data-stu-id="02489-112">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="02489-113">Al definir una tabla, solo tiene que suministrar una entrada para `term` en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="02489-113">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="02489-114">Cada elemento de la lista se especifica con un `<item>` bloque.</span><span class="sxs-lookup"><span data-stu-id="02489-114">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="02489-115">Al crear una lista de definiciones, debe especificar ambos `term` y `description`.</span><span class="sxs-lookup"><span data-stu-id="02489-115">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="02489-116">Sin embargo, para una tabla, lista con viñetas o lista numerada, solo tiene que suministrar una entrada para `description`.</span><span class="sxs-lookup"><span data-stu-id="02489-116">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="02489-117">Una lista o tabla puede tener tantos `<item>` bloquea según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="02489-117">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="02489-118">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="02489-118">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02489-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02489-119">Example</span></span>  
 <span data-ttu-id="02489-120">Este ejemplo se usa el `<list>` etiqueta para definir una lista con viñetas en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="02489-120">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/list_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="02489-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="02489-121">See Also</span></span>  
 [<span data-ttu-id="02489-122">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="02489-122">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
