---
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
ms.openlocfilehash: 646c6ce307131f3edba194af19920eade9c1753c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84389119"
---
# <a name="walkthrough-defining-classes-visual-basic"></a><span data-ttu-id="b4ac6-102">Tutorial: Definir clases (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4ac6-102">Walkthrough: Defining Classes (Visual Basic)</span></span>

<span data-ttu-id="b4ac6-103">En este tutorial se muestra cómo definir clases, que puede usar para crear objetos.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-103">This walkthrough demonstrates how to define classes, which you can then use to create objects.</span></span> <span data-ttu-id="b4ac6-104">También se muestra cómo agregar propiedades y métodos a la nueva clase y se muestra cómo inicializar un objeto.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-104">It also shows you how to add properties and methods to the new class, and demonstrates how to initialize an object.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a><span data-ttu-id="b4ac6-105">Para definir una clase</span><span class="sxs-lookup"><span data-stu-id="b4ac6-105">To define a class</span></span>
  
1. <span data-ttu-id="b4ac6-106">Cree un proyecto haciendo clic en **nuevo proyecto** en el menú **archivo** .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-106">Create a project by clicking **New Project** on the **File** menu.</span></span> <span data-ttu-id="b4ac6-107">Aparecerá el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-107">The **New Project** dialog box appears.</span></span>  
  
2. <span data-ttu-id="b4ac6-108">Seleccione aplicación de Windows en la lista de Visual Basic plantillas de proyecto para mostrar el nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-108">Select Windows Application from the list of Visual Basic project templates to display the new project.</span></span>  
  
3. <span data-ttu-id="b4ac6-109">Agregue una nueva clase al proyecto haciendo clic en **Agregar clase** en el menú **proyecto** .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-109">Add a new class to the project by clicking **Add Class** on the **Project** menu.</span></span> <span data-ttu-id="b4ac6-110">Aparecerá el cuadro de diálogo **Agregar nuevo elemento** .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-110">The **Add New Item** dialog box appears.</span></span>  
  
4. <span data-ttu-id="b4ac6-111">Seleccione la plantilla **clase** .</span><span class="sxs-lookup"><span data-stu-id="b4ac6-111">Select the **Class** template.</span></span>  
  
5. <span data-ttu-id="b4ac6-112">Asigne a la nueva clase el nombre `UserNameInfo.vb` y, a continuación, haga clic en **Agregar** para mostrar el código de la nueva clase.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-112">Name the new class `UserNameInfo.vb`, and then click **Add** to display the code for the new class.</span></span>  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    > <span data-ttu-id="b4ac6-113">Puede usar el editor de **código** de Visual Basic para agregar una clase al formulario de inicio escribiendo la `Class` palabra clave seguida del nombre de la nueva clase.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-113">You can use the Visual Basic **Code Editor** to add a class to your startup form by typing the `Class` keyword followed by the name of the new class.</span></span> <span data-ttu-id="b4ac6-114">El **Editor de código** proporciona una `End Class` instrucción correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-114">The **Code Editor** provides a corresponding `End Class` statement for you.</span></span>  
  
6. <span data-ttu-id="b4ac6-115">Defina un campo privado para la clase agregando el código siguiente entre las `Class` `End Class` instrucciones y:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-115">Define a private field for the class by adding the following code between the `Class` and `End Class` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     <span data-ttu-id="b4ac6-116">Declarar el campo como `Private` significa que solo se puede usar dentro de la clase.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-116">Declaring the field as `Private` means it can be used only within the class.</span></span> <span data-ttu-id="b4ac6-117">Puede hacer que los campos estén disponibles desde fuera de una clase mediante modificadores de acceso como `Public` que proporcionan más acceso.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-117">You can make fields available from outside a class by using access modifiers such as `Public` that provide more access.</span></span> <span data-ttu-id="b4ac6-118">Para obtener más información, consulte [niveles de acceso en Visual Basic](../declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="b4ac6-118">For more information, see [Access levels in Visual Basic](../declared-elements/access-levels.md).</span></span>  
  
7. <span data-ttu-id="b4ac6-119">Defina una propiedad para la clase agregando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-119">Define a property for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8. <span data-ttu-id="b4ac6-120">Defina un método para la clase agregando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-120">Define a method for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. <span data-ttu-id="b4ac6-121">Defina un constructor con parámetros para la nueva clase agregando un procedimiento denominado `Sub New` :</span><span class="sxs-lookup"><span data-stu-id="b4ac6-121">Define a parameterized constructor for the new class by adding a procedure named `Sub New`:</span></span>  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     <span data-ttu-id="b4ac6-122">`Sub New`Se llama al constructor automáticamente cuando se crea un objeto basado en esta clase.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-122">The `Sub New` constructor is called automatically when an object based on this class is created.</span></span> <span data-ttu-id="b4ac6-123">Este constructor establece el valor del campo que contiene el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-123">This constructor sets the value of the field that holds the user name.</span></span>  
  
## <a name="to-create-a-button-to-test-the-class"></a><span data-ttu-id="b4ac6-124">Para crear un botón para probar la clase</span><span class="sxs-lookup"><span data-stu-id="b4ac6-124">To create a button to test the class</span></span>
  
1. <span data-ttu-id="b4ac6-125">Cambie el formulario de inicio al modo de diseño; para ello, haga clic con el botón secundario en su nombre en **Explorador de soluciones** y, a continuación, haga clic en **Ver diseñador**.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-125">Change the startup form to design mode by right-clicking its name in **Solution Explorer** and then clicking **View Designer**.</span></span> <span data-ttu-id="b4ac6-126">De forma predeterminada, el formulario de inicio para los proyectos de aplicación de Windows se denomina Form1. VB.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-126">By default, the startup form for Windows Application projects is named Form1.vb.</span></span> <span data-ttu-id="b4ac6-127">Aparecerá el formulario principal.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-127">The main form will then appear.</span></span>  
  
2. <span data-ttu-id="b4ac6-128">Agregue un botón al formulario principal y haga doble clic en él para mostrar el código del `Button1_Click` controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-128">Add a button to the main form and double-click it to display the code for the `Button1_Click` event handler.</span></span> <span data-ttu-id="b4ac6-129">Agregue el código siguiente para llamar al procedimiento de prueba:</span><span class="sxs-lookup"><span data-stu-id="b4ac6-129">Add the following code to call the test procedure:</span></span>  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a><span data-ttu-id="b4ac6-130">Para ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="b4ac6-130">To run your application</span></span>
  
1. <span data-ttu-id="b4ac6-131">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-131">Run your application by pressing F5.</span></span> <span data-ttu-id="b4ac6-132">Haga clic en el botón del formulario para llamar al procedimiento de prueba.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-132">Click the button on the form to call the test procedure.</span></span> <span data-ttu-id="b4ac6-133">Muestra un mensaje que indica que el original `UserName` es "Moore, Alberto", porque el procedimiento llamó al `Capitalize` método del objeto.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-133">It displays a message stating that the original `UserName` is "MOORE, BOBBY", because the procedure called the `Capitalize` method of the object.</span></span>  
  
2. <span data-ttu-id="b4ac6-134">Haga clic en **Aceptar** para descartar el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="b4ac6-134">Click **OK** to dismiss the message box.</span></span> <span data-ttu-id="b4ac6-135">El `Button1 Click` procedimiento cambia el valor de la `UserName` propiedad y muestra un mensaje que indica que el nuevo valor de `UserName` es "Worden, Joe".</span><span class="sxs-lookup"><span data-stu-id="b4ac6-135">The `Button1 Click` procedure changes the value of the `UserName` property and displays a message stating that the new value of `UserName` is "Worden, Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4ac6-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b4ac6-136">See also</span></span>

- [<span data-ttu-id="b4ac6-137">Programación orientada a objetos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4ac6-137">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
- [<span data-ttu-id="b4ac6-138">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="b4ac6-138">Objects and Classes</span></span>](index.md)
