---
title: '&lt;c&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 556c00fa761a1bce5e922a304706c78893550901
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599611"
---
# <a name="ltcgt-visual-basic"></a><span data-ttu-id="32758-102">&lt;c&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32758-102">&lt;c&gt; (Visual Basic)</span></span>
<span data-ttu-id="32758-103">Indica que el texto de una descripción es código.</span><span class="sxs-lookup"><span data-stu-id="32758-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32758-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="32758-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="32758-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="32758-105">Parameters</span></span>  
  
|<span data-ttu-id="32758-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="32758-106">Parameter</span></span>|<span data-ttu-id="32758-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="32758-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="32758-108">El texto que le gustaría indicar como código.</span><span class="sxs-lookup"><span data-stu-id="32758-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32758-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="32758-109">Remarks</span></span>  
 <span data-ttu-id="32758-110">La `<c>` etiqueta ofrece una manera de indicar que el texto dentro de una descripción se debe marcar como código.</span><span class="sxs-lookup"><span data-stu-id="32758-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="32758-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) para indicar varias líneas como código.</span><span class="sxs-lookup"><span data-stu-id="32758-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="32758-112">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="32758-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32758-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="32758-113">Example</span></span>  
 <span data-ttu-id="32758-114">Este ejemplo se utiliza la `<c>` etiqueta en la sección de resumen para indicar que `Counter` es el código.</span><span class="sxs-lookup"><span data-stu-id="32758-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="32758-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="32758-115">See Also</span></span>  
 [<span data-ttu-id="32758-116">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="32758-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
