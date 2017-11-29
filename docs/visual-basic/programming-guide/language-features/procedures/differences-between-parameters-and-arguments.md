---
title: "Diferencias entre parámetros y argumentos (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- parameters [Visual Basic], and arguments
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], and parameters
- procedure parameters
- parameters [Visual Basic], definition
ms.assetid: c237c056-74f4-4749-9f2c-15864f139a31
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6613c64a24ef18239422b69f8b5320eadc95b92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a><span data-ttu-id="a12b1-102">Diferencias entre parámetros y argumentos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a12b1-102">Differences Between Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="a12b1-103">En la mayoría de los casos, un procedimiento debe tener cierta información sobre las circunstancias en que se ha llamado.</span><span class="sxs-lookup"><span data-stu-id="a12b1-103">In most cases, a procedure must have some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="a12b1-104">Un procedimiento que realiza las tareas repetitivas o compartidas utiliza información diferente para cada llamada.</span><span class="sxs-lookup"><span data-stu-id="a12b1-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="a12b1-105">Esta información está formada por las variables, constantes y expresiones que se pasan al procedimiento cuando se llama al método.</span><span class="sxs-lookup"><span data-stu-id="a12b1-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="a12b1-106">Para comunicar esta información al procedimiento, el procedimiento define un *parámetro*, y el código que realiza la llamada pasa un *argumento* a ese parámetro.</span><span class="sxs-lookup"><span data-stu-id="a12b1-106">To communicate this information to the procedure, the procedure defines a *parameter*, and the calling code passes an *argument* to that parameter.</span></span> <span data-ttu-id="a12b1-107">Se puede considerar el parámetro como un espacio de estacionamiento y el argumento como un automóvil.</span><span class="sxs-lookup"><span data-stu-id="a12b1-107">You can think of the parameter as a parking space and the argument as an automobile.</span></span> <span data-ttu-id="a12b1-108">Igual que diferentes automóviles pueden park en un espacio de estacionamiento en momentos diferentes, el código de llamada puede pasar un argumento distinto al mismo parámetro cada vez que llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="a12b1-108">Just as different automobiles can park in a parking space at different times, the calling code can pass a different argument to the same parameter every time that it calls the procedure.</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="a12b1-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a12b1-109">Parameters</span></span>  
 <span data-ttu-id="a12b1-110">A *parámetro* representa un valor que el procedimiento espera que se pasan cuando se llama al método.</span><span class="sxs-lookup"><span data-stu-id="a12b1-110">A *parameter* represents a value that the procedure expects you to pass when you call it.</span></span> <span data-ttu-id="a12b1-111">La declaración del procedimiento define sus parámetros.</span><span class="sxs-lookup"><span data-stu-id="a12b1-111">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="a12b1-112">Cuando se define una `Function` o `Sub` procedimiento, especifique un *lista de parámetros* entre paréntesis inmediatamente después del nombre de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="a12b1-112">When you define a `Function` or `Sub` procedure, you specify a *parameter list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="a12b1-113">Para cada parámetro, especifique un nombre, un tipo de datos y un mecanismo para pasar argumentos ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)).</span><span class="sxs-lookup"><span data-stu-id="a12b1-113">For each parameter, you specify a name, a data type, and a passing mechanism ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)).</span></span> <span data-ttu-id="a12b1-114">También puede indicar que un parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="a12b1-114">You can also indicate that a parameter is optional.</span></span> <span data-ttu-id="a12b1-115">Esto significa que el código de llamada no tiene que pasar un valor para él.</span><span class="sxs-lookup"><span data-stu-id="a12b1-115">This means that the calling code does not have to pass a value for it.</span></span>  
  
 <span data-ttu-id="a12b1-116">El nombre de cada parámetro actúa como un *variable local* en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="a12b1-116">The name of each parameter serves as a *local variable* in the procedure.</span></span> <span data-ttu-id="a12b1-117">Utilice el nombre del parámetro de la misma forma que usa cualquier otra variable.</span><span class="sxs-lookup"><span data-stu-id="a12b1-117">You use the parameter name the same way you use any other variable.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="a12b1-118">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a12b1-118">Arguments</span></span>  
 <span data-ttu-id="a12b1-119">Un *argumento* representa el valor que se pasa a un parámetro de procedimiento cuando se llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="a12b1-119">An *argument* represents the value that you pass to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="a12b1-120">El código de llamada proporciona los argumentos cuando llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="a12b1-120">The calling code supplies the arguments when it calls the procedure.</span></span>  
  
 <span data-ttu-id="a12b1-121">Cuando se llama a un `Function` o `Sub` procedimiento, incluye un *lista de argumentos* entre paréntesis inmediatamente después del nombre de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="a12b1-121">When you call a `Function` or `Sub` procedure, you include an *argument list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="a12b1-122">Cada argumento se corresponde con el parámetro en la misma posición en la lista.</span><span class="sxs-lookup"><span data-stu-id="a12b1-122">Each argument corresponds to the parameter in the same position in the list.</span></span>  
  
 <span data-ttu-id="a12b1-123">A diferencia de la definición de parámetros, argumentos no tienen nombres.</span><span class="sxs-lookup"><span data-stu-id="a12b1-123">In contrast to parameter definition, arguments do not have names.</span></span> <span data-ttu-id="a12b1-124">Cada argumento es una expresión, que puede contener cero o más variables, constantes y literales.</span><span class="sxs-lookup"><span data-stu-id="a12b1-124">Each argument is an expression, which can contain zero or more variables, constants, and literals.</span></span> <span data-ttu-id="a12b1-125">El tipo de datos de la expresión evaluada normalmente debe coincidir con el tipo de datos definido para el parámetro correspondiente, y en cualquier caso, debe poder convertirse al tipo de parámetro.</span><span class="sxs-lookup"><span data-stu-id="a12b1-125">The data type of the evaluated expression should typically match the data type defined for the corresponding parameter, and in any case it must be convertible to the parameter type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a12b1-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="a12b1-126">See Also</span></span>  
 [<span data-ttu-id="a12b1-127">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="a12b1-127">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="a12b1-128">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="a12b1-128">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="a12b1-129">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="a12b1-129">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="a12b1-130">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="a12b1-130">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="a12b1-131">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="a12b1-131">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="a12b1-132">Definir un parámetro para un procedimiento</span><span class="sxs-lookup"><span data-stu-id="a12b1-132">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)  
 [<span data-ttu-id="a12b1-133">Pasar argumentos a un procedimiento</span><span class="sxs-lookup"><span data-stu-id="a12b1-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="a12b1-134">Paso de argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="a12b1-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="a12b1-135">Procedimientos recursivos</span><span class="sxs-lookup"><span data-stu-id="a12b1-135">Recursive Procedures</span></span>](./recursive-procedures.md)  
 [<span data-ttu-id="a12b1-136">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="a12b1-136">Procedure Overloading</span></span>](./procedure-overloading.md)
