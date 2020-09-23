---
title: Diferencias entre parámetros y argumentos
ms.date: 07/20/2015
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
ms.openlocfilehash: 0ad9104f347205cebc6e078aac246a413c0d9b78
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91057850"
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a><span data-ttu-id="0b76f-102">Diferencias entre parámetros y argumentos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b76f-102">Differences Between Parameters and Arguments (Visual Basic)</span></span>

<span data-ttu-id="0b76f-103">En la mayoría de los casos, un procedimiento debe tener información sobre las circunstancias en las que se ha llamado.</span><span class="sxs-lookup"><span data-stu-id="0b76f-103">In most cases, a procedure must have some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="0b76f-104">Un procedimiento que realiza tareas repetidas o compartidas utiliza información diferente para cada llamada.</span><span class="sxs-lookup"><span data-stu-id="0b76f-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="0b76f-105">Esta información se compone de variables, constantes y expresiones que se pasan al procedimiento cuando se llama.</span><span class="sxs-lookup"><span data-stu-id="0b76f-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="0b76f-106">Para comunicar esta información al procedimiento, el procedimiento define un *parámetro*y el código de llamada pasa un *argumento* a ese parámetro.</span><span class="sxs-lookup"><span data-stu-id="0b76f-106">To communicate this information to the procedure, the procedure defines a *parameter*, and the calling code passes an *argument* to that parameter.</span></span> <span data-ttu-id="0b76f-107">Puede pensar en el parámetro como un espacio de estacionamiento y el argumento como un automóvil.</span><span class="sxs-lookup"><span data-stu-id="0b76f-107">You can think of the parameter as a parking space and the argument as an automobile.</span></span> <span data-ttu-id="0b76f-108">Del mismo modo que los diferentes automóviles pueden detenerse en un espacio de estacionamiento en momentos diferentes, el código de llamada puede pasar un argumento diferente al mismo parámetro cada vez que llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0b76f-108">Just as different automobiles can park in a parking space at different times, the calling code can pass a different argument to the same parameter every time that it calls the procedure.</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="0b76f-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0b76f-109">Parameters</span></span>  

 <span data-ttu-id="0b76f-110">Un *parámetro* representa un valor que el procedimiento espera que pase al llamarlo.</span><span class="sxs-lookup"><span data-stu-id="0b76f-110">A *parameter* represents a value that the procedure expects you to pass when you call it.</span></span> <span data-ttu-id="0b76f-111">La declaración del procedimiento define sus parámetros.</span><span class="sxs-lookup"><span data-stu-id="0b76f-111">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="0b76f-112">Al definir un `Function` procedimiento o `Sub` , se especifica una *lista de parámetros* entre paréntesis inmediatamente después del nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0b76f-112">When you define a `Function` or `Sub` procedure, you specify a *parameter list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="0b76f-113">Para cada parámetro, se especifica un nombre, un tipo de datos y un mecanismo de paso ([ByVal](../../../language-reference/modifiers/byval.md) o [ByRef](../../../language-reference/modifiers/byref.md)).</span><span class="sxs-lookup"><span data-stu-id="0b76f-113">For each parameter, you specify a name, a data type, and a passing mechanism ([ByVal](../../../language-reference/modifiers/byval.md) or [ByRef](../../../language-reference/modifiers/byref.md)).</span></span> <span data-ttu-id="0b76f-114">También puede indicar que un parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="0b76f-114">You can also indicate that a parameter is optional.</span></span> <span data-ttu-id="0b76f-115">Esto significa que el código de llamada no tiene que pasar un valor para él.</span><span class="sxs-lookup"><span data-stu-id="0b76f-115">This means that the calling code does not have to pass a value for it.</span></span>  
  
 <span data-ttu-id="0b76f-116">El nombre de cada parámetro actúa como una *variable local* en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0b76f-116">The name of each parameter serves as a *local variable* in the procedure.</span></span> <span data-ttu-id="0b76f-117">El nombre del parámetro se utiliza de la misma manera que cualquier otra variable.</span><span class="sxs-lookup"><span data-stu-id="0b76f-117">You use the parameter name the same way you use any other variable.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="0b76f-118">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0b76f-118">Arguments</span></span>  

 <span data-ttu-id="0b76f-119">Un *argumento* representa el valor que se pasa a un parámetro de procedimiento cuando se llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0b76f-119">An *argument* represents the value that you pass to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="0b76f-120">El código de llamada proporciona los argumentos cuando llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0b76f-120">The calling code supplies the arguments when it calls the procedure.</span></span>  
  
 <span data-ttu-id="0b76f-121">Cuando se llama a `Function` un `Sub` procedimiento o, se incluye una *lista de argumentos* entre paréntesis inmediatamente después del nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0b76f-121">When you call a `Function` or `Sub` procedure, you include an *argument list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="0b76f-122">Cada argumento corresponde al parámetro en la misma posición en la lista.</span><span class="sxs-lookup"><span data-stu-id="0b76f-122">Each argument corresponds to the parameter in the same position in the list.</span></span>  
  
 <span data-ttu-id="0b76f-123">A diferencia de la definición de parámetros, los argumentos no tienen nombres.</span><span class="sxs-lookup"><span data-stu-id="0b76f-123">In contrast to parameter definition, arguments do not have names.</span></span> <span data-ttu-id="0b76f-124">Cada argumento es una expresión, que puede contener cero o más variables, constantes y literales.</span><span class="sxs-lookup"><span data-stu-id="0b76f-124">Each argument is an expression, which can contain zero or more variables, constants, and literals.</span></span> <span data-ttu-id="0b76f-125">El tipo de datos de la expresión evaluada debe coincidir normalmente con el tipo de datos definido para el parámetro correspondiente y, en cualquier caso, debe ser convertible en el tipo de parámetro.</span><span class="sxs-lookup"><span data-stu-id="0b76f-125">The data type of the evaluated expression should typically match the data type defined for the corresponding parameter, and in any case it must be convertible to the parameter type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b76f-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b76f-126">See also</span></span>

- [<span data-ttu-id="0b76f-127">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="0b76f-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="0b76f-128">Procedimientos Sub</span><span class="sxs-lookup"><span data-stu-id="0b76f-128">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="0b76f-129">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="0b76f-129">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="0b76f-130">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="0b76f-130">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="0b76f-131">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="0b76f-131">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="0b76f-132">Procedimiento para definir un parámetro para un procedimiento</span><span class="sxs-lookup"><span data-stu-id="0b76f-132">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="0b76f-133">Procedimiento para pasar argumentos a un procedimiento</span><span class="sxs-lookup"><span data-stu-id="0b76f-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="0b76f-134">Pasar argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="0b76f-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="0b76f-135">Procedimientos recursivos</span><span class="sxs-lookup"><span data-stu-id="0b76f-135">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="0b76f-136">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="0b76f-136">Procedure Overloading</span></span>](./procedure-overloading.md)
