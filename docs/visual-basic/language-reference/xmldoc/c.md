---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: c8ba03d9cc01c4751d15c01530c6cbf7d499dc3b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400168"
---
# <a name="c-visual-basic"></a><span data-ttu-id="0c61c-101">\<c> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c61c-101">\<c> (Visual Basic)</span></span>
<span data-ttu-id="0c61c-102">Indica que el texto de una descripción es código.</span><span class="sxs-lookup"><span data-stu-id="0c61c-102">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c61c-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c61c-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c61c-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0c61c-104">Parameters</span></span>  
  
|<span data-ttu-id="0c61c-105">Parámetro</span><span class="sxs-lookup"><span data-stu-id="0c61c-105">Parameter</span></span>|<span data-ttu-id="0c61c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c61c-106">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="0c61c-107">El texto que le gustaría indicar como código.</span><span class="sxs-lookup"><span data-stu-id="0c61c-107">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c61c-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0c61c-108">Remarks</span></span>  
 <span data-ttu-id="0c61c-109">La `<c>` etiqueta proporciona una manera de indicar que el texto dentro de una descripción debe marcarse como código.</span><span class="sxs-lookup"><span data-stu-id="0c61c-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="0c61c-110">[\<code>](code.md)Se usa para indicar varias líneas como código.</span><span class="sxs-lookup"><span data-stu-id="0c61c-110">Use [\<code>](code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="0c61c-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.</span><span class="sxs-lookup"><span data-stu-id="0c61c-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c61c-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c61c-112">Example</span></span>  
 <span data-ttu-id="0c61c-113">En este ejemplo se usa la `<c>` etiqueta en la sección de resumen para indicar que `Counter` es código.</span><span class="sxs-lookup"><span data-stu-id="0c61c-113">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0c61c-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0c61c-114">See also</span></span>

- [<span data-ttu-id="0c61c-115">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="0c61c-115">XML Comment Tags</span></span>](index.md)
