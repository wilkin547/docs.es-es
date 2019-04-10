---
title: Filtrar Llamar a un procedimiento sobrecargado (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: d325c09516b4ce03facedce86f17ea49480b997a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59317816"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a><span data-ttu-id="ca78a-102">Filtrar Llamar a un procedimiento sobrecargado (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca78a-102">How to: Call an Overloaded Procedure (Visual Basic)</span></span>
<span data-ttu-id="ca78a-103">La ventaja de sobrecargar un procedimiento es en la flexibilidad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ca78a-103">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="ca78a-104">El código de llamada puede obtener la información que necesita para pasar al procedimiento y, a continuación, llamar a un único nombre de procedimiento, independientemente de los argumentos está pasando.</span><span class="sxs-lookup"><span data-stu-id="ca78a-104">The calling code can obtain the information it needs to pass to the procedure and then call a single procedure name, no matter what arguments it is passing.</span></span>  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a><span data-ttu-id="ca78a-105">Llamar a un procedimiento que tiene más de una versión definida</span><span class="sxs-lookup"><span data-stu-id="ca78a-105">To call a procedure that has more than one version defined</span></span>  
  
1. <span data-ttu-id="ca78a-106">En el código que realiza la llamada, determine qué datos se deben pasar al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ca78a-106">In the calling code, determine which data to pass to the procedure.</span></span>  
  
2. <span data-ttu-id="ca78a-107">Escribir la llamada al procedimiento de la manera normal, presentación de datos en la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="ca78a-107">Write the procedure call in the normal way, presenting the data in the argument list.</span></span> <span data-ttu-id="ca78a-108">Asegúrese de que los argumentos coinciden con la lista de parámetros en una de las versiones definidas para el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ca78a-108">Be sure the arguments match the parameter list in one of the versions defined for the procedure.</span></span>  
  
3. <span data-ttu-id="ca78a-109">No es necesario que determinar qué versión del procedimiento para llamar a.</span><span class="sxs-lookup"><span data-stu-id="ca78a-109">You do not have to determine which version of the procedure to call.</span></span> <span data-ttu-id="ca78a-110">Visual Basic pasa el control a la versión que coincida con la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="ca78a-110">Visual Basic passes control to the version matching your argument list.</span></span>  
  
     <span data-ttu-id="ca78a-111">El ejemplo siguiente se llama el `post` procedimiento declarado en [Cómo: Definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="ca78a-111">The following example calls the `post` procedure declared in [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span></span> <span data-ttu-id="ca78a-112">Obtiene la identificación del cliente, se determina si es un `String` o `Integer`y, a continuación, en cualquier caso, llama el mismo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ca78a-112">It obtains the customer identification, determines whether it is a `String` or an `Integer`, and then in either case calls the same procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
     [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a><span data-ttu-id="ca78a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca78a-113">See also</span></span>

- [<span data-ttu-id="ca78a-114">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="ca78a-114">Procedures</span></span>](./index.md)
- [<span data-ttu-id="ca78a-115">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="ca78a-115">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="ca78a-116">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="ca78a-116">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="ca78a-117">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="ca78a-117">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="ca78a-118">Filtrar para definir varias versiones de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="ca78a-118">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="ca78a-119">Filtrar para sobrecargar un procedimiento que toma parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="ca78a-119">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="ca78a-120">Filtrar para sobrecargar un procedimiento que toma un número indefinido de parámetros</span><span class="sxs-lookup"><span data-stu-id="ca78a-120">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="ca78a-121">Consideraciones sobre la sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="ca78a-121">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="ca78a-122">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="ca78a-122">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="ca78a-123">Overloads</span><span class="sxs-lookup"><span data-stu-id="ca78a-123">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
