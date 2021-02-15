---
description: 'Más información acerca de: Tutorial: definir clases (Visual Basic)'
title: Definir clases
ms.date: 07/20/2015
helpviewer_keywords:
- execution [Visual Basic], ending
- objects [Visual Basic], initializing
- Initialize event [Visual Basic]
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
ms.openlocfilehash: a97e04b92db3387966afa410d5697a05b482ae09
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100438793"
---
# <a name="walkthrough-defining-classes-visual-basic"></a><span data-ttu-id="509e3-103">Tutorial: Definir clases (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="509e3-103">Walkthrough: Defining Classes (Visual Basic)</span></span>

<span data-ttu-id="509e3-104">En este tutorial se muestra cómo definir clases, que puede usar para crear objetos.</span><span class="sxs-lookup"><span data-stu-id="509e3-104">This walkthrough demonstrates how to define classes, which you can then use to create objects.</span></span> <span data-ttu-id="509e3-105">También se muestra cómo agregar propiedades y métodos a la nueva clase y se muestra cómo inicializar un objeto.</span><span class="sxs-lookup"><span data-stu-id="509e3-105">It also shows you how to add properties and methods to the new class, and demonstrates how to initialize an object.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a><span data-ttu-id="509e3-106">Para definir una clase</span><span class="sxs-lookup"><span data-stu-id="509e3-106">To define a class</span></span>
  
1. <span data-ttu-id="509e3-107">Cree un proyecto haciendo clic en **nuevo proyecto** en el menú **archivo** .</span><span class="sxs-lookup"><span data-stu-id="509e3-107">Create a project by clicking **New Project** on the **File** menu.</span></span> <span data-ttu-id="509e3-108">Aparecerá el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="509e3-108">The **New Project** dialog box appears.</span></span>  
  
2. <span data-ttu-id="509e3-109">Seleccione aplicación de Windows en la lista de Visual Basic plantillas de proyecto para mostrar el nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="509e3-109">Select Windows Application from the list of Visual Basic project templates to display the new project.</span></span>  
  
3. <span data-ttu-id="509e3-110">Agregue una nueva clase al proyecto haciendo clic en **Agregar clase** en el menú **proyecto** .</span><span class="sxs-lookup"><span data-stu-id="509e3-110">Add a new class to the project by clicking **Add Class** on the **Project** menu.</span></span> <span data-ttu-id="509e3-111">Aparecerá el cuadro de diálogo **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="509e3-111">The **Add New Item** dialog box appears.</span></span>  
  
4. <span data-ttu-id="509e3-112">Seleccione la plantilla **clase** .</span><span class="sxs-lookup"><span data-stu-id="509e3-112">Select the **Class** template.</span></span>  
  
5. <span data-ttu-id="509e3-113">Asigne a la nueva clase el nombre `UserNameInfo.vb` y, a continuación, haga clic en **Agregar** para mostrar el código de la nueva clase.</span><span class="sxs-lookup"><span data-stu-id="509e3-113">Name the new class `UserNameInfo.vb`, and then click **Add** to display the code for the new class.</span></span>  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    > <span data-ttu-id="509e3-114">Puede usar el editor de **código** de Visual Basic para agregar una clase al formulario de inicio escribiendo la `Class` palabra clave seguida del nombre de la nueva clase.</span><span class="sxs-lookup"><span data-stu-id="509e3-114">You can use the Visual Basic **Code Editor** to add a class to your startup form by typing the `Class` keyword followed by the name of the new class.</span></span> <span data-ttu-id="509e3-115">El **Editor de código** proporciona una `End Class` instrucción correspondiente.</span><span class="sxs-lookup"><span data-stu-id="509e3-115">The **Code Editor** provides a corresponding `End Class` statement for you.</span></span>  
  
6. <span data-ttu-id="509e3-116">Defina un campo privado para la clase agregando el código siguiente entre las `Class` `End Class` instrucciones y:</span><span class="sxs-lookup"><span data-stu-id="509e3-116">Define a private field for the class by adding the following code between the `Class` and `End Class` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     <span data-ttu-id="509e3-117">Declarar el campo como `Private` significa que solo se puede usar dentro de la clase.</span><span class="sxs-lookup"><span data-stu-id="509e3-117">Declaring the field as `Private` means it can be used only within the class.</span></span> <span data-ttu-id="509e3-118">Puede hacer que los campos estén disponibles desde fuera de una clase mediante modificadores de acceso como `Public` que proporcionan más acceso.</span><span class="sxs-lookup"><span data-stu-id="509e3-118">You can make fields available from outside a class by using access modifiers such as `Public` that provide more access.</span></span> <span data-ttu-id="509e3-119">Para obtener más información, consulte [niveles de acceso en Visual Basic](../declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="509e3-119">For more information, see [Access levels in Visual Basic](../declared-elements/access-levels.md).</span></span>  
  
7. <span data-ttu-id="509e3-120">Defina una propiedad para la clase agregando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="509e3-120">Define a property for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8. <span data-ttu-id="509e3-121">Defina un método para la clase agregando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="509e3-121">Define a method for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. <span data-ttu-id="509e3-122">Defina un constructor con parámetros para la nueva clase agregando un procedimiento denominado `Sub New` :</span><span class="sxs-lookup"><span data-stu-id="509e3-122">Define a parameterized constructor for the new class by adding a procedure named `Sub New`:</span></span>  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     <span data-ttu-id="509e3-123">`Sub New`Se llama al constructor automáticamente cuando se crea un objeto basado en esta clase.</span><span class="sxs-lookup"><span data-stu-id="509e3-123">The `Sub New` constructor is called automatically when an object based on this class is created.</span></span> <span data-ttu-id="509e3-124">Este constructor establece el valor del campo que contiene el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="509e3-124">This constructor sets the value of the field that holds the user name.</span></span>  
  
## <a name="to-create-a-button-to-test-the-class"></a><span data-ttu-id="509e3-125">Para crear un botón para probar la clase</span><span class="sxs-lookup"><span data-stu-id="509e3-125">To create a button to test the class</span></span>
  
1. <span data-ttu-id="509e3-126">Cambie el formulario de inicio al modo de diseño; para ello, haga clic con el botón secundario en su nombre en **Explorador de soluciones** y, a continuación, haga clic en **Ver diseñador**.</span><span class="sxs-lookup"><span data-stu-id="509e3-126">Change the startup form to design mode by right-clicking its name in **Solution Explorer** and then clicking **View Designer**.</span></span> <span data-ttu-id="509e3-127">De forma predeterminada, el formulario de inicio para los proyectos de aplicación de Windows se denomina Form1. VB.</span><span class="sxs-lookup"><span data-stu-id="509e3-127">By default, the startup form for Windows Application projects is named Form1.vb.</span></span> <span data-ttu-id="509e3-128">Aparecerá el formulario principal.</span><span class="sxs-lookup"><span data-stu-id="509e3-128">The main form will then appear.</span></span>  
  
2. <span data-ttu-id="509e3-129">Agregue un botón al formulario principal y haga doble clic en él para mostrar el código del `Button1_Click` controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="509e3-129">Add a button to the main form and double-click it to display the code for the `Button1_Click` event handler.</span></span> <span data-ttu-id="509e3-130">Agregue el código siguiente para llamar al procedimiento de prueba:</span><span class="sxs-lookup"><span data-stu-id="509e3-130">Add the following code to call the test procedure:</span></span>  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a><span data-ttu-id="509e3-131">Para ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="509e3-131">To run your application</span></span>
  
1. <span data-ttu-id="509e3-132">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="509e3-132">Run your application by pressing F5.</span></span> <span data-ttu-id="509e3-133">Haga clic en el botón del formulario para llamar al procedimiento de prueba.</span><span class="sxs-lookup"><span data-stu-id="509e3-133">Click the button on the form to call the test procedure.</span></span> <span data-ttu-id="509e3-134">Muestra un mensaje que indica que el original `UserName` es "Moore, Alberto", porque el procedimiento llamó al `Capitalize` método del objeto.</span><span class="sxs-lookup"><span data-stu-id="509e3-134">It displays a message stating that the original `UserName` is "MOORE, BOBBY", because the procedure called the `Capitalize` method of the object.</span></span>  
  
2. <span data-ttu-id="509e3-135">Haga clic en **Aceptar** para descartar el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="509e3-135">Click **OK** to dismiss the message box.</span></span> <span data-ttu-id="509e3-136">El `Button1 Click` procedimiento cambia el valor de la `UserName` propiedad y muestra un mensaje que indica que el nuevo valor de `UserName` es "Worden, Joe".</span><span class="sxs-lookup"><span data-stu-id="509e3-136">The `Button1 Click` procedure changes the value of the `UserName` property and displays a message stating that the new value of `UserName` is "Worden, Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="509e3-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="509e3-137">See also</span></span>

- [<span data-ttu-id="509e3-138">Programación orientada a objetos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="509e3-138">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
- [<span data-ttu-id="509e3-139">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="509e3-139">Objects and Classes</span></span>](index.md)
