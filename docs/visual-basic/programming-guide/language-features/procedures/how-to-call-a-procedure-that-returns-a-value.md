---
title: Filtrar Llamar a un procedimiento que devuelve un valor (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: 6f45f01489ee84b6addb1f7c7c8dc584332f38dd
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59333891"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="fc7e5-102">Filtrar Llamar a un procedimiento que devuelve un valor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc7e5-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="fc7e5-103">Un `Function` procedimiento devuelve un valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="fc7e5-104">Llamarlo mediante la inclusión de su nombre y argumentos en el lado derecho de una instrucción de asignación o en una expresión.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="fc7e5-105">Para llamar a un procedimiento Function dentro de una expresión</span><span class="sxs-lookup"><span data-stu-id="fc7e5-105">To call a Function procedure within an expression</span></span>  
  
1. <span data-ttu-id="fc7e5-106">Utilice la `Function` del mismo modo que usaría una variable de nombre de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="fc7e5-107">Puede usar un `Function` llame al procedimiento desde cualquier lugar puede usar una variable o constante en una expresión.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2. <span data-ttu-id="fc7e5-108">Siga el nombre del procedimiento con paréntesis para delimitar la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="fc7e5-109">Si no hay ningún argumento, opcionalmente, puede omitir los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="fc7e5-110">Sin embargo, el uso de los paréntesis hace que el código más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="fc7e5-111">Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="fc7e5-112">Asegúrese de proporcionar los argumentos en el mismo orden que el `Function` procedimiento define los parámetros correspondientes.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="fc7e5-113">Como alternativa, puede pasar uno o más argumentos por nombre.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="fc7e5-114">Para obtener más información, consulte [pasar argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="fc7e5-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4. <span data-ttu-id="fc7e5-115">El valor devuelto del procedimiento participa en la expresión igual que el valor de una variable o constante.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="fc7e5-116">Para llamar a un procedimiento Function en una instrucción de asignación</span><span class="sxs-lookup"><span data-stu-id="fc7e5-116">To call a Function procedure in an assignment statement</span></span>  
  
1. <span data-ttu-id="fc7e5-117">Use la `Function` nombre del procedimiento siguiendo la igual (`=`) inicie sesión en la instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2. <span data-ttu-id="fc7e5-118">Siga el nombre del procedimiento con paréntesis para delimitar la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="fc7e5-119">Si no hay ningún argumento, opcionalmente, puede omitir los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="fc7e5-120">Sin embargo, el uso de los paréntesis hace que el código más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="fc7e5-121">Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="fc7e5-122">Asegúrese de proporcionar los argumentos en el mismo orden que el `Function` procedimiento define los parámetros correspondientes, a menos que se pasan por nombre.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4. <span data-ttu-id="fc7e5-123">El valor devuelto del procedimiento se almacena en la variable o propiedad en el lado izquierdo de la instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc7e5-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc7e5-124">Example</span></span>  
 <span data-ttu-id="fc7e5-125">El ejemplo siguiente se llama a la de Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> para recuperar el valor de una variable de entorno del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-125">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="fc7e5-126">Las llamadas de línea primera `Environ` dentro de una expresión y la segunda línea lo llama en una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> `Environ` <span data-ttu-id="fc7e5-127">toma el nombre de variable como su único argumento.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-127">takes the variable name as its sole argument.</span></span> <span data-ttu-id="fc7e5-128">Devuelve el valor de la variable al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="fc7e5-128">It returns the variable's value to the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="fc7e5-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc7e5-129">See also</span></span>

- [<span data-ttu-id="fc7e5-130">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="fc7e5-130">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="fc7e5-131">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="fc7e5-131">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="fc7e5-132">Function (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="fc7e5-132">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="fc7e5-133">Filtrar para crear un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="fc7e5-133">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="fc7e5-134">Filtrar para devolver un valor de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="fc7e5-134">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="fc7e5-135">Filtrar apara llamar a un procedimiento que no devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="fc7e5-135">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
