---
description: 'Más información acerca de cómo: llamar a un procedimiento sobrecargado (Visual Basic)'
title: Procedimiento para llamar a un procedimiento sobrecargado
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: 6a67a598bd4a42964fd8fc01bc22b1b919f5e2a9
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472597"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a><span data-ttu-id="3a28e-103">Cómo: Llamar a un procedimiento sobrecargado (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a28e-103">How to: Call an Overloaded Procedure (Visual Basic)</span></span>

<span data-ttu-id="3a28e-104">La ventaja de sobrecargar un procedimiento es la flexibilidad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3a28e-104">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="3a28e-105">El código de llamada puede obtener la información que necesita para pasar al procedimiento y, a continuación, llamar a un nombre de procedimiento único, independientemente de los argumentos que pase.</span><span class="sxs-lookup"><span data-stu-id="3a28e-105">The calling code can obtain the information it needs to pass to the procedure and then call a single procedure name, no matter what arguments it is passing.</span></span>  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a><span data-ttu-id="3a28e-106">Para llamar a un procedimiento que tiene más de una versión definida</span><span class="sxs-lookup"><span data-stu-id="3a28e-106">To call a procedure that has more than one version defined</span></span>  
  
1. <span data-ttu-id="3a28e-107">En el código de llamada, determine qué datos se van a pasar al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="3a28e-107">In the calling code, determine which data to pass to the procedure.</span></span>  
  
2. <span data-ttu-id="3a28e-108">Escriba la llamada a procedimiento de la manera normal y presente los datos en la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="3a28e-108">Write the procedure call in the normal way, presenting the data in the argument list.</span></span> <span data-ttu-id="3a28e-109">Asegúrese de que los argumentos coincidan con la lista de parámetros en una de las versiones definidas para el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="3a28e-109">Be sure the arguments match the parameter list in one of the versions defined for the procedure.</span></span>  
  
3. <span data-ttu-id="3a28e-110">No es necesario determinar la versión del procedimiento que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="3a28e-110">You do not have to determine which version of the procedure to call.</span></span> <span data-ttu-id="3a28e-111">Visual Basic pasa el control a la versión que coincida con la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="3a28e-111">Visual Basic passes control to the version matching your argument list.</span></span>  
  
     <span data-ttu-id="3a28e-112">En el ejemplo siguiente se llama al `post` procedimiento declarado en [Cómo: definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="3a28e-112">The following example calls the `post` procedure declared in [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span></span> <span data-ttu-id="3a28e-113">Obtiene la identificación del cliente, determina si es `String` o `Integer` , y, en cualquier caso, llama al mismo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="3a28e-113">It obtains the customer identification, determines whether it is a `String` or an `Integer`, and then in either case calls the same procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
     [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a><span data-ttu-id="3a28e-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3a28e-114">See also</span></span>

- [<span data-ttu-id="3a28e-115">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="3a28e-115">Procedures</span></span>](./index.md)
- [<span data-ttu-id="3a28e-116">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="3a28e-116">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="3a28e-117">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="3a28e-117">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="3a28e-118">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="3a28e-118">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="3a28e-119">Procedimiento para definir varias versiones de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="3a28e-119">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="3a28e-120">Procedimiento para sobrecargar un procedimiento que toma parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="3a28e-120">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="3a28e-121">Procedimiento para sobrecargar un procedimiento que toma un número indefinido de parámetros</span><span class="sxs-lookup"><span data-stu-id="3a28e-121">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="3a28e-122">Consideraciones sobre la sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="3a28e-122">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="3a28e-123">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="3a28e-123">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="3a28e-124">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="3a28e-124">Overloads</span></span>](../../../language-reference/modifiers/overloads.md)
