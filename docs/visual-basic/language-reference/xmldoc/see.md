---
title: '&lt;consulte&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 78311651593d3d4a47c723f64a9a74d4660f7c90
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44248883"
---
# <a name="ltseegt-visual-basic"></a><span data-ttu-id="6f561-102">&lt;consulte&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f561-102">&lt;see&gt; (Visual Basic)</span></span>
<span data-ttu-id="6f561-103">Especifica un vínculo a otro miembro.</span><span class="sxs-lookup"><span data-stu-id="6f561-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f561-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f561-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6f561-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6f561-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="6f561-106">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="6f561-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="6f561-107">El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.</span><span class="sxs-lookup"><span data-stu-id="6f561-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="6f561-108">`member` debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="6f561-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f561-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6f561-109">Remarks</span></span>  
 <span data-ttu-id="6f561-110">Use la `<see>` etiqueta para especificar un vínculo desde dentro del texto.</span><span class="sxs-lookup"><span data-stu-id="6f561-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="6f561-111">Use [ \<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) para indicar el texto que desea que aparezca en una sección "Vea también".</span><span class="sxs-lookup"><span data-stu-id="6f561-111">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="6f561-112">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="6f561-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f561-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f561-113">Example</span></span>  
 <span data-ttu-id="6f561-114">Este ejemplo se usa el `<see>` etiquetar en el `UpdateRecord` comentarios la sección para hacer referencia a la `DoesRecordExist` método.</span><span class="sxs-lookup"><span data-stu-id="6f561-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/see_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6f561-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f561-115">See Also</span></span>  
 [<span data-ttu-id="6f561-116">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="6f561-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
