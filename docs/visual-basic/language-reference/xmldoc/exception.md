---
title: <exception> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 157287ce5c85ec51f1711934cf9a5e4f568957ef
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977193"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="006f6-102">\<excepción > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="006f6-102">\<exception> (Visual Basic)</span></span>
<span data-ttu-id="006f6-103">Especifica qué excepciones se pueden producir.</span><span class="sxs-lookup"><span data-stu-id="006f6-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="006f6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="006f6-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="006f6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="006f6-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="006f6-106">Una referencia a una excepción que está disponible desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="006f6-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="006f6-107">El compilador comprueba si la excepción dada existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="006f6-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="006f6-108">`member` debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="006f6-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="006f6-109">Una descripción.</span><span class="sxs-lookup"><span data-stu-id="006f6-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="006f6-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="006f6-110">Remarks</span></span>  
 <span data-ttu-id="006f6-111">Use la `<exception>` etiqueta para especificar qué excepciones se pueden producir.</span><span class="sxs-lookup"><span data-stu-id="006f6-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="006f6-112">Esta etiqueta se aplica a una definición de método.</span><span class="sxs-lookup"><span data-stu-id="006f6-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="006f6-113">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="006f6-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="006f6-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="006f6-114">Example</span></span>  
 <span data-ttu-id="006f6-115">Este ejemplo se usa el `<exception>` etiquetas para describir una excepción que el `IntDivide` función puede producir.</span><span class="sxs-lookup"><span data-stu-id="006f6-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="006f6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="006f6-116">See also</span></span>
- [<span data-ttu-id="006f6-117">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="006f6-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
