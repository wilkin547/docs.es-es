---
title: '&lt;seealso&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: a792bbea108bcdf33d430c47773466ef3dccdb0c
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43880502"
---
# <a name="ltseealsogt-visual-basic"></a><span data-ttu-id="04825-102">&lt;seealso&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04825-102">&lt;seealso&gt; (Visual Basic)</span></span>
<span data-ttu-id="04825-103">Especifica un vínculo que aparece en la sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="04825-103">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04825-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04825-104">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04825-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="04825-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="04825-106">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="04825-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="04825-107">El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.</span><span class="sxs-lookup"><span data-stu-id="04825-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="04825-108">`member` debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="04825-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04825-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="04825-109">Remarks</span></span>  
 <span data-ttu-id="04825-110">Use la `<seealso>` etiqueta para especificar el texto que desea que aparezca en una sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="04825-110">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="04825-111">Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) para especificar un vínculo desde dentro del texto.</span><span class="sxs-lookup"><span data-stu-id="04825-111">Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="04825-112">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="04825-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04825-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04825-113">Example</span></span>  
 <span data-ttu-id="04825-114">Este ejemplo se usa el `<seealso>` etiquetar en el `DoesRecordExist` comentarios la sección para hacer referencia a la `UpdateRecord` método.</span><span class="sxs-lookup"><span data-stu-id="04825-114">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/seealso_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="04825-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="04825-115">See Also</span></span>  
 [<span data-ttu-id="04825-116">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="04825-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
