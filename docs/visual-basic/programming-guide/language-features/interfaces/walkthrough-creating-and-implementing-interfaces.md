---
title: Creación e implementación de interfaces
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: 89e8f91a04b25b84bc783d5c4f4b91cf12426f72
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405072"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="697aa-102">Tutorial: Crear e implementar interfaces (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="697aa-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>

<span data-ttu-id="697aa-103">Las interfaces describen las características de las propiedades, los métodos y los eventos, pero dejan los detalles de la implementación hasta estructuras o clases.</span><span class="sxs-lookup"><span data-stu-id="697aa-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="697aa-104">En este tutorial se muestra cómo declarar e implementar una interfaz.</span><span class="sxs-lookup"><span data-stu-id="697aa-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="697aa-105">En este tutorial no se proporciona información sobre cómo crear una interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="697aa-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a><span data-ttu-id="697aa-106">Para definir una interfaz</span><span class="sxs-lookup"><span data-stu-id="697aa-106">To define an interface</span></span>
  
1. <span data-ttu-id="697aa-107">Abra un proyecto Aplicación Windows de Visual Basic nuevo.</span><span class="sxs-lookup"><span data-stu-id="697aa-107">Open a new Visual Basic Windows Application project.</span></span>  
  
2. <span data-ttu-id="697aa-108">Agregue un nuevo módulo al proyecto haciendo clic en **Agregar módulo** en el menú **proyecto** .</span><span class="sxs-lookup"><span data-stu-id="697aa-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3. <span data-ttu-id="697aa-109">Asigne un nombre al nuevo módulo `Module1.vb` y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="697aa-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="697aa-110">Se muestra el código para el nuevo módulo.</span><span class="sxs-lookup"><span data-stu-id="697aa-110">The code for the new module is displayed.</span></span>  
  
4. <span data-ttu-id="697aa-111">Defina una interfaz denominada `TestInterface` dentro de `Module1` escribiendo `Interface TestInterface` entre las `Module` `End Module` instrucciones y y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="697aa-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="697aa-112">El **Editor de código** aplica sangría `Interface` a la palabra clave y agrega una `End Interface` instrucción para formar un bloque de código.</span><span class="sxs-lookup"><span data-stu-id="697aa-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5. <span data-ttu-id="697aa-113">Defina una propiedad, un método y un evento para la interfaz colocando el siguiente código entre las `Interface` `End Interface` instrucciones y:</span><span class="sxs-lookup"><span data-stu-id="697aa-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a><span data-ttu-id="697aa-114">Implementación</span><span class="sxs-lookup"><span data-stu-id="697aa-114">Implementation</span></span>

 <span data-ttu-id="697aa-115">Es posible que observe que la sintaxis usada para declarar miembros de interfaz es diferente de la sintaxis utilizada para declarar miembros de clase.</span><span class="sxs-lookup"><span data-stu-id="697aa-115">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="697aa-116">Esta diferencia refleja el hecho de que las interfaces no pueden contener código de implementación.</span><span class="sxs-lookup"><span data-stu-id="697aa-116">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
### <a name="to-implement-the-interface"></a><span data-ttu-id="697aa-117">Para implementar la interfaz</span><span class="sxs-lookup"><span data-stu-id="697aa-117">To implement the interface</span></span>
  
1. <span data-ttu-id="697aa-118">Agregue una clase denominada agregando `ImplementationClass` la siguiente instrucción a `Module1` , después de la `End Interface` instrucción, pero antes de la `End Module` instrucción y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="697aa-118">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     <span data-ttu-id="697aa-119">Si está trabajando en el entorno de desarrollo integrado, el **Editor de código** proporciona una `End Class` instrucción coincidente al presionar entrar.</span><span class="sxs-lookup"><span data-stu-id="697aa-119">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2. <span data-ttu-id="697aa-120">Agregue la siguiente `Implements` instrucción a `ImplementationClass` , que nombra la interfaz que la clase implementa:</span><span class="sxs-lookup"><span data-stu-id="697aa-120">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     <span data-ttu-id="697aa-121">Cuando se enumeran por separado de otros elementos en la parte superior de una clase o estructura, la `Implements` instrucción indica que la clase o estructura implementa una interfaz.</span><span class="sxs-lookup"><span data-stu-id="697aa-121">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="697aa-122">Si está trabajando en el entorno de desarrollo integrado, el **Editor de código** implementa los miembros de clase requeridos por `TestInterface` al presionar entrar, y puede omitir el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="697aa-122">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3. <span data-ttu-id="697aa-123">Si no está trabajando en el entorno de desarrollo integrado, debe implementar todos los miembros de la interfaz `MyInterface` .</span><span class="sxs-lookup"><span data-stu-id="697aa-123">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="697aa-124">Agregue el código siguiente a `ImplementationClass` para implementar `Event1` , `Method1` y `Prop1` :</span><span class="sxs-lookup"><span data-stu-id="697aa-124">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     <span data-ttu-id="697aa-125">La `Implements` instrucción nombra la interfaz y el miembro de interfaz que se está implementando.</span><span class="sxs-lookup"><span data-stu-id="697aa-125">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4. <span data-ttu-id="697aa-126">Complete la definición de `Prop1` agregando un campo privado a la clase que almacenó el valor de propiedad:</span><span class="sxs-lookup"><span data-stu-id="697aa-126">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     <span data-ttu-id="697aa-127">Devuelva el valor de `pval` desde el descriptor de acceso get de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="697aa-127">Return the value of the `pval` from the property get accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     <span data-ttu-id="697aa-128">Establezca el valor de `pval` en el descriptor de acceso set de propiedad.</span><span class="sxs-lookup"><span data-stu-id="697aa-128">Set the value of `pval` in the property set accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5. <span data-ttu-id="697aa-129">`Method1`Agregue el código siguiente para completar la definición de.</span><span class="sxs-lookup"><span data-stu-id="697aa-129">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="697aa-130">Para probar la implementación de la interfaz</span><span class="sxs-lookup"><span data-stu-id="697aa-130">To test the implementation of the interface</span></span>
  
1. <span data-ttu-id="697aa-131">Haga clic con el botón secundario en el formulario de inicio del proyecto en el **Explorador de soluciones**y haga clic en **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="697aa-131">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="697aa-132">El editor muestra la clase del formulario de inicio.</span><span class="sxs-lookup"><span data-stu-id="697aa-132">The editor displays the class for your startup form.</span></span> <span data-ttu-id="697aa-133">De forma predeterminada, se llama al formulario de inicio `Form1` .</span><span class="sxs-lookup"><span data-stu-id="697aa-133">By default, the startup form is called `Form1`.</span></span>  
  
2. <span data-ttu-id="697aa-134">Agregue el siguiente `testInstance` campo a la `Form1` clase:</span><span class="sxs-lookup"><span data-stu-id="697aa-134">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     <span data-ttu-id="697aa-135">Al declarar `testInstance` como `WithEvents` , la `Form1` clase puede controlar sus eventos.</span><span class="sxs-lookup"><span data-stu-id="697aa-135">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3. <span data-ttu-id="697aa-136">Agregue el siguiente controlador de eventos a la `Form1` clase para controlar los eventos generados por `testInstance` :</span><span class="sxs-lookup"><span data-stu-id="697aa-136">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4. <span data-ttu-id="697aa-137">Agregue una subrutina denominada `Test` a la `Form1` clase para probar la clase de implementación:</span><span class="sxs-lookup"><span data-stu-id="697aa-137">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     <span data-ttu-id="697aa-138">El `Test` procedimiento crea una instancia de la clase que implementa `MyInterface` , asigna esa instancia al `testInstance` campo, establece una propiedad y ejecuta un método a través de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="697aa-138">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5. <span data-ttu-id="697aa-139">Agregue código para llamar al `Test` procedimiento desde el `Form1 Load` procedimiento del formulario de Inicio:</span><span class="sxs-lookup"><span data-stu-id="697aa-139">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6. <span data-ttu-id="697aa-140">Ejecute el `Test` procedimiento presionando F5.</span><span class="sxs-lookup"><span data-stu-id="697aa-140">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="697aa-141">Se muestra el mensaje "Prop1 se estableció en 9".</span><span class="sxs-lookup"><span data-stu-id="697aa-141">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="697aa-142">Después de hacer clic en aceptar, se muestra el mensaje "el parámetro X de method1 es 5".</span><span class="sxs-lookup"><span data-stu-id="697aa-142">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="697aa-143">Haga clic en aceptar y se mostrará el mensaje "el controlador de eventos detectó el evento".</span><span class="sxs-lookup"><span data-stu-id="697aa-143">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="697aa-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="697aa-144">See also</span></span>

- [<span data-ttu-id="697aa-145">Implements (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="697aa-145">Implements Statement</span></span>](../../../language-reference/statements/implements-statement.md)
- [<span data-ttu-id="697aa-146">Interfaces</span><span class="sxs-lookup"><span data-stu-id="697aa-146">Interfaces</span></span>](index.md)
- [<span data-ttu-id="697aa-147">Instrucción Interface</span><span class="sxs-lookup"><span data-stu-id="697aa-147">Interface Statement</span></span>](../../../language-reference/statements/interface-statement.md)
- [<span data-ttu-id="697aa-148">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="697aa-148">Event Statement</span></span>](../../../language-reference/statements/event-statement.md)
