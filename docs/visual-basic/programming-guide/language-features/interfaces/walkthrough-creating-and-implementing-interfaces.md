---
title: Crear e implementar Interfaces (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 08bf6dc7344d4f83c8ab1908fdeb29eb4a53e142
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="ed315-102">Tutorial: Crear e implementar interfaces (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed315-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>
<span data-ttu-id="ed315-103">Interfaces describen las características de propiedades, métodos y eventos, pero dejan los detalles de implementación para las estructuras o clases.</span><span class="sxs-lookup"><span data-stu-id="ed315-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="ed315-104">Este tutorial muestra cómo declarar e implementar una interfaz.</span><span class="sxs-lookup"><span data-stu-id="ed315-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed315-105">En este tutorial no proporciona información sobre cómo crear una interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="ed315-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-define-an-interface"></a><span data-ttu-id="ed315-106">Para definir una interfaz</span><span class="sxs-lookup"><span data-stu-id="ed315-106">To define an interface</span></span>  
  
1.  <span data-ttu-id="ed315-107">Abra un proyecto de aplicación Windows de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] nuevo.</span><span class="sxs-lookup"><span data-stu-id="ed315-107">Open a new [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Windows Application project.</span></span>  
  
2.  <span data-ttu-id="ed315-108">Agregar un nuevo módulo al proyecto haciendo clic en **Agregar módulo** en el **proyecto** menú.</span><span class="sxs-lookup"><span data-stu-id="ed315-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3.  <span data-ttu-id="ed315-109">Nombre del nuevo módulo `Module1.vb` y haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="ed315-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="ed315-110">Se muestra el código para el nuevo módulo.</span><span class="sxs-lookup"><span data-stu-id="ed315-110">The code for the new module is displayed.</span></span>  
  
4.  <span data-ttu-id="ed315-111">Defina una interfaz denominada `TestInterface` en `Module1` escribiendo `Interface TestInterface` entre el `Module` y `End Module` instrucciones y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="ed315-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="ed315-112">El **Editor de código** sangrías el `Interface` (palabra clave) y agrega un `End Interface` instrucción para formar un bloque de código.</span><span class="sxs-lookup"><span data-stu-id="ed315-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5.  <span data-ttu-id="ed315-113">Definir una propiedad, el método y el evento para la interfaz, coloque el código siguiente entre las `Interface` y `End Interface` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="ed315-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#98](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]  
  
## <a name="implementation"></a><span data-ttu-id="ed315-114">Implementación</span><span class="sxs-lookup"><span data-stu-id="ed315-114">Implementation</span></span>  
 <span data-ttu-id="ed315-115">Puede observar que la sintaxis utilizada para declarar a los miembros de interfaz es diferente de la sintaxis utilizada para declarar a miembros de clase.</span><span class="sxs-lookup"><span data-stu-id="ed315-115">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="ed315-116">Esta diferencia refleja el hecho de que las interfaces no pueden contener código de implementación.</span><span class="sxs-lookup"><span data-stu-id="ed315-116">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
#### <a name="to-implement-the-interface"></a><span data-ttu-id="ed315-117">Para implementar la interfaz</span><span class="sxs-lookup"><span data-stu-id="ed315-117">To implement the interface</span></span>  
  
1.  <span data-ttu-id="ed315-118">Agregue una clase denominada `ImplementationClass` agregando la siguiente instrucción para `Module1`, después la `End Interface` instrucción pero antes del `End Module` instrucción y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="ed315-118">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     [!code-vb[VbVbalrOOP#99](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]  
  
     <span data-ttu-id="ed315-119">Si está trabajando dentro del entorno de desarrollo integrado, el **Editor de código** proporciona una coincidencia `End Class` instrucción cuando se presiona ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="ed315-119">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2.  <span data-ttu-id="ed315-120">Agregue el siguiente `Implements` instrucción `ImplementationClass`, que la interfaz de un nombre a la clase implementa:</span><span class="sxs-lookup"><span data-stu-id="ed315-120">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     [!code-vb[VbVbalrOOP#100](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]  
  
     <span data-ttu-id="ed315-121">Cuando se muestra por separado de otros elementos en la parte superior de una clase o estructura, el `Implements` instrucción indica que la clase o estructura implementa una interfaz.</span><span class="sxs-lookup"><span data-stu-id="ed315-121">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="ed315-122">Si está trabajando dentro del entorno de desarrollo integrado, el **Editor de código** implementa los miembros de clase requeridos por `TestInterface` cuando se presiona ENTRAR, y puede omitir el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="ed315-122">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3.  <span data-ttu-id="ed315-123">Si no está trabajando en el entorno de desarrollo integrado, debe implementar todos los miembros de la interfaz `MyInterface`.</span><span class="sxs-lookup"><span data-stu-id="ed315-123">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="ed315-124">Agregue el código siguiente a `ImplementationClass` implementar `Event1`, `Method1`, y `Prop1`:</span><span class="sxs-lookup"><span data-stu-id="ed315-124">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     [!code-vb[VbVbalrOOP#101](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]  
  
     <span data-ttu-id="ed315-125">El `Implements` designadas por la interfaz y el miembro de interfaz que se implementa la instrucción.</span><span class="sxs-lookup"><span data-stu-id="ed315-125">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4.  <span data-ttu-id="ed315-126">Completar la definición de `Prop1` mediante la adición de un campo privado a la clase que almacena el valor de propiedad:</span><span class="sxs-lookup"><span data-stu-id="ed315-126">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     [!code-vb[VbVbalrOOP#102](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]  
  
     <span data-ttu-id="ed315-127">Devolver el valor de la `pval` de la propiedad de descriptor de acceso get.</span><span class="sxs-lookup"><span data-stu-id="ed315-127">Return the value of the `pval` from the property get accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#103](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]  
  
     <span data-ttu-id="ed315-128">Establezca el valor de `pval` en la propiedad de descriptor de acceso set.</span><span class="sxs-lookup"><span data-stu-id="ed315-128">Set the value of `pval` in the property set accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#104](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]  
  
5.  <span data-ttu-id="ed315-129">Completar la definición de `Method1` agregando el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="ed315-129">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     [!code-vb[VbVbalrOOP#105](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]  
  
#### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="ed315-130">Para probar la implementación de la interfaz</span><span class="sxs-lookup"><span data-stu-id="ed315-130">To test the implementation of the interface</span></span>  
  
1.  <span data-ttu-id="ed315-131">Haga clic en el formulario de inicio para el proyecto en el **el Explorador de soluciones**y haga clic en **ver código**.</span><span class="sxs-lookup"><span data-stu-id="ed315-131">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="ed315-132">El editor muestra la clase para el formulario de inicio.</span><span class="sxs-lookup"><span data-stu-id="ed315-132">The editor displays the class for your startup form.</span></span> <span data-ttu-id="ed315-133">De forma predeterminada, el formulario de inicio se denomina `Form1`.</span><span class="sxs-lookup"><span data-stu-id="ed315-133">By default, the startup form is called `Form1`.</span></span>  
  
2.  <span data-ttu-id="ed315-134">Agregue el siguiente `testInstance` campo el `Form1` clase:</span><span class="sxs-lookup"><span data-stu-id="ed315-134">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     [!code-vb[VbVbalrOOP#120](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]  
  
     <span data-ttu-id="ed315-135">Mediante la declaración de `testInstance` como `WithEvents`, la `Form1` clase puede controlar sus eventos.</span><span class="sxs-lookup"><span data-stu-id="ed315-135">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3.  <span data-ttu-id="ed315-136">Agregue el siguiente controlador de eventos para el `Form1` clase para controlar los eventos generados por `testInstance`:</span><span class="sxs-lookup"><span data-stu-id="ed315-136">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     [!code-vb[VbVbalrOOP#106](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]  
  
4.  <span data-ttu-id="ed315-137">Agregue una subrutina denominada `Test` a la `Form1` clase para probar la clase de implementación:</span><span class="sxs-lookup"><span data-stu-id="ed315-137">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     [!code-vb[VbVbalrOOP#107](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]  
  
     <span data-ttu-id="ed315-138">El `Test` procedimiento crea una instancia de la clase que implementa `MyInterface`, asigna esa instancia a la `testInstance` campo, Establece una propiedad y ejecuta un método a través de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="ed315-138">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5.  <span data-ttu-id="ed315-139">Agregue código para llamar a la `Test` procedimiento desde la `Form1 Load` procedimiento con el formulario de inicio:</span><span class="sxs-lookup"><span data-stu-id="ed315-139">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     [!code-vb[VbVbalrOOP#108](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]  
  
6.  <span data-ttu-id="ed315-140">Ejecute el `Test` procedimiento presionando F5.</span><span class="sxs-lookup"><span data-stu-id="ed315-140">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="ed315-141">Se muestra el mensaje "Prop1 se establece en 9".</span><span class="sxs-lookup"><span data-stu-id="ed315-141">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="ed315-142">Después de hacer clic en Aceptar, el mensaje "el parámetro X de Method1 es 5" se muestran.</span><span class="sxs-lookup"><span data-stu-id="ed315-142">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="ed315-143">Haga clic en Aceptar, y se muestra el mensaje "el controlador de eventos ha interceptado el evento".</span><span class="sxs-lookup"><span data-stu-id="ed315-143">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed315-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed315-144">See Also</span></span>  
 [<span data-ttu-id="ed315-145">Implements (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ed315-145">Implements Statement</span></span>](../../../../visual-basic/language-reference/statements/implements-statement.md)  
 [<span data-ttu-id="ed315-146">Interfaces</span><span class="sxs-lookup"><span data-stu-id="ed315-146">Interfaces</span></span>](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 [<span data-ttu-id="ed315-147">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ed315-147">Interface Statement</span></span>](../../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="ed315-148">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ed315-148">Event Statement</span></span>](../../../../visual-basic/language-reference/statements/event-statement.md)
