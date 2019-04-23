---
title: Procedimiento para agregar controles sin una interfaz de usuario a formularios Windows Forms
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
ms.openlocfilehash: 0768f811653543b3370310ccc0b59890273baf52
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59330108"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a><span data-ttu-id="f69f7-102">Procedimiento para agregar controles sin una interfaz de usuario a formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f69f7-102">How to: Add Controls Without a User Interface to Windows Forms</span></span>
<span data-ttu-id="f69f7-103">Un control no Visual (o componente) proporciona funcionalidad para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f69f7-103">A nonvisual control (or component) provides functionality to your application.</span></span> <span data-ttu-id="f69f7-104">A diferencia de otros controles, componentes no proporcionan una interfaz de usuario para el usuario y, por tanto, no es necesario que se mostrará en la superficie del Diseñador de formularios de Windows.</span><span class="sxs-lookup"><span data-stu-id="f69f7-104">Unlike other controls, components do not provide a user interface to the user and thus do not need to be displayed on the Windows Forms Designer surface.</span></span> <span data-ttu-id="f69f7-105">Cuando se agrega un componente a un formulario, el Diseñador de Windows Forms muestra una bandeja de tamaño variable en la parte inferior del formulario donde se muestran todos los componentes.</span><span class="sxs-lookup"><span data-stu-id="f69f7-105">When a component is added to a form, the Windows Forms Designer displays a resizable tray at the bottom of the form where all components are displayed.</span></span> <span data-ttu-id="f69f7-106">Una vez que un control se ha agregado a la Bandeja de componentes, puede seleccionar el componente y establezca sus propiedades como lo haría con cualquier otro control en el formulario.</span><span class="sxs-lookup"><span data-stu-id="f69f7-106">Once a control has been added to the component tray, you can select the component and set its properties as you would any other control on the form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f69f7-107">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="f69f7-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f69f7-108">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="f69f7-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f69f7-109">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="f69f7-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-a-component-to-a-windows-form"></a><span data-ttu-id="f69f7-110">Para agregar un componente a un formulario de Windows</span><span class="sxs-lookup"><span data-stu-id="f69f7-110">To add a component to a Windows Form</span></span>  
  
1. <span data-ttu-id="f69f7-111">Abra el formulario.</span><span class="sxs-lookup"><span data-stu-id="f69f7-111">Open the form.</span></span> <span data-ttu-id="f69f7-112">Para obtener más detalles, vea [Cómo: Mostrar Windows Forms en el diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f69f7-112">For details, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="f69f7-113">En el **cuadro de herramientas**, haga clic en un componente y arrástrelo al formulario.</span><span class="sxs-lookup"><span data-stu-id="f69f7-113">In the **Toolbox**, click a component and drag it to your form.</span></span>  
  
     <span data-ttu-id="f69f7-114">El componente aparecerá en la Bandeja de componentes.</span><span class="sxs-lookup"><span data-stu-id="f69f7-114">Your component appears in the component tray.</span></span>  
  
 <span data-ttu-id="f69f7-115">Además, se pueden agregar componentes a un formulario en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f69f7-115">Furthermore, components can be added to a form at run time.</span></span> <span data-ttu-id="f69f7-116">Se trata de un escenario común, especialmente porque los componentes no tienen una expresión visual, a diferencia de los controles que tienen una interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="f69f7-116">This is a common scenario, especially because components do not have a visual expression, unlike controls that have a user interface.</span></span> <span data-ttu-id="f69f7-117">En el ejemplo siguiente, un <xref:System.Windows.Forms.Timer> se agrega el componente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f69f7-117">In the example below, a <xref:System.Windows.Forms.Timer> component is added at run time.</span></span> <span data-ttu-id="f69f7-118">(Tenga en cuenta que Visual Studio contiene un número de temporizadores diferentes; en este caso, utilice un formulario Windows Forms <xref:System.Windows.Forms.Timer> componente.</span><span class="sxs-lookup"><span data-stu-id="f69f7-118">(Note that Visual Studio contains a number of different timers; in this case, use a Windows Forms <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="f69f7-119">Para obtener más información sobre los diferentes temporizadores en Visual Studio, consulte [Introducción a los temporizadores basados en servidor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)</span><span class="sxs-lookup"><span data-stu-id="f69f7-119">For more information about the different timers in Visual Studio, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="f69f7-120">A menudo, los componentes tienen propiedades específicas del control que se deben establecer para que el componente funcione de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="f69f7-120">Components often have control-specific properties that must be set for the component to function effectively.</span></span> <span data-ttu-id="f69f7-121">En el caso de los <xref:System.Windows.Forms.Timer> componentes indicados a continuación, Establece el `Interval` propiedad.</span><span class="sxs-lookup"><span data-stu-id="f69f7-121">In the case of the <xref:System.Windows.Forms.Timer> component below, you set the `Interval` property.</span></span> <span data-ttu-id="f69f7-122">Asegúrese de, al agregar componentes al proyecto, Establece las propiedades necesarias para cada componente.</span><span class="sxs-lookup"><span data-stu-id="f69f7-122">Be sure, when adding components to your project, that you set the properties necessary for that component.</span></span>  
  
#### <a name="to-add-a-component-to-a-windows-form-programmatically"></a><span data-ttu-id="f69f7-123">Para agregar un componente a un formulario Windows Forms mediante programación</span><span class="sxs-lookup"><span data-stu-id="f69f7-123">To add a component to a Windows Form programmatically</span></span>  
  
1. <span data-ttu-id="f69f7-124">Cree una instancia de la <xref:System.Windows.Forms.Timer> clase en código.</span><span class="sxs-lookup"><span data-stu-id="f69f7-124">Create an instance of the <xref:System.Windows.Forms.Timer> class in code.</span></span>  
  
2. <span data-ttu-id="f69f7-125">Establecer el `Interval` propiedad para determinar el tiempo entre los pasos del temporizador.</span><span class="sxs-lookup"><span data-stu-id="f69f7-125">Set the `Interval` property to determine the time between ticks of the timer.</span></span>  
  
3. <span data-ttu-id="f69f7-126">Configurar las otras propiedades necesarias para el componente.</span><span class="sxs-lookup"><span data-stu-id="f69f7-126">Configure any other necessary properties for your component.</span></span>  
  
     <span data-ttu-id="f69f7-127">El código siguiente muestra la creación de un <xref:System.Windows.Forms.Timer> con su `Interval` conjunto de propiedades.</span><span class="sxs-lookup"><span data-stu-id="f69f7-127">The following code shows the creation of a <xref:System.Windows.Forms.Timer> with its `Interval` property set.</span></span>  
  
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
    >  <span data-ttu-id="f69f7-128">Puede exponer el equipo local a un riesgo de seguridad a través de la red haciendo referencia a un control de usuario malintencionado.</span><span class="sxs-lookup"><span data-stu-id="f69f7-128">You might expose your local computer to a security risk through the network by referencing a malicious UserControl.</span></span> <span data-ttu-id="f69f7-129">Esto solo sería un problema en el caso de una persona malintencionada cree un control personalizado perjudicial, seguido por el que se agregara a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="f69f7-129">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f69f7-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="f69f7-130">See also</span></span>

- [<span data-ttu-id="f69f7-131">Controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f69f7-131">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="f69f7-132">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f69f7-132">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="f69f7-133">Cómo: Agregar controles ActiveX a formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="f69f7-133">How to: Add ActiveX Controls to Windows Forms</span></span>](how-to-add-activex-controls-to-windows-forms.md)
- [<span data-ttu-id="f69f7-134">Cómo: Copiar controles entre formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="f69f7-134">How to: Copy Controls Between Windows Forms</span></span>](how-to-copy-controls-between-windows-forms.md)
- [<span data-ttu-id="f69f7-135">Insertar controles en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f69f7-135">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
- [<span data-ttu-id="f69f7-136">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="f69f7-136">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="f69f7-137">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f69f7-137">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="f69f7-138">Controles de formularios Windows Forms por función</span><span class="sxs-lookup"><span data-stu-id="f69f7-138">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
