---
title: <see>
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 3c149b8ff60bcc2aba06856ad95f461fb18da4b6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352228"
---
# <a name="see-visual-basic"></a><span data-ttu-id="2fec4-101">\<Ver > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2fec4-101">\<see> (Visual Basic)</span></span>
<span data-ttu-id="2fec4-102">Especifica un vínculo a otro miembro.</span><span class="sxs-lookup"><span data-stu-id="2fec4-102">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fec4-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2fec4-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fec4-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2fec4-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="2fec4-105">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="2fec4-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="2fec4-106">El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.</span><span class="sxs-lookup"><span data-stu-id="2fec4-106">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="2fec4-107">`member` debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="2fec4-107">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fec4-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2fec4-108">Remarks</span></span>  
 <span data-ttu-id="2fec4-109">Use la etiqueta `<see>` para especificar un vínculo desde dentro del texto.</span><span class="sxs-lookup"><span data-stu-id="2fec4-109">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="2fec4-110">Use [\<> seeAlso](../../../visual-basic/language-reference/xmldoc/seealso.md) para indicar el texto que desea que aparezca en la sección "vea también".</span><span class="sxs-lookup"><span data-stu-id="2fec4-110">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="2fec4-111">Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="2fec4-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fec4-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2fec4-112">Example</span></span>  
 <span data-ttu-id="2fec4-113">En este ejemplo se usa la etiqueta `<see>` de la sección `UpdateRecord` notas para hacer referencia al método `DoesRecordExist`.</span><span class="sxs-lookup"><span data-stu-id="2fec4-113">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="2fec4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2fec4-114">See also</span></span>

- [<span data-ttu-id="2fec4-115">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="2fec4-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
