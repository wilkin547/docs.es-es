---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 857ea1ccca4d74daf65bba03845004561afefd55
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348508"
---
# <a name="c-visual-basic"></a><span data-ttu-id="6706f-101">\<c> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6706f-101">\<c> (Visual Basic)</span></span>
<span data-ttu-id="6706f-102">Indicates that text within a description is code.</span><span class="sxs-lookup"><span data-stu-id="6706f-102">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6706f-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6706f-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="6706f-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6706f-104">Parameters</span></span>  
  
|<span data-ttu-id="6706f-105">Parámetro</span><span class="sxs-lookup"><span data-stu-id="6706f-105">Parameter</span></span>|<span data-ttu-id="6706f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="6706f-106">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="6706f-107">El texto que le gustaría indicar como código.</span><span class="sxs-lookup"><span data-stu-id="6706f-107">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6706f-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6706f-108">Remarks</span></span>  
 <span data-ttu-id="6706f-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span><span class="sxs-lookup"><span data-stu-id="6706f-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="6706f-110">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) para indicar varias líneas como código.</span><span class="sxs-lookup"><span data-stu-id="6706f-110">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="6706f-111">Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="6706f-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6706f-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6706f-112">Example</span></span>  
 <span data-ttu-id="6706f-113">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span><span class="sxs-lookup"><span data-stu-id="6706f-113">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6706f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6706f-114">See also</span></span>

- [<span data-ttu-id="6706f-115">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="6706f-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
