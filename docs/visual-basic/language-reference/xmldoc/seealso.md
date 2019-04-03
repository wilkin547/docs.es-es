---
title: <seealso> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: 0df999ef502bf61bdfb65cb472947b93efded36e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58823485"
---
# <a name="seealso-visual-basic"></a><span data-ttu-id="31463-102">\<seealso > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31463-102">\<seealso> (Visual Basic)</span></span>
<span data-ttu-id="31463-103">Especifica un vínculo que aparece en la sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="31463-103">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31463-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31463-104">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="31463-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="31463-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="31463-106">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="31463-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="31463-107">El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.</span><span class="sxs-lookup"><span data-stu-id="31463-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="31463-108">`member` debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="31463-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31463-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="31463-109">Remarks</span></span>  
 <span data-ttu-id="31463-110">Use la `<seealso>` etiqueta para especificar el texto que desea que aparezca en una sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="31463-110">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="31463-111">Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) para especificar un vínculo desde dentro del texto.</span><span class="sxs-lookup"><span data-stu-id="31463-111">Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="31463-112">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="31463-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31463-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="31463-113">Example</span></span>  
 <span data-ttu-id="31463-114">Este ejemplo se usa el `<seealso>` etiquetar en el `DoesRecordExist` comentarios la sección para hacer referencia a la `UpdateRecord` método.</span><span class="sxs-lookup"><span data-stu-id="31463-114">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="31463-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="31463-115">See also</span></span>

- [<span data-ttu-id="31463-116">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="31463-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
