---
title: <see>
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 51eaaef2ddb88afbb52ab58b85ed1a58ba251c1e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866452"
---
# <a name="see-visual-basic"></a><span data-ttu-id="55b8a-101">\<see> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55b8a-101">\<see> (Visual Basic)</span></span>

<span data-ttu-id="55b8a-102">Especifica un vínculo a otro miembro.</span><span class="sxs-lookup"><span data-stu-id="55b8a-102">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55b8a-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55b8a-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="55b8a-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="55b8a-104">Parameters</span></span>  

 `member`  
 <span data-ttu-id="55b8a-105">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="55b8a-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="55b8a-106">El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.</span><span class="sxs-lookup"><span data-stu-id="55b8a-106">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="55b8a-107">`member` debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="55b8a-107">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55b8a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="55b8a-108">Remarks</span></span>  

 <span data-ttu-id="55b8a-109">Use la `<see>` etiqueta para especificar un vínculo desde dentro del texto.</span><span class="sxs-lookup"><span data-stu-id="55b8a-109">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="55b8a-110">Use [\<seealso>](seealso.md) para indicar el texto que desea que aparezca en la sección "vea también".</span><span class="sxs-lookup"><span data-stu-id="55b8a-110">Use [\<seealso>](seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="55b8a-111">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="55b8a-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55b8a-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="55b8a-112">Example</span></span>  

 <span data-ttu-id="55b8a-113">En este ejemplo se usa la `<see>` etiqueta de la `UpdateRecord` sección Comentarios para hacer referencia al `DoesRecordExist` método.</span><span class="sxs-lookup"><span data-stu-id="55b8a-113">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="55b8a-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="55b8a-114">See also</span></span>

- [<span data-ttu-id="55b8a-115">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="55b8a-115">XML Comment Tags</span></span>](index.md)
