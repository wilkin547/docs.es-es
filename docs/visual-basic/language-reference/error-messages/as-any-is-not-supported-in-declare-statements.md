---
title: '&#39;Como cualquier&#39; no se admite en &#39;Declare&#39; instrucciones'
ms.date: 07/20/2015
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
ms.openlocfilehash: 34beaeb7178645d5a167d1b7b969bb3e4f500e1a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588231"
---
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a><span data-ttu-id="0fbc8-102">&#39;Como cualquier&#39; no se admite en &#39;Declare&#39; instrucciones</span><span class="sxs-lookup"><span data-stu-id="0fbc8-102">&#39;As Any&#39; is not supported in &#39;Declare&#39; statements</span></span>
<span data-ttu-id="0fbc8-103">El `Any` tipo de datos se usó con `Declare` instrucciones en Visual Basic 6.0 y versiones anteriores para permitir el uso de argumentos que puede contener cualquier tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-103">The `Any` data type was used with `Declare` statements in Visual Basic 6.0 and earlier versions to permit the use of arguments that could contain any type of data.</span></span> <span data-ttu-id="0fbc8-104">Visual Basic admite sobrecarga, sin embargo y por lo que facilita la `Any` obsoleta del tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-104">Visual Basic supports overloading, however, and so makes the `Any` data type obsolete.</span></span>  
  
 <span data-ttu-id="0fbc8-105">**Id. de error:** BC30828</span><span class="sxs-lookup"><span data-stu-id="0fbc8-105">**Error ID:** BC30828</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0fbc8-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="0fbc8-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="0fbc8-107">Declare los parámetros del tipo específico que desea usar; Por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-107">Declare parameters of the specific type you want to use; for example.</span></span>  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  <span data-ttu-id="0fbc8-108">Use la <xref:System.Runtime.InteropServices.MarshalAsAttribute> atributo para especificar `As Any` cuando `Void*` se espera que el procedimiento que se llama.</span><span class="sxs-lookup"><span data-stu-id="0fbc8-108">Use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to specify `As Any` when `Void*` is expected by the procedure being called.</span></span>  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0fbc8-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fbc8-109">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="0fbc8-110">Tutorial: Llamar a las API de Windows</span><span class="sxs-lookup"><span data-stu-id="0fbc8-110">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [<span data-ttu-id="0fbc8-111">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="0fbc8-111">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="0fbc8-112">Crear prototipos en código administrado</span><span class="sxs-lookup"><span data-stu-id="0fbc8-112">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)
