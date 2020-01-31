---
title: para agregar controles sin una interfaz de usuario
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- NonVisualSelection
helpviewer_keywords:
- invisible controls [Windows Forms]
- Windows Forms controls, adding to form
- controls [Windows Forms], nonvisual
- Windows Forms controls, nonvisual
- nonvisual controls [Windows Forms]
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
ms.openlocfilehash: 43f13b4f009fcd6e5d82fa2c00113a77d48877b6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744758"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a><span data-ttu-id="772cc-102">Cómo: Agregar controles sin una interfaz de usuario a formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="772cc-102">How to: Add Controls Without a User Interface to Windows Forms</span></span>

<span data-ttu-id="772cc-103">Un control (o componente) no visual proporciona funcionalidad a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="772cc-103">A nonvisual control (or component) provides functionality to your application.</span></span> <span data-ttu-id="772cc-104">A diferencia de otros controles, los componentes no proporcionan una interfaz de usuario al usuario y, por tanto, no es necesario que se muestren en la superficie de Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="772cc-104">Unlike other controls, components do not provide a user interface to the user and thus do not need to be displayed on the Windows Forms Designer surface.</span></span> <span data-ttu-id="772cc-105">Cuando se agrega un componente a un formulario, el Diseñador de Windows Forms muestra una bandeja de tamaño variable en la parte inferior del formulario donde se muestran todos los componentes.</span><span class="sxs-lookup"><span data-stu-id="772cc-105">When a component is added to a form, the Windows Forms Designer displays a resizable tray at the bottom of the form where all components are displayed.</span></span> <span data-ttu-id="772cc-106">Una vez que se ha agregado un control a la bandeja de componentes, puede seleccionar el componente y establecer sus propiedades como lo haría con cualquier otro control del formulario.</span><span class="sxs-lookup"><span data-stu-id="772cc-106">Once a control has been added to the component tray, you can select the component and set its properties as you would any other control on the form.</span></span>

## <a name="add-a-component-to-a-windows-form"></a><span data-ttu-id="772cc-107">Agregar un componente a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="772cc-107">Add a component to a Windows Form</span></span>

1. <span data-ttu-id="772cc-108">Abra el formulario en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="772cc-108">Open the form in Visual Studio.</span></span> <span data-ttu-id="772cc-109">Para obtener más información, vea [Cómo: mostrar Windows Forms en el diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="772cc-109">For details, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="772cc-110">En el **cuadro de herramientas**, haga clic en un componente y arrástrelo al formulario.</span><span class="sxs-lookup"><span data-stu-id="772cc-110">In the **Toolbox**, click a component and drag it to your form.</span></span>

     <span data-ttu-id="772cc-111">El componente aparecerá en la bandeja de componentes.</span><span class="sxs-lookup"><span data-stu-id="772cc-111">Your component appears in the component tray.</span></span>

<span data-ttu-id="772cc-112">Además, los componentes se pueden agregar a un formulario en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="772cc-112">Furthermore, components can be added to a form at run time.</span></span> <span data-ttu-id="772cc-113">Se trata de un escenario común, especialmente porque los componentes no tienen una expresión visual, a diferencia de los controles que tienen una interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="772cc-113">This is a common scenario, especially because components do not have a visual expression, unlike controls that have a user interface.</span></span> <span data-ttu-id="772cc-114">En el ejemplo siguiente, se agrega un componente de <xref:System.Windows.Forms.Timer> en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="772cc-114">In the example below, a <xref:System.Windows.Forms.Timer> component is added at run time.</span></span> <span data-ttu-id="772cc-115">(Tenga en cuenta que Visual Studio contiene varios temporizadores diferentes; en este caso, use un componente de <xref:System.Windows.Forms.Timer> de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="772cc-115">(Note that Visual Studio contains a number of different timers; in this case, use a Windows Forms <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="772cc-116">Para obtener más información sobre los diferentes temporizadores en Visual Studio, consulte [Introducción a los temporizadores basados en servidor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="772cc-116">For more information about the different timers in Visual Studio, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)</span></span>

> [!CAUTION]
> <span data-ttu-id="772cc-117">Los componentes suelen tener propiedades específicas del control que se deben establecer para que el componente funcione de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="772cc-117">Components often have control-specific properties that must be set for the component to function effectively.</span></span> <span data-ttu-id="772cc-118">En el caso del <xref:System.Windows.Forms.Timer> componente siguiente, establezca la propiedad `Interval`.</span><span class="sxs-lookup"><span data-stu-id="772cc-118">In the case of the <xref:System.Windows.Forms.Timer> component below, you set the `Interval` property.</span></span> <span data-ttu-id="772cc-119">Asegúrese de que, al agregar componentes al proyecto, establezca las propiedades necesarias para ese componente.</span><span class="sxs-lookup"><span data-stu-id="772cc-119">Be sure, when adding components to your project, that you set the properties necessary for that component.</span></span>

## <a name="add-a-component-to-a-windows-form-programmatically"></a><span data-ttu-id="772cc-120">Agregar un componente a un formulario de Windows Forms mediante programación</span><span class="sxs-lookup"><span data-stu-id="772cc-120">Add a component to a Windows Form programmatically</span></span>

1. <span data-ttu-id="772cc-121">Cree una instancia de la clase <xref:System.Windows.Forms.Timer> en el código.</span><span class="sxs-lookup"><span data-stu-id="772cc-121">Create an instance of the <xref:System.Windows.Forms.Timer> class in code.</span></span>

2. <span data-ttu-id="772cc-122">Establezca la propiedad `Interval` para determinar el tiempo entre los tics del temporizador.</span><span class="sxs-lookup"><span data-stu-id="772cc-122">Set the `Interval` property to determine the time between ticks of the timer.</span></span>

3. <span data-ttu-id="772cc-123">Configure cualquier otra propiedad necesaria para el componente.</span><span class="sxs-lookup"><span data-stu-id="772cc-123">Configure any other necessary properties for your component.</span></span>

     <span data-ttu-id="772cc-124">En el código siguiente se muestra la creación de un <xref:System.Windows.Forms.Timer> con su conjunto de propiedades `Interval`.</span><span class="sxs-lookup"><span data-stu-id="772cc-124">The following code shows the creation of a <xref:System.Windows.Forms.Timer> with its `Interval` property set.</span></span>

    ```vb
    Public Sub CreateTimer()
       Dim timerKeepTrack As New System.Windows.Forms.Timer
       timerKeepTrack.Interval = 1000
    End Sub
    ```

    ```csharp
    public void createTimer()
    {
       System.Windows.Forms.Timer timerKeepTrack = new
           System.Windows.Forms.Timer();
       timerKeepTrack.Interval = 1000;
    }
    ```

    ```cpp
    public:
       void createTimer()
       {
          System::Windows::Forms::Timer^ timerKeepTrack = gcnew
             System::Windows::Forms::Timer();
          timerKeepTrack->Interval = 1000;
       }
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="772cc-125">Puede exponer el equipo local a un riesgo de seguridad a través de la red haciendo referencia a un UserControl malintencionado.</span><span class="sxs-lookup"><span data-stu-id="772cc-125">You might expose your local computer to a security risk through the network by referencing a malicious UserControl.</span></span> <span data-ttu-id="772cc-126">Esto solo suponer un problema en el caso de que una persona malintencionada cree un control personalizado perjudicial y, después, lo agregue por error a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="772cc-126">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>

## <a name="see-also"></a><span data-ttu-id="772cc-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="772cc-127">See also</span></span>

- [<span data-ttu-id="772cc-128">Controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="772cc-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="772cc-129">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="772cc-129">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="772cc-130">Procedimiento para agregar controles ActiveX a formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="772cc-130">How to: Add ActiveX Controls to Windows Forms</span></span>](how-to-add-activex-controls-to-windows-forms.md)
- [<span data-ttu-id="772cc-131">Insertar controles en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="772cc-131">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
- [<span data-ttu-id="772cc-132">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="772cc-132">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="772cc-133">Controles que se utilizan en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="772cc-133">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="772cc-134">Controles de formularios Windows Forms por función</span><span class="sxs-lookup"><span data-stu-id="772cc-134">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
