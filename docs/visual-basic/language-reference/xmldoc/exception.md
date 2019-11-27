---
title: <exception>
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: e1e7f2d0fb06599f83ba224ed52a10429d9b11fe
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346960"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="a2d74-101">\<> de excepciones (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2d74-101">\<exception> (Visual Basic)</span></span>
<span data-ttu-id="a2d74-102">Especifica qué excepciones se pueden iniciar.</span><span class="sxs-lookup"><span data-stu-id="a2d74-102">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2d74-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a2d74-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2d74-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a2d74-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="a2d74-105">Una referencia a una excepción que está disponible desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="a2d74-105">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="a2d74-106">El compilador comprueba si la excepción dada existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="a2d74-106">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="a2d74-107">`member` debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="a2d74-107">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="a2d74-108">Una descripción.</span><span class="sxs-lookup"><span data-stu-id="a2d74-108">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2d74-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a2d74-109">Remarks</span></span>  
 <span data-ttu-id="a2d74-110">Use la etiqueta `<exception>` para especificar qué excepciones se pueden iniciar.</span><span class="sxs-lookup"><span data-stu-id="a2d74-110">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="a2d74-111">Esta etiqueta se aplica a una definición de método.</span><span class="sxs-lookup"><span data-stu-id="a2d74-111">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="a2d74-112">Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="a2d74-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2d74-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a2d74-113">Example</span></span>  
 <span data-ttu-id="a2d74-114">En este ejemplo se usa la etiqueta `<exception>` para describir una excepción que la función `IntDivide` puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="a2d74-114">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="a2d74-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2d74-115">See also</span></span>

- [<span data-ttu-id="a2d74-116">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="a2d74-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
