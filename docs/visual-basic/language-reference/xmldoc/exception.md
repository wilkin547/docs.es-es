---
title: <exception>
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: e3f386d2a1e15ea3e1519d6e1e5e31c34c73fb99
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872905"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="7bec8-101">\<exception> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7bec8-101">\<exception> (Visual Basic)</span></span>

<span data-ttu-id="7bec8-102">Especifica qué excepciones se pueden iniciar.</span><span class="sxs-lookup"><span data-stu-id="7bec8-102">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bec8-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7bec8-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bec8-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7bec8-104">Parameters</span></span>  

 `member`  
 <span data-ttu-id="7bec8-105">Una referencia a una excepción que está disponible desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="7bec8-105">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="7bec8-106">El compilador comprueba si la excepción dada existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="7bec8-106">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="7bec8-107">`member` debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="7bec8-107">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="7bec8-108">Una descripción.</span><span class="sxs-lookup"><span data-stu-id="7bec8-108">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bec8-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7bec8-109">Remarks</span></span>  

 <span data-ttu-id="7bec8-110">Use la `<exception>` etiqueta para especificar qué excepciones se pueden iniciar.</span><span class="sxs-lookup"><span data-stu-id="7bec8-110">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="7bec8-111">Esta etiqueta se aplica a una definición de método.</span><span class="sxs-lookup"><span data-stu-id="7bec8-111">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="7bec8-112">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="7bec8-112">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bec8-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7bec8-113">Example</span></span>  

 <span data-ttu-id="7bec8-114">En este ejemplo se usa la `<exception>` etiqueta para describir una excepción que la `IntDivide` función puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="7bec8-114">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="7bec8-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7bec8-115">See also</span></span>

- [<span data-ttu-id="7bec8-116">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="7bec8-116">XML Comment Tags</span></span>](index.md)
