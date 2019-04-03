---
title: "'As Any' no se admite en instrucciones 'Declare'"
ms.date: 07/20/2015
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
ms.openlocfilehash: c6c792e02bb655dc8a9544c4b5b46a64210556f6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839930"
---
# <a name="as-any-is-not-supported-in-declare-statements"></a><span data-ttu-id="b69e1-102">'As Any' no se admite en instrucciones 'Declare'</span><span class="sxs-lookup"><span data-stu-id="b69e1-102">'As Any' is not supported in 'Declare' statements</span></span>
<span data-ttu-id="b69e1-103">El `Any` se utilizó el tipo de datos con `Declare` instrucciones en Visual Basic 6.0 y versiones anteriores para permitir el uso de argumentos que puede contener cualquier tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="b69e1-103">The `Any` data type was used with `Declare` statements in Visual Basic 6.0 and earlier versions to permit the use of arguments that could contain any type of data.</span></span> <span data-ttu-id="b69e1-104">Visual Basic admite sobrecargas, sin embargo y por lo que facilita la `Any` obsoleto del tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="b69e1-104">Visual Basic supports overloading, however, and so makes the `Any` data type obsolete.</span></span>  
  
 <span data-ttu-id="b69e1-105">**Identificador de error:** BC30828</span><span class="sxs-lookup"><span data-stu-id="b69e1-105">**Error ID:** BC30828</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b69e1-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="b69e1-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="b69e1-107">Declare los parámetros del tipo específico que desea usar; Por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b69e1-107">Declare parameters of the specific type you want to use; for example.</span></span>  
  
     [!code-vb[VbVbalrStatements#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class5.vb#95)]  
  
2.  <span data-ttu-id="b69e1-108">Use la <xref:System.Runtime.InteropServices.MarshalAsAttribute> atributo para especificar `As Any` cuando `Void*` se espera que el procedimiento que se llama.</span><span class="sxs-lookup"><span data-stu-id="b69e1-108">Use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to specify `As Any` when `Void*` is expected by the procedure being called.</span></span>  
  
     [!code-vb[VbVbalrStatements#96](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class5.vb#96)]  
  
## <a name="see-also"></a><span data-ttu-id="b69e1-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="b69e1-109">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="b69e1-110">Tutorial: Llamar a las API de Windows</span><span class="sxs-lookup"><span data-stu-id="b69e1-110">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="b69e1-111">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b69e1-111">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="b69e1-112">Crear prototipos en código administrado</span><span class="sxs-lookup"><span data-stu-id="b69e1-112">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)
