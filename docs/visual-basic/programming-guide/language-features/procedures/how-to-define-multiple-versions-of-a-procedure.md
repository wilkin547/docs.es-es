---
description: 'Más información acerca de cómo: definir varias versiones de un procedimiento (Visual Basic)'
title: Procedimiento para definir varias versiones de un procedimiento
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: 4b470e478c22c3a827f71b9b28056e16d6d9b7cd
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100456034"
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a><span data-ttu-id="29439-103">Cómo: Definir varias versiones de un procedimiento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="29439-103">How to: Define Multiple Versions of a Procedure (Visual Basic)</span></span>

<span data-ttu-id="29439-104">Puede definir un procedimiento en varias versiones si lo *sobrecarga* , con el mismo nombre, pero con una lista de parámetros diferente para cada versión.</span><span class="sxs-lookup"><span data-stu-id="29439-104">You can define a procedure in multiple versions by *overloading* it, using the same name but a different parameter list for each version.</span></span> <span data-ttu-id="29439-105">El propósito de la sobrecarga es definir varias versiones estrechamente relacionadas de un procedimiento sin tener que diferenciarlas por nombre.</span><span class="sxs-lookup"><span data-stu-id="29439-105">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span>  
  
 <span data-ttu-id="29439-106">Para obtener más información, consulta [Procedure Overloading](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="29439-106">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a><span data-ttu-id="29439-107">Para definir varias versiones de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="29439-107">To define multiple versions of a procedure</span></span>  
  
1. <span data-ttu-id="29439-108">Escriba una `Sub` `Function` instrucción de declaración o para cada versión del procedimiento que desee definir.</span><span class="sxs-lookup"><span data-stu-id="29439-108">Write a `Sub` or `Function` declaration statement for each version of the procedure you want to define.</span></span> <span data-ttu-id="29439-109">Use el mismo nombre de procedimiento en cada declaración.</span><span class="sxs-lookup"><span data-stu-id="29439-109">Use the same procedure name in every declaration.</span></span>  
  
2. <span data-ttu-id="29439-110">Anteponga la `Sub` `Function` palabra clave o en cada declaración con la palabra clave [Overloads](../../../language-reference/modifiers/overloads.md) .</span><span class="sxs-lookup"><span data-stu-id="29439-110">Precede the `Sub` or `Function` keyword in each declaration with the [Overloads](../../../language-reference/modifiers/overloads.md) keyword.</span></span> <span data-ttu-id="29439-111">Opcionalmente, puede omitir `Overloads` en las declaraciones, pero si la incluye en cualquiera de las declaraciones, debe incluirla en cada declaración.</span><span class="sxs-lookup"><span data-stu-id="29439-111">You can optionally omit `Overloads` in the declarations, but if you include it in any of the declarations, you must include it in every declaration.</span></span>  
  
3. <span data-ttu-id="29439-112">Después de cada instrucción de declaración, escriba el código de procedimiento para controlar el caso concreto en el que el código de llamada proporciona argumentos que coinciden con la lista de parámetros de la versión.</span><span class="sxs-lookup"><span data-stu-id="29439-112">Following each declaration statement, write procedure code to handle the specific case where the calling code supplies arguments matching that version's parameter list.</span></span> <span data-ttu-id="29439-113">No es necesario comprobar los parámetros que ha proporcionado el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="29439-113">You do not have to test for which parameters the calling code has supplied.</span></span> <span data-ttu-id="29439-114">Visual Basic pasa el control a la versión correspondiente del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="29439-114">Visual Basic passes control to the matching version of your procedure.</span></span>  
  
4. <span data-ttu-id="29439-115">Finalice cada versión del procedimiento con la `End Sub` instrucción o `End Function` según corresponda.</span><span class="sxs-lookup"><span data-stu-id="29439-115">Terminate each version of the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29439-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="29439-116">Example</span></span>  

 <span data-ttu-id="29439-117">En el ejemplo siguiente se define un `Sub` procedimiento para publicar una transacción en el saldo de un cliente.</span><span class="sxs-lookup"><span data-stu-id="29439-117">The following example defines a `Sub` procedure to post a transaction against a customer's balance.</span></span> <span data-ttu-id="29439-118">Usa la `Overloads` palabra clave para definir dos versiones del procedimiento, una que acepta el cliente por nombre y la otra por número de cuenta.</span><span class="sxs-lookup"><span data-stu-id="29439-118">It uses the `Overloads` keyword to define two versions of the procedure, one that accepts the customer by name and the other by account number.</span></span>  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
 <span data-ttu-id="29439-119">El código de llamada puede obtener la identificación del cliente como `String` o `Integer` y, a continuación, utilizar la misma instrucción de llamada en cualquier caso.</span><span class="sxs-lookup"><span data-stu-id="29439-119">The calling code can obtain the customer identification as either a `String` or an `Integer`, and then use the same calling statement in either case.</span></span>  
  
 <span data-ttu-id="29439-120">Para obtener información sobre cómo llamar a estas versiones del `post` procedimiento, vea [Cómo: llamar a un procedimiento sobrecargado](./how-to-call-an-overloaded-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="29439-120">For information on how to call these versions of the `post` procedure, see [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md).</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="29439-121">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="29439-121">Compile the code</span></span>  

 <span data-ttu-id="29439-122">Asegúrese de que cada una de las versiones sobrecargadas tiene el mismo nombre de procedimiento pero una lista de parámetros diferente.</span><span class="sxs-lookup"><span data-stu-id="29439-122">Make sure each of your overloaded versions has the same procedure name but a different parameter list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29439-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="29439-123">See also</span></span>

- [<span data-ttu-id="29439-124">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="29439-124">Procedures</span></span>](./index.md)
- [<span data-ttu-id="29439-125">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="29439-125">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="29439-126">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="29439-126">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="29439-127">Procedimiento para sobrecargar un procedimiento que toma parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="29439-127">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="29439-128">Procedimiento para sobrecargar un procedimiento que toma un número indefinido de parámetros</span><span class="sxs-lookup"><span data-stu-id="29439-128">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="29439-129">Consideraciones sobre la sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="29439-129">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="29439-130">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="29439-130">Overload Resolution</span></span>](./overload-resolution.md)
