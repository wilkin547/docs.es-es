---
title: Crear e implementar Interfaces (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: 7a5694826e0fff82aceb8ad18f75f96f308e724c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680393"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="3e54e-102">Tutorial: Crear e implementar Interfaces (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e54e-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>

<span data-ttu-id="3e54e-103">Interfaces describen las características de propiedades, métodos y eventos, pero dejan los detalles de implementación para las estructuras o clases.</span><span class="sxs-lookup"><span data-stu-id="3e54e-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="3e54e-104">Este tutorial muestra cómo declarar e implementar una interfaz.</span><span class="sxs-lookup"><span data-stu-id="3e54e-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e54e-105">En este tutorial no proporciona información sobre cómo crear una interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="3e54e-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a><span data-ttu-id="3e54e-106">Para definir una interfaz</span><span class="sxs-lookup"><span data-stu-id="3e54e-106">To define an interface</span></span>
  
1.  <span data-ttu-id="3e54e-107">Abra un proyecto Aplicación Windows de Visual Basic nuevo.</span><span class="sxs-lookup"><span data-stu-id="3e54e-107">Open a new Visual Basic Windows Application project.</span></span>  
  
2.  <span data-ttu-id="3e54e-108">Agregue un nuevo módulo al proyecto haciendo clic en **Agregar módulo** en el **proyecto** menú.</span><span class="sxs-lookup"><span data-stu-id="3e54e-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3.  <span data-ttu-id="3e54e-109">Nombre del nuevo módulo `Module1.vb` y haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="3e54e-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="3e54e-110">Se muestra el código para el nuevo módulo.</span><span class="sxs-lookup"><span data-stu-id="3e54e-110">The code for the new module is displayed.</span></span>  
  
4.  <span data-ttu-id="3e54e-111">Defina una interfaz denominada `TestInterface` en `Module1` escribiendo `Interface TestInterface` entre el `Module` y `End Module` instrucciones y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="3e54e-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="3e54e-112">El **Editor de código** aplica una sangría hacia la `Interface` palabra clave y agrega un `End Interface` instrucción para formar un bloque de código.</span><span class="sxs-lookup"><span data-stu-id="3e54e-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5.  <span data-ttu-id="3e54e-113">Definir una propiedad, método y evento para la interfaz, coloque el código siguiente entre las `Interface` y `End Interface` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="3e54e-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a><span data-ttu-id="3e54e-114">Implementación</span><span class="sxs-lookup"><span data-stu-id="3e54e-114">Implementation</span></span>

 <span data-ttu-id="3e54e-115">Es posible que tenga en cuenta que la sintaxis que se utiliza para declarar a miembros de interfaz es diferente de la sintaxis utilizada para declarar a miembros de clase.</span><span class="sxs-lookup"><span data-stu-id="3e54e-115">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="3e54e-116">Esta diferencia refleja el hecho de que las interfaces no pueden contener código de implementación.</span><span class="sxs-lookup"><span data-stu-id="3e54e-116">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
### <a name="to-implement-the-interface"></a><span data-ttu-id="3e54e-117">Para implementar la interfaz</span><span class="sxs-lookup"><span data-stu-id="3e54e-117">To implement the interface</span></span>
  
1.  <span data-ttu-id="3e54e-118">Agregue una clase denominada `ImplementationClass` agregando la siguiente instrucción para `Module1`, después el `End Interface` instrucción pero antes la `End Module` instrucción y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="3e54e-118">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     <span data-ttu-id="3e54e-119">Si está trabajando en el entorno de desarrollo integrado, el **Editor de código** suministra una coincidencia `End Class` instrucción cuando se presiona ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="3e54e-119">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2.  <span data-ttu-id="3e54e-120">Agregue el siguiente `Implements` instrucción `ImplementationClass`, que nombra la interfaz de la clase implementa:</span><span class="sxs-lookup"><span data-stu-id="3e54e-120">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     <span data-ttu-id="3e54e-121">Cuando se muestra por separado de otros elementos en la parte superior de una clase o estructura, el `Implements` instrucción indica que la clase o estructura implementa una interfaz.</span><span class="sxs-lookup"><span data-stu-id="3e54e-121">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="3e54e-122">Si está trabajando en el entorno de desarrollo integrado, el **Editor de código** implementa los miembros de clase requeridos por `TestInterface` cuando presione ENTRAR y puede omitir el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="3e54e-122">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3.  <span data-ttu-id="3e54e-123">Si no está trabajando dentro del entorno de desarrollo integrado, debe implementar todos los miembros de la interfaz `MyInterface`.</span><span class="sxs-lookup"><span data-stu-id="3e54e-123">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="3e54e-124">Agregue el código siguiente al `ImplementationClass` implementar `Event1`, `Method1`, y `Prop1`:</span><span class="sxs-lookup"><span data-stu-id="3e54e-124">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     <span data-ttu-id="3e54e-125">El `Implements` designadas por la interfaz y miembro de interfaz que se implementa la instrucción.</span><span class="sxs-lookup"><span data-stu-id="3e54e-125">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4.  <span data-ttu-id="3e54e-126">Completar la definición de `Prop1` mediante la adición de un campo privado a la clase que almacena el valor de propiedad:</span><span class="sxs-lookup"><span data-stu-id="3e54e-126">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     <span data-ttu-id="3e54e-127">Devolver el valor de la `pval` de la propiedad de descriptor de acceso get.</span><span class="sxs-lookup"><span data-stu-id="3e54e-127">Return the value of the `pval` from the property get accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     <span data-ttu-id="3e54e-128">Establezca el valor de `pval` en la propiedad de descriptor de acceso set.</span><span class="sxs-lookup"><span data-stu-id="3e54e-128">Set the value of `pval` in the property set accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5.  <span data-ttu-id="3e54e-129">Completar la definición de `Method1` agregando el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="3e54e-129">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="3e54e-130">Para probar la implementación de la interfaz</span><span class="sxs-lookup"><span data-stu-id="3e54e-130">To test the implementation of the interface</span></span>
  
1.  <span data-ttu-id="3e54e-131">Haga clic en el formulario de inicio para el proyecto en el **el Explorador de soluciones**y haga clic en **ver código**.</span><span class="sxs-lookup"><span data-stu-id="3e54e-131">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="3e54e-132">El editor muestra la clase de formulario de inicio.</span><span class="sxs-lookup"><span data-stu-id="3e54e-132">The editor displays the class for your startup form.</span></span> <span data-ttu-id="3e54e-133">De forma predeterminada, el formulario de inicio se denomina `Form1`.</span><span class="sxs-lookup"><span data-stu-id="3e54e-133">By default, the startup form is called `Form1`.</span></span>  
  
2.  <span data-ttu-id="3e54e-134">Agregue el siguiente `testInstance` campo el `Form1` clase:</span><span class="sxs-lookup"><span data-stu-id="3e54e-134">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     <span data-ttu-id="3e54e-135">Declarando `testInstance` como `WithEvents`, el `Form1` clase puede controlar sus eventos.</span><span class="sxs-lookup"><span data-stu-id="3e54e-135">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3.  <span data-ttu-id="3e54e-136">Agregue el siguiente controlador de eventos para el `Form1` clase para controlar los eventos generados por `testInstance`:</span><span class="sxs-lookup"><span data-stu-id="3e54e-136">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4.  <span data-ttu-id="3e54e-137">Agregue una subrutina denominada `Test` a la `Form1` clase para probar la clase de implementación:</span><span class="sxs-lookup"><span data-stu-id="3e54e-137">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     <span data-ttu-id="3e54e-138">El `Test` procedimiento crea una instancia de la clase que implementa `MyInterface`, asigna esa instancia para el `testInstance` establece una propiedad de campo y se ejecuta un método a través de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="3e54e-138">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5.  <span data-ttu-id="3e54e-139">Agregue código para llamar a la `Test` procedimiento desde el `Form1 Load` procedimiento del formulario de inicio:</span><span class="sxs-lookup"><span data-stu-id="3e54e-139">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6.  <span data-ttu-id="3e54e-140">Ejecute el `Test` procedimiento presionando F5.</span><span class="sxs-lookup"><span data-stu-id="3e54e-140">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="3e54e-141">Se muestra el mensaje "Prop1 se estableció en 9".</span><span class="sxs-lookup"><span data-stu-id="3e54e-141">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="3e54e-142">Se muestra después de hacer clic en Aceptar, el mensaje "el parámetro X de Method1 es 5".</span><span class="sxs-lookup"><span data-stu-id="3e54e-142">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="3e54e-143">Haga clic en Aceptar, y se muestra el mensaje "se detectó el controlador de eventos al evento".</span><span class="sxs-lookup"><span data-stu-id="3e54e-143">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e54e-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e54e-144">See also</span></span>

- [<span data-ttu-id="3e54e-145">Implements (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3e54e-145">Implements Statement</span></span>](../../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="3e54e-146">Interfaces</span><span class="sxs-lookup"><span data-stu-id="3e54e-146">Interfaces</span></span>](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [<span data-ttu-id="3e54e-147">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3e54e-147">Interface Statement</span></span>](../../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="3e54e-148">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3e54e-148">Event Statement</span></span>](../../../../visual-basic/language-reference/statements/event-statement.md)
