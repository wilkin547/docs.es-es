---
title: <see> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: e3ae5fb63540e47e5b8da2e2d60d5bd736e019d7
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524658"
---
# <a name="see-visual-basic"></a><span data-ttu-id="527a6-102">\<see > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="527a6-102">\<see> (Visual Basic)</span></span>
<span data-ttu-id="527a6-103">Especifica un vínculo a otro miembro.</span><span class="sxs-lookup"><span data-stu-id="527a6-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="527a6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="527a6-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="527a6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="527a6-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="527a6-106">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="527a6-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="527a6-107">El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.</span><span class="sxs-lookup"><span data-stu-id="527a6-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="527a6-108">`member` debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="527a6-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="527a6-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="527a6-109">Remarks</span></span>  
 <span data-ttu-id="527a6-110">Use la etiqueta `<see>` para especificar un vínculo desde dentro del texto.</span><span class="sxs-lookup"><span data-stu-id="527a6-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="527a6-111">Use [\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) para indicar el texto que desea que aparezca en la sección "vea también".</span><span class="sxs-lookup"><span data-stu-id="527a6-111">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="527a6-112">Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="527a6-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="527a6-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="527a6-113">Example</span></span>  
 <span data-ttu-id="527a6-114">En este ejemplo se usa la etiqueta `<see>` de la sección `UpdateRecord` notas para hacer referencia al método `DoesRecordExist`.</span><span class="sxs-lookup"><span data-stu-id="527a6-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="527a6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="527a6-115">See also</span></span>

- [<span data-ttu-id="527a6-116">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="527a6-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
