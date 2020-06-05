---
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: aa65fed863718f1f00b510f82051a13e764e1b23
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400154"
---
# <a name="code-visual-basic"></a><span data-ttu-id="a20ae-101">\<code> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a20ae-101">\<code> (Visual Basic)</span></span>
<span data-ttu-id="a20ae-102">Indica que el texto es varias líneas de código.</span><span class="sxs-lookup"><span data-stu-id="a20ae-102">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a20ae-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a20ae-103">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a><span data-ttu-id="a20ae-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a20ae-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="a20ae-105">Texto que se va a marcar como código.</span><span class="sxs-lookup"><span data-stu-id="a20ae-105">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a20ae-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a20ae-106">Remarks</span></span>  
 <span data-ttu-id="a20ae-107">Use la `<code>` etiqueta para indicar varias líneas como código.</span><span class="sxs-lookup"><span data-stu-id="a20ae-107">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="a20ae-108">Use [\<c>](c.md) para indicar que el texto dentro de una descripción debe marcarse como código.</span><span class="sxs-lookup"><span data-stu-id="a20ae-108">Use [\<c>](c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="a20ae-109">Compile with [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.</span><span class="sxs-lookup"><span data-stu-id="a20ae-109">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a20ae-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a20ae-110">Example</span></span>  
 <span data-ttu-id="a20ae-111">En este ejemplo se usa la \<code> etiqueta para incluir código de ejemplo para usar el `ID` campo.</span><span class="sxs-lookup"><span data-stu-id="a20ae-111">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="a20ae-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a20ae-112">See also</span></span>

- [<span data-ttu-id="a20ae-113">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="a20ae-113">XML Comment Tags</span></span>](index.md)
