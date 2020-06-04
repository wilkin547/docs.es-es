---
title: <seealso>
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: 5999a4ebcc90f21ee8331b96ffb2a50f7905b1b6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411517"
---
# <a name="seealso-visual-basic"></a><span data-ttu-id="3130e-101">\<seealso> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3130e-101">\<seealso> (Visual Basic)</span></span>
<span data-ttu-id="3130e-102">Especifica un vínculo que aparece en la sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="3130e-102">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3130e-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3130e-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="3130e-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3130e-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="3130e-105">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="3130e-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="3130e-106">El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.</span><span class="sxs-lookup"><span data-stu-id="3130e-106">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="3130e-107">`member` debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="3130e-107">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3130e-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3130e-108">Remarks</span></span>  
 <span data-ttu-id="3130e-109">Use la `<seealso>` etiqueta para especificar el texto que desea que aparezca en la sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="3130e-109">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="3130e-110">[\<see>](see.md)Se usa para especificar un vínculo desde dentro del texto.</span><span class="sxs-lookup"><span data-stu-id="3130e-110">Use [\<see>](see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="3130e-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.</span><span class="sxs-lookup"><span data-stu-id="3130e-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3130e-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3130e-112">Example</span></span>  
 <span data-ttu-id="3130e-113">En este ejemplo se usa la `<seealso>` etiqueta de la `DoesRecordExist` sección Comentarios para hacer referencia al `UpdateRecord` método.</span><span class="sxs-lookup"><span data-stu-id="3130e-113">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="3130e-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3130e-114">See also</span></span>

- [<span data-ttu-id="3130e-115">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="3130e-115">XML Comment Tags</span></span>](index.md)
