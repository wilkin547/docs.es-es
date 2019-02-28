---
title: Handles (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Handles
- vb.Handles
helpviewer_keywords:
- Handles keyword [Visual Basic]
ms.assetid: 1b051c0e-f499-42f6-acb5-6f4f27824b40
ms.openlocfilehash: 3be28ee718675b1f6bebfaff03baaf561a6fff43
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974073"
---
# <a name="handles-clause-visual-basic"></a><span data-ttu-id="96c31-102">Handles (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96c31-102">Handles Clause (Visual Basic)</span></span>
<span data-ttu-id="96c31-103">Declara que un procedimiento controla un evento especificado.</span><span class="sxs-lookup"><span data-stu-id="96c31-103">Declares that a procedure handles a specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96c31-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96c31-104">Syntax</span></span>  
  
```  
proceduredeclaration Handles eventlist  
```  
  
## <a name="parts"></a><span data-ttu-id="96c31-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="96c31-105">Parts</span></span>  
 `proceduredeclaration`  
 <span data-ttu-id="96c31-106">La declaración de procedimiento `Sub` del procedimiento que controlará el evento.</span><span class="sxs-lookup"><span data-stu-id="96c31-106">The `Sub` procedure declaration for the procedure that will handle the event.</span></span>  
  
 `eventlist`  
 <span data-ttu-id="96c31-107">Lista de los eventos que `proceduredeclaration` debe controlar, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="96c31-107">List of the events for `proceduredeclaration` to handle, separated by commas.</span></span> <span data-ttu-id="96c31-108">Los eventos deben ser generados bien por la clase base de la clase actual o bien por un objeto declarado mediante la palabra clave `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="96c31-108">The events must be raised by either the base class for the current class, or by an object declared using the `WithEvents` keyword.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96c31-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="96c31-109">Remarks</span></span>  
 <span data-ttu-id="96c31-110">Utilice la palabra clave `Handles` al final de una declaración de procedimiento para que controle los eventos generados por una variable de objeto declarada mediante el uso de la palabra clave `WithEvents` .</span><span class="sxs-lookup"><span data-stu-id="96c31-110">Use the `Handles` keyword at the end of a procedure declaration to cause it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span> <span data-ttu-id="96c31-111">La palabra clave `Handles` también puede usarse en una clase derivada para controlar eventos de una clase base.</span><span class="sxs-lookup"><span data-stu-id="96c31-111">The `Handles` keyword can also be used in a derived class to handle events from a base class.</span></span>  
  
 <span data-ttu-id="96c31-112">La palabra clave `Handles` y la instrucción `AddHandler` permiten especificar que determinados procedimientos controlen eventos determinados, pero hay diferencias.</span><span class="sxs-lookup"><span data-stu-id="96c31-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="96c31-113">Use la palabra clave `Handles` al definir un procedimiento para especificar que controla un evento determinado.</span><span class="sxs-lookup"><span data-stu-id="96c31-113">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="96c31-114">La instrucción `AddHandler` conecta los procedimientos a los eventos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="96c31-114">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="96c31-115">Para obtener más información, consulte [AddHandler (instrucción)](../../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="96c31-115">For more information, see [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span>  
  
 <span data-ttu-id="96c31-116">Para los eventos personalizados, la aplicación invoca al descriptor de acceso `AddHandler` del evento cuando agrega el procedimiento como un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="96c31-116">For custom events, the application invokes the event's `AddHandler` accessor when it adds the procedure as an event handler.</span></span> <span data-ttu-id="96c31-117">Para obtener más información sobre los eventos personalizados, vea [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="96c31-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="96c31-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="96c31-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#2)]  
  
 <span data-ttu-id="96c31-119">En el siguiente ejemplo se demuestra cómo una clase derivada puede usar la instrucción `Handles` para controlar un evento de una clase base.</span><span class="sxs-lookup"><span data-stu-id="96c31-119">The following example demonstrates how a derived class can use the `Handles` statement to handle an event from a base class.</span></span>  
  
 [!code-vb[VbVbalrEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="96c31-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="96c31-120">Example</span></span>  
 <span data-ttu-id="96c31-121">El ejemplo siguiente contiene dos controladores de eventos de botón para un **aplicación WPF** proyecto.</span><span class="sxs-lookup"><span data-stu-id="96c31-121">The following example contains two button event handlers for a **WPF Application** project.</span></span>  
  
 [!code-vb[VbVbalrEvents#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/class3.vb#41)]  
  
## <a name="example"></a><span data-ttu-id="96c31-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="96c31-122">Example</span></span>  
 <span data-ttu-id="96c31-123">El siguiente ejemplo es equivalente al ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="96c31-123">The following example is equivalent to the previous example.</span></span> <span data-ttu-id="96c31-124">El `eventlist` en la cláusula `Handles` contiene los eventos de ambos botones.</span><span class="sxs-lookup"><span data-stu-id="96c31-124">The `eventlist` in the `Handles` clause contains the events for both buttons.</span></span>  
  
 [!code-vb[VbVbalrEvents#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/class3.vb#42)]  
  
## <a name="see-also"></a><span data-ttu-id="96c31-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="96c31-125">See also</span></span>
- [<span data-ttu-id="96c31-126">WithEvents</span><span class="sxs-lookup"><span data-stu-id="96c31-126">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
- [<span data-ttu-id="96c31-127">AddHandler (instrucción)</span><span class="sxs-lookup"><span data-stu-id="96c31-127">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="96c31-128">RemoveHandler (instrucción)</span><span class="sxs-lookup"><span data-stu-id="96c31-128">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="96c31-129">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="96c31-129">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="96c31-130">RaiseEvent (instrucción)</span><span class="sxs-lookup"><span data-stu-id="96c31-130">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
- [<span data-ttu-id="96c31-131">Eventos</span><span class="sxs-lookup"><span data-stu-id="96c31-131">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
