---
title: <exception> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 16ffb4f6b57dabb3650376c913a7d7608a00646d
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523922"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="c578a-102">\<exception > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c578a-102">\<exception> (Visual Basic)</span></span>
<span data-ttu-id="c578a-103">Especifica qué excepciones se pueden iniciar.</span><span class="sxs-lookup"><span data-stu-id="c578a-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c578a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c578a-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="c578a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c578a-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="c578a-106">Una referencia a una excepción que está disponible desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="c578a-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="c578a-107">El compilador comprueba si la excepción dada existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="c578a-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="c578a-108">`member` debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="c578a-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="c578a-109">Una descripción.</span><span class="sxs-lookup"><span data-stu-id="c578a-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c578a-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c578a-110">Remarks</span></span>  
 <span data-ttu-id="c578a-111">Use la etiqueta `<exception>` para especificar qué excepciones se pueden iniciar.</span><span class="sxs-lookup"><span data-stu-id="c578a-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="c578a-112">Esta etiqueta se aplica a una definición de método.</span><span class="sxs-lookup"><span data-stu-id="c578a-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="c578a-113">Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="c578a-113">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c578a-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c578a-114">Example</span></span>  
 <span data-ttu-id="c578a-115">En este ejemplo se usa la etiqueta `<exception>` para describir una excepción que la función `IntDivide` puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="c578a-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="c578a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c578a-116">See also</span></span>

- [<span data-ttu-id="c578a-117">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="c578a-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
