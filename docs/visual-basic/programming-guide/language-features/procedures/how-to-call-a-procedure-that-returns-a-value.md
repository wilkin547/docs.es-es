---
title: Procedimiento para llamar a un procedimiento que devuelve un valor
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: 53589f84c6675d1e7ae2a593341e5dac747132a9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91083982"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="42c46-102">Cómo: Llamar a un procedimiento que devuelve un valor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="42c46-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>

<span data-ttu-id="42c46-103">Un `Function` procedimiento devuelve un valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="42c46-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="42c46-104">Para llamarlo, incluya su nombre y sus argumentos en el lado derecho de una instrucción de asignación o en una expresión.</span><span class="sxs-lookup"><span data-stu-id="42c46-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="42c46-105">Para llamar a un procedimiento de función dentro de una expresión</span><span class="sxs-lookup"><span data-stu-id="42c46-105">To call a Function procedure within an expression</span></span>  
  
1. <span data-ttu-id="42c46-106">Use el `Function` nombre del procedimiento del mismo modo que usaría una variable.</span><span class="sxs-lookup"><span data-stu-id="42c46-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="42c46-107">Puede usar una `Function` llamada a procedimiento en cualquier lugar en el que pueda usar una variable o una constante en una expresión.</span><span class="sxs-lookup"><span data-stu-id="42c46-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2. <span data-ttu-id="42c46-108">Siga el nombre del procedimiento entre paréntesis para incluir la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="42c46-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="42c46-109">Si no hay ningún argumento, puede omitir los paréntesis opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="42c46-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="42c46-110">Sin embargo, el uso de los paréntesis facilita la lectura del código.</span><span class="sxs-lookup"><span data-stu-id="42c46-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="42c46-111">Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="42c46-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="42c46-112">Asegúrese de proporcionar los argumentos en el mismo orden en que el `Function` procedimiento define los parámetros correspondientes.</span><span class="sxs-lookup"><span data-stu-id="42c46-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="42c46-113">Como alternativa, puede pasar uno o varios argumentos por nombre.</span><span class="sxs-lookup"><span data-stu-id="42c46-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="42c46-114">Para obtener más información, vea [pasar argumentos por posición y por nombre](./passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="42c46-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4. <span data-ttu-id="42c46-115">El valor devuelto del procedimiento participa en la expresión de la misma forma que el valor de una variable o constante.</span><span class="sxs-lookup"><span data-stu-id="42c46-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="42c46-116">Para llamar a un procedimiento de función en una instrucción de asignación</span><span class="sxs-lookup"><span data-stu-id="42c46-116">To call a Function procedure in an assignment statement</span></span>  
  
1. <span data-ttu-id="42c46-117">Use el `Function` nombre del procedimiento que sigue al `=` signo igual () en la instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="42c46-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2. <span data-ttu-id="42c46-118">Siga el nombre del procedimiento entre paréntesis para incluir la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="42c46-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="42c46-119">Si no hay ningún argumento, puede omitir los paréntesis opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="42c46-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="42c46-120">Sin embargo, el uso de los paréntesis facilita la lectura del código.</span><span class="sxs-lookup"><span data-stu-id="42c46-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="42c46-121">Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="42c46-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="42c46-122">Asegúrese de proporcionar los argumentos en el mismo orden en que el `Function` procedimiento define los parámetros correspondientes, a menos que los pase por nombre.</span><span class="sxs-lookup"><span data-stu-id="42c46-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4. <span data-ttu-id="42c46-123">El valor devuelto del procedimiento se almacena en la variable o la propiedad en el lado izquierdo de la instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="42c46-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42c46-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="42c46-124">Example</span></span>  

 <span data-ttu-id="42c46-125">En el ejemplo siguiente se llama al Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> para recuperar el valor de una variable de entorno del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="42c46-125">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="42c46-126">La primera línea llama a `Environ` dentro de una expresión y la segunda línea la llama en una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="42c46-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> <span data-ttu-id="42c46-127">`Environ` toma el nombre de la variable como su único argumento.</span><span class="sxs-lookup"><span data-stu-id="42c46-127">`Environ` takes the variable name as its sole argument.</span></span> <span data-ttu-id="42c46-128">Devuelve el valor de la variable al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="42c46-128">It returns the variable's value to the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="42c46-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="42c46-129">See also</span></span>

- [<span data-ttu-id="42c46-130">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="42c46-130">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="42c46-131">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="42c46-131">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="42c46-132">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="42c46-132">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="42c46-133">Procedimiento para crear un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="42c46-133">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="42c46-134">Procedimiento para devolver un valor de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="42c46-134">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="42c46-135">Procedimiento apara llamar a un procedimiento que no devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="42c46-135">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
