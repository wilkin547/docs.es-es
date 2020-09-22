---
title: <seealso>
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: f435fa2ab86d81053cd185f5d90ec22996a1458d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869419"
---
# <a name="seealso-visual-basic"></a><span data-ttu-id="66c55-101">\<seealso> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66c55-101">\<seealso> (Visual Basic)</span></span>

<span data-ttu-id="66c55-102">Especifica un vínculo que aparece en la sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="66c55-102">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66c55-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66c55-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="66c55-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="66c55-104">Parameters</span></span>  

 `member`  
 <span data-ttu-id="66c55-105">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="66c55-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="66c55-106">El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.</span><span class="sxs-lookup"><span data-stu-id="66c55-106">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="66c55-107">`member` debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="66c55-107">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66c55-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="66c55-108">Remarks</span></span>  

 <span data-ttu-id="66c55-109">Use la `<seealso>` etiqueta para especificar el texto que desea que aparezca en la sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="66c55-109">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="66c55-110">Use [\<see>](see.md) para especificar un vínculo desde dentro del texto.</span><span class="sxs-lookup"><span data-stu-id="66c55-110">Use [\<see>](see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="66c55-111">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="66c55-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66c55-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="66c55-112">Example</span></span>  

 <span data-ttu-id="66c55-113">En este ejemplo se usa la `<seealso>` etiqueta de la `DoesRecordExist` sección Comentarios para hacer referencia al `UpdateRecord` método.</span><span class="sxs-lookup"><span data-stu-id="66c55-113">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="66c55-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66c55-114">See also</span></span>

- [<span data-ttu-id="66c55-115">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="66c55-115">XML Comment Tags</span></span>](index.md)
