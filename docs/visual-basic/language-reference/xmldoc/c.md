---
title: <c> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: d8efd2359ecb65bec1b427d8b1dca4b0c88a1152
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469032"
---
# <a name="c-visual-basic"></a><span data-ttu-id="332c6-102">\<c > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="332c6-102">\<c> (Visual Basic)</span></span>
<span data-ttu-id="332c6-103">Indica que el texto dentro de una descripción es código.</span><span class="sxs-lookup"><span data-stu-id="332c6-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="332c6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="332c6-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="332c6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="332c6-105">Parameters</span></span>  
  
|<span data-ttu-id="332c6-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="332c6-106">Parameter</span></span>|<span data-ttu-id="332c6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="332c6-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="332c6-108">El texto que le gustaría indicar como código.</span><span class="sxs-lookup"><span data-stu-id="332c6-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="332c6-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="332c6-109">Remarks</span></span>  
 <span data-ttu-id="332c6-110">El `<c>` etiqueta ofrece una manera de indicar que el texto dentro de una descripción debe marcarse como código.</span><span class="sxs-lookup"><span data-stu-id="332c6-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="332c6-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) para indicar varias líneas como código.</span><span class="sxs-lookup"><span data-stu-id="332c6-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="332c6-112">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="332c6-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="332c6-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="332c6-113">Example</span></span>  
 <span data-ttu-id="332c6-114">Este ejemplo se usa el `<c>` etiqueta en la sección de resumen para indicar que `Counter` es el código.</span><span class="sxs-lookup"><span data-stu-id="332c6-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="332c6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="332c6-115">See also</span></span>
- [<span data-ttu-id="332c6-116">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="332c6-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
