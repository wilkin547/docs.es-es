---
title: '&lt;comentarios&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 137e2fcd36d5d7618e0193461ebf7ca70b24d19f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737655"
---
# <a name="ltremarksgt-visual-basic"></a><span data-ttu-id="76db1-102">&lt;comentarios&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="76db1-102">&lt;remarks&gt; (Visual Basic)</span></span>
<span data-ttu-id="76db1-103">Especifica una sección de comentarios del miembro.</span><span class="sxs-lookup"><span data-stu-id="76db1-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76db1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76db1-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="76db1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="76db1-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="76db1-106">Descripción del miembro.</span><span class="sxs-lookup"><span data-stu-id="76db1-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76db1-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="76db1-107">Remarks</span></span>  
 <span data-ttu-id="76db1-108">Use la `<remarks>` etiqueta para agregar información sobre un tipo, complementar la información especificada con [ \<resumen >](../../../visual-basic/language-reference/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="76db1-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="76db1-109">Esta información aparece en el Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="76db1-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="76db1-110">Para obtener información sobre el Examinador de objetos, vea [ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="76db1-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="76db1-111">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="76db1-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76db1-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="76db1-112">Example</span></span>  
 <span data-ttu-id="76db1-113">Este ejemplo se usa el `<remarks>` etiqueta para explicar qué es el `UpdateRecord` método.</span><span class="sxs-lookup"><span data-stu-id="76db1-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="76db1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="76db1-114">See also</span></span>
- [<span data-ttu-id="76db1-115">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="76db1-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
