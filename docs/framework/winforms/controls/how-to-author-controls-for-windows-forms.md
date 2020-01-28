---
title: 'Cómo: crear controles'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], creating
- UserControl class [Windows Forms], Windows Forms
- custom controls [Windows Forms], creating
ms.assetid: 7570e982-545b-4c3a-a7c7-55581d313400
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 169104f51898f9bda08efa08685207e50406a7ff
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746722"
---
# <a name="how-to-author-controls-for-windows-forms"></a><span data-ttu-id="e73b3-102">Cómo: crear controles para Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e73b3-102">How to: Author controls for Windows Forms</span></span>

<span data-ttu-id="e73b3-103">Un control representa un vínculo gráfico entre el usuario y el programa.</span><span class="sxs-lookup"><span data-stu-id="e73b3-103">A control represents a graphical link between the user and the program.</span></span> <span data-ttu-id="e73b3-104">Un control puede proporcionar o procesar datos, aceptar datos proporcionados por el usuario, responder a eventos o ejecutar cualquier otra función que conecte al usuario con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e73b3-104">A control can provide or process data, accept user input, respond to events, or perform any number of other functions that connect the user and the application.</span></span> <span data-ttu-id="e73b3-105">Dado que los controles son básicamente componentes con una interfaz gráfica, pueden ejecutar las mismas funciones que realizan los componentes, así como proporcionar interacción con los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e73b3-105">Because a control is essentially a component with a graphical interface, it can serve any function that a component does, as well as provide user interaction.</span></span> <span data-ttu-id="e73b3-106">Los controles se crean con un propósito específico; la creación de controles no es más que una tarea de programación como otra cualquiera.</span><span class="sxs-lookup"><span data-stu-id="e73b3-106">Controls are created to serve specific purposes, and authoring controls is just another programming task.</span></span> <span data-ttu-id="e73b3-107">Teniendo esto en cuenta, los pasos siguientes representan información general sobre el proceso de creación de controles.</span><span class="sxs-lookup"><span data-stu-id="e73b3-107">With that in mind, the following steps represent an overview of the control authoring process.</span></span> <span data-ttu-id="e73b3-108">Los vínculos proporcionan información adicional sobre cada paso.</span><span class="sxs-lookup"><span data-stu-id="e73b3-108">Links provide additional information on the individual steps.</span></span>

## <a name="to-author-a-control"></a><span data-ttu-id="e73b3-109">Para crear un control</span><span class="sxs-lookup"><span data-stu-id="e73b3-109">To author a control</span></span>

1. <span data-ttu-id="e73b3-110">Determine qué desea que haga el control o qué función desempeñará en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e73b3-110">Determine what you want your control to accomplish, or what part it will play in your application.</span></span> <span data-ttu-id="e73b3-111">Debe tener en cuenta los siguientes factores:</span><span class="sxs-lookup"><span data-stu-id="e73b3-111">Factors to consider are:</span></span>

    - <span data-ttu-id="e73b3-112">¿Qué tipo de interfaz gráfica necesita?</span><span class="sxs-lookup"><span data-stu-id="e73b3-112">What kind of graphical interface do you need?</span></span>

    - <span data-ttu-id="e73b3-113">¿De qué interacciones específicas con el usuario se ocupará este control?</span><span class="sxs-lookup"><span data-stu-id="e73b3-113">What specific user interactions will this control handle?</span></span>

    - <span data-ttu-id="e73b3-114">¿Existe algún control que proporcione la funcionalidad que necesita?</span><span class="sxs-lookup"><span data-stu-id="e73b3-114">Is the functionality you need provided by any existing controls?</span></span>

    - <span data-ttu-id="e73b3-115">¿Puede obtener la funcionalidad necesaria mediante la combinación de varios controles de Windows Forms?</span><span class="sxs-lookup"><span data-stu-id="e73b3-115">Can you get the functionality you need by combining several Windows Forms controls?</span></span>

2. <span data-ttu-id="e73b3-116">Si necesita un modelo de objetos para el control, determine cómo se distribuirá la funcionalidad a través del modelo de objetos y divídala entre el control y los objetos secundarios.</span><span class="sxs-lookup"><span data-stu-id="e73b3-116">If you need an object model for your control, determine how functionality will be distributed throughout the object model, and divide up functionality between the control and any subobjects.</span></span> <span data-ttu-id="e73b3-117">Un modelo de objetos puede resultar útil si piensa crear un control complejo o desea incorporar varias funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="e73b3-117">An object model may be useful if you are planning a complex control, or want to incorporate several functionalities.</span></span>

3. <span data-ttu-id="e73b3-118">Determine el tipo de control (por ejemplo, un control de usuario, un control personalizado o un control heredado de Windows Forms) que necesita.</span><span class="sxs-lookup"><span data-stu-id="e73b3-118">Determine the type of control (for example, user control, custom control, inherited Windows Forms control) you need.</span></span> <span data-ttu-id="e73b3-119">Para más información, consulte [Recomendaciones sobre tipos de controles](control-type-recommendations.md) y [Variedades de controles personalizados](varieties-of-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="e73b3-119">For details, see [Control Type Recommendations](control-type-recommendations.md) and [Varieties of Custom Controls](varieties-of-custom-controls.md).</span></span>

4. <span data-ttu-id="e73b3-120">Exprese la funcionalidad en forma de propiedades, métodos y eventos del control y sus objetos secundarios o estructuras subsidiarias, y asigne los niveles de acceso adecuados (por ejemplo, público, protegido, etc.).</span><span class="sxs-lookup"><span data-stu-id="e73b3-120">Express functionality as properties, methods, and events of the control and its subobjects or subsidiary structures, and assign appropriate access levels (for example, public, protected, and so on).</span></span>

5. <span data-ttu-id="e73b3-121">Si necesita que el control utilice una representación personalizada, agregue el código necesario.</span><span class="sxs-lookup"><span data-stu-id="e73b3-121">If you need custom painting for your control, add code for it.</span></span> <span data-ttu-id="e73b3-122">Para información detallada, vea [Dibujo y representación personalizados de controles](custom-control-painting-and-rendering.md).</span><span class="sxs-lookup"><span data-stu-id="e73b3-122">For details, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>

6. <span data-ttu-id="e73b3-123">Si el control hereda de <xref:System.Windows.Forms.UserControl>, puede probar su comportamiento en tiempo de ejecución compilando el proyecto de control y ejecutando en el **contenedor de pruebas de UserControl**.</span><span class="sxs-lookup"><span data-stu-id="e73b3-123">If your control inherits from <xref:System.Windows.Forms.UserControl>, you can test its runtime behavior by building the control project and running it in the **UserControl Test Container**.</span></span> <span data-ttu-id="e73b3-124">Para más información, consulte [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="e73b3-124">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

7. <span data-ttu-id="e73b3-125">También puede probar y depurar el control creando un nuevo proyecto, como una Aplicación Windows, y colocándola en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="e73b3-125">You can also test and debug your control by creating a new project, such as a Windows Application, and placing it into a container.</span></span> <span data-ttu-id="e73b3-126">Este proceso se muestra como parte del [Tutorial: crear un control compuesto](walkthrough-authoring-a-composite-control-with-visual-csharp.md).</span><span class="sxs-lookup"><span data-stu-id="e73b3-126">This process is demonstrated as part of [Walkthrough: Authoring a Composite Control](walkthrough-authoring-a-composite-control-with-visual-csharp.md).</span></span>

8. <span data-ttu-id="e73b3-127">A medida que agrega cada característica, agregue características al proyecto de prueba para ejecutar la nueva funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="e73b3-127">As you add each feature, add features to your test project to exercise the new functionality.</span></span>

9. <span data-ttu-id="e73b3-128">Repita este proceso para refinar el diseño.</span><span class="sxs-lookup"><span data-stu-id="e73b3-128">Repeat, refining the design.</span></span>

10. <span data-ttu-id="e73b3-129">Empaquete e implemente el control.</span><span class="sxs-lookup"><span data-stu-id="e73b3-129">Package and deploy your control.</span></span> <span data-ttu-id="e73b3-130">Para obtener más información, vea [primer vistazo a la implementación en Visual Studio](/visualstudio/deployment/deploying-applications-services-and-components).</span><span class="sxs-lookup"><span data-stu-id="e73b3-130">For details, see [First look at deployment in Visual Studio](/visualstudio/deployment/deploying-applications-services-and-components).</span></span>

## <a name="see-also"></a><span data-ttu-id="e73b3-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="e73b3-131">See also</span></span>

- [<span data-ttu-id="e73b3-132">Cómo: Heredar de una clase UserControl</span><span class="sxs-lookup"><span data-stu-id="e73b3-132">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="e73b3-133">Cómo: Heredar de la clase control</span><span class="sxs-lookup"><span data-stu-id="e73b3-133">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="e73b3-134">Cómo: Heredar de controles de Windows Forms existentes</span><span class="sxs-lookup"><span data-stu-id="e73b3-134">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)
- [<span data-ttu-id="e73b3-135">Cómo: Comprobar el comportamiento de una clase UserControl en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e73b3-135">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [<span data-ttu-id="e73b3-136">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="e73b3-136">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
