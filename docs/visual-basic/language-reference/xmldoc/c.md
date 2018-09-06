---
title: '&lt;c&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 06c6899895f278fdf652725a05ecc7229805f4d4
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "44041127"
---
# <a name="ltcgt-visual-basic"></a><span data-ttu-id="5bd1d-102">&lt;c&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5bd1d-102">&lt;c&gt; (Visual Basic)</span></span>
<span data-ttu-id="5bd1d-103">Indica que el texto dentro de una descripción es código.</span><span class="sxs-lookup"><span data-stu-id="5bd1d-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bd1d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5bd1d-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5bd1d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5bd1d-105">Parameters</span></span>  
  
|<span data-ttu-id="5bd1d-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="5bd1d-106">Parameter</span></span>|<span data-ttu-id="5bd1d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5bd1d-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="5bd1d-108">El texto que le gustaría indicar como código.</span><span class="sxs-lookup"><span data-stu-id="5bd1d-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bd1d-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5bd1d-109">Remarks</span></span>  
 <span data-ttu-id="5bd1d-110">El `<c>` etiqueta ofrece una manera de indicar que el texto dentro de una descripción debe marcarse como código.</span><span class="sxs-lookup"><span data-stu-id="5bd1d-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="5bd1d-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) para indicar varias líneas como código.</span><span class="sxs-lookup"><span data-stu-id="5bd1d-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="5bd1d-112">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="5bd1d-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bd1d-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bd1d-113">Example</span></span>  
 <span data-ttu-id="5bd1d-114">Este ejemplo se usa el `<c>` etiqueta en la sección de resumen para indicar que `Counter` es el código.</span><span class="sxs-lookup"><span data-stu-id="5bd1d-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5bd1d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bd1d-115">See Also</span></span>  
 [<span data-ttu-id="5bd1d-116">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="5bd1d-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
