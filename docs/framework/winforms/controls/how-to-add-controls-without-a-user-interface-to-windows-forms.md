---
title: "Cómo: Agregar controles sin una interfaz de usuario a formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3abbf931cff9ad459e8c9221f91430ecccefa9cc
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a><span data-ttu-id="da857-102">Cómo: Agregar controles sin una interfaz de usuario a formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da857-102">How to: Add Controls Without a User Interface to Windows Forms</span></span>
<span data-ttu-id="da857-103">Un control no Visual (o componente) proporciona la funcionalidad a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="da857-103">A nonvisual control (or component) provides functionality to your application.</span></span> <span data-ttu-id="da857-104">A diferencia de otros controles, componentes no proporcionan una interfaz de usuario para el usuario y, por tanto, no es necesario que se mostrará en la superficie del Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="da857-104">Unlike other controls, components do not provide a user interface to the user and thus do not need to be displayed on the Windows Forms Designer surface.</span></span> <span data-ttu-id="da857-105">Cuando se agrega un componente a un formulario, el Diseñador de Windows Forms muestra una bandeja de tamaño variable en la parte inferior del formulario donde se muestran todos los componentes.</span><span class="sxs-lookup"><span data-stu-id="da857-105">When a component is added to a form, the Windows Forms Designer displays a resizable tray at the bottom of the form where all components are displayed.</span></span> <span data-ttu-id="da857-106">Una vez que un control se ha agregado a la Bandeja de componentes, puede seleccionar el componente y establecer sus propiedades tal y como lo haría con cualquier otro control en el formulario.</span><span class="sxs-lookup"><span data-stu-id="da857-106">Once a control has been added to the component tray, you can select the component and set its properties as you would any other control on the form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da857-107">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="da857-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="da857-108">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="da857-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="da857-109">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="da857-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-a-component-to-a-windows-form"></a><span data-ttu-id="da857-110">Para agregar un componente a un formulario Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da857-110">To add a component to a Windows Form</span></span>  
  
1.  <span data-ttu-id="da857-111">Abra el formulario.</span><span class="sxs-lookup"><span data-stu-id="da857-111">Open the form.</span></span> <span data-ttu-id="da857-112">Para obtener más información, consulte [Cómo: mostrar Windows Forms en el diseñador](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span><span class="sxs-lookup"><span data-stu-id="da857-112">For details, see [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span></span>  
  
2.  <span data-ttu-id="da857-113">En el **cuadro de herramientas**, haga clic en un componente y arrástrelo al formulario.</span><span class="sxs-lookup"><span data-stu-id="da857-113">In the **Toolbox**, click a component and drag it to your form.</span></span>  
  
     <span data-ttu-id="da857-114">El componente aparecerá en la Bandeja de componentes.</span><span class="sxs-lookup"><span data-stu-id="da857-114">Your component appears in the component tray.</span></span>  
  
 <span data-ttu-id="da857-115">Además, los componentes se pueden agregar a un formulario en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="da857-115">Furthermore, components can be added to a form at run time.</span></span> <span data-ttu-id="da857-116">Se trata de un escenario común, sobre todo porque los componentes no tienen una expresión visual, a diferencia de los controles que tienen una interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="da857-116">This is a common scenario, especially because components do not have a visual expression, unlike controls that have a user interface.</span></span> <span data-ttu-id="da857-117">En el ejemplo siguiente, un <xref:System.Windows.Forms.Timer> se agrega el componente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="da857-117">In the example below, a <xref:System.Windows.Forms.Timer> component is added at run time.</span></span> <span data-ttu-id="da857-118">(Tenga en cuenta que [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] contiene un número de temporizadores diferentes; en este caso, utilice un formulario Windows Forms <xref:System.Windows.Forms.Timer> componente.</span><span class="sxs-lookup"><span data-stu-id="da857-118">(Note that [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] contains a number of different timers; in this case, use a Windows Forms <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="da857-119">Para obtener más información sobre los diferentes temporizadores en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], consulte [Introducción a los temporizadores basados en servidor](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).)</span><span class="sxs-lookup"><span data-stu-id="da857-119">For more information about the different timers in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], see [Introduction to Server-Based Timers](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="da857-120">Componentes a menudo tienen propiedades específicas del control que se deben establecer para que el componente funcione de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="da857-120">Components often have control-specific properties that must be set for the component to function effectively.</span></span> <span data-ttu-id="da857-121">En el caso de los <xref:System.Windows.Forms.Timer> siguiente componente, establecer el `Interval` propiedad.</span><span class="sxs-lookup"><span data-stu-id="da857-121">In the case of the <xref:System.Windows.Forms.Timer> component below, you set the `Interval` property.</span></span> <span data-ttu-id="da857-122">Debe tener, al agregar componentes al proyecto, se configuran las propiedades necesarias para cada componente.</span><span class="sxs-lookup"><span data-stu-id="da857-122">Be sure, when adding components to your project, that you set the properties necessary for that component.</span></span>  
  
#### <a name="to-add-a-component-to-a-windows-form-programmatically"></a><span data-ttu-id="da857-123">Para agregar un componente a un formulario Windows Forms mediante programación</span><span class="sxs-lookup"><span data-stu-id="da857-123">To add a component to a Windows Form programmatically</span></span>  
  
1.  <span data-ttu-id="da857-124">Cree una instancia de la <xref:System.Windows.Forms.Timer> clase en el código.</span><span class="sxs-lookup"><span data-stu-id="da857-124">Create an instance of the <xref:System.Windows.Forms.Timer> class in code.</span></span>  
  
2.  <span data-ttu-id="da857-125">Establecer el `Interval` propiedad para determinar el tiempo entre los pasos del temporizador.</span><span class="sxs-lookup"><span data-stu-id="da857-125">Set the `Interval` property to determine the time between ticks of the timer.</span></span>  
  
3.  <span data-ttu-id="da857-126">Configure las restantes propiedades necesarias para el componente.</span><span class="sxs-lookup"><span data-stu-id="da857-126">Configure any other necessary properties for your component.</span></span>  
  
     <span data-ttu-id="da857-127">El código siguiente muestra la creación de un <xref:System.Windows.Forms.Timer> con su `Interval` conjunto de propiedades.</span><span class="sxs-lookup"><span data-stu-id="da857-127">The following code shows the creation of a <xref:System.Windows.Forms.Timer> with its `Interval` property set.</span></span>  
  
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
    >  <span data-ttu-id="da857-128">Puede exponer el equipo local a un riesgo de seguridad a través de la red haciendo referencia a un control de usuario malintencionado.</span><span class="sxs-lookup"><span data-stu-id="da857-128">You might expose your local computer to a security risk through the network by referencing a malicious UserControl.</span></span> <span data-ttu-id="da857-129">Esto solo sería un problema en el caso de una persona malintencionada cree un control personalizado perjudicial, seguido por el que se agregara a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="da857-129">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da857-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="da857-130">See Also</span></span>  
 [<span data-ttu-id="da857-131">Controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da857-131">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="da857-132">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da857-132">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [<span data-ttu-id="da857-133">Procedimiento para agregar controles ActiveX a formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da857-133">How to: Add ActiveX Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [<span data-ttu-id="da857-134">Procedimiento para copiar controles entre formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da857-134">How to: Copy Controls Between Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-copy-controls-between-windows-forms.md)  
 [<span data-ttu-id="da857-135">Insertar controles en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da857-135">Putting Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)  
 [<span data-ttu-id="da857-136">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="da857-136">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="da857-137">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da857-137">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="da857-138">Controles de formularios Windows Forms por función</span><span class="sxs-lookup"><span data-stu-id="da857-138">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
