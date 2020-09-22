---
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
ms.openlocfilehash: 900cd8c467a21812d980cffa7e41120ae557704b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872783"
---
# <a name="list-visual-basic"></a><span data-ttu-id="57648-101">\<list> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57648-101">\<list> (Visual Basic)</span></span>

<span data-ttu-id="57648-102">Define una lista o una tabla.</span><span class="sxs-lookup"><span data-stu-id="57648-102">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57648-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57648-103">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="57648-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="57648-104">Parameters</span></span>  

 `type`  
 <span data-ttu-id="57648-105">El tipo de la lista.</span><span class="sxs-lookup"><span data-stu-id="57648-105">The type of the list.</span></span> <span data-ttu-id="57648-106">Debe ser una "viñeta" para una lista con viñetas, "número" para una lista numerada o "tabla" para una tabla de dos columnas.</span><span class="sxs-lookup"><span data-stu-id="57648-106">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="57648-107">Solo se utiliza cuando `type` es "Table".</span><span class="sxs-lookup"><span data-stu-id="57648-107">Only used when `type` is "table."</span></span> <span data-ttu-id="57648-108">Un término para definir, que se define en la etiqueta de descripción.</span><span class="sxs-lookup"><span data-stu-id="57648-108">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="57648-109">Cuando `type` es "Bullet" o "número", `description` es un elemento de la lista cuando `type` es "Table", `description` es la definición de `term` .</span><span class="sxs-lookup"><span data-stu-id="57648-109">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57648-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="57648-110">Remarks</span></span>  

 <span data-ttu-id="57648-111">El `<listheader>` bloque define el encabezado de una tabla o de una lista de definiciones.</span><span class="sxs-lookup"><span data-stu-id="57648-111">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="57648-112">Al definir una tabla, solo tiene que proporcionar una entrada para `term` en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="57648-112">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="57648-113">Cada elemento de la lista se especifica con un bloque `<item>`.</span><span class="sxs-lookup"><span data-stu-id="57648-113">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="57648-114">Al crear una lista de definiciones, debe especificar `term` y `description` .</span><span class="sxs-lookup"><span data-stu-id="57648-114">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="57648-115">Sin embargo, para una tabla, una lista con viñetas o una lista numerada, solo tiene que proporcionar una entrada para `description` .</span><span class="sxs-lookup"><span data-stu-id="57648-115">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="57648-116">Una lista o una tabla pueden tener tantos bloques `<item>` como sean necesarios.</span><span class="sxs-lookup"><span data-stu-id="57648-116">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="57648-117">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="57648-117">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57648-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57648-118">Example</span></span>  

 <span data-ttu-id="57648-119">En este ejemplo se usa la `<list>` etiqueta para definir una lista con viñetas en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="57648-119">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="57648-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57648-120">See also</span></span>

- [<span data-ttu-id="57648-121">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="57648-121">XML Comment Tags</span></span>](index.md)
