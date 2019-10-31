---
title: 'Tutorial: Actualizar la información de la barra de estado en tiempo de ejecución'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], updating at run time
- status bars [Windows Forms], refreshing panels
- StatusBar control [Windows Forms], refreshing panels
- panels [Windows Forms], refreshing status bar
ms.assetid: cc2abb06-c082-49f7-a5a3-2fd1bbcb58d1
ms.openlocfilehash: f1d22079dfa3a6452efb74ef57530bb43e059a4a
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197102"
---
# <a name="walkthrough-updating-status-bar-information-at-run-time"></a><span data-ttu-id="a13c5-102">Tutorial: Actualizar la información de la barra de estado en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a13c5-102">Walkthrough: Updating Status Bar Information at Run Time</span></span>
> [!IMPORTANT]
> <span data-ttu-id="a13c5-103">Los controles <xref:System.Windows.Forms.StatusStrip> y <xref:System.Windows.Forms.ToolStripStatusLabel> reemplazan y agregan funcionalidad a los controles <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel>; sin embargo, los controles <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel> se conservan por compatibilidad con versiones anteriores y uso futuro, si así lo decide.</span><span class="sxs-lookup"><span data-stu-id="a13c5-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="a13c5-104">Con frecuencia, un programa llamará para que actualice el contenido de los paneles de la barra de estado dinámicamente en tiempo de ejecución, en función de los cambios de estado de la aplicación u otra interacción del usuario.</span><span class="sxs-lookup"><span data-stu-id="a13c5-104">Often, a program will call for you to update the contents of status bar panels dynamically at run time, based on changes to application state or other user interaction.</span></span> <span data-ttu-id="a13c5-105">Se trata de una manera habitual de indicar a los usuarios que teclas tales como Bloq Mayús, Bloq Num o BLOQ DESPL están habilitadas o para proporcionar la fecha o un reloj como referencia cómoda.</span><span class="sxs-lookup"><span data-stu-id="a13c5-105">This is a common way to signal users that keys such as the CAPS LOCK, NUM LOCK, or SCROLL LOCK are enabled, or to provide the date or a clock as a convenient reference.</span></span>  
  
 <span data-ttu-id="a13c5-106">En el ejemplo siguiente, utilizará una instancia de la clase <xref:System.Windows.Forms.StatusBarPanel> para hospedar un reloj.</span><span class="sxs-lookup"><span data-stu-id="a13c5-106">In the following example, you will use an instance of the <xref:System.Windows.Forms.StatusBarPanel> class to host a clock.</span></span>  
  
### <a name="to-get-the-status-bar-ready-for-updating"></a><span data-ttu-id="a13c5-107">Para preparar la barra de estado para la actualización</span><span class="sxs-lookup"><span data-stu-id="a13c5-107">To get the status bar ready for updating</span></span>  
  
1. <span data-ttu-id="a13c5-108">Cree un nuevo formulario Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a13c5-108">Create a new Windows form.</span></span>  
  
2. <span data-ttu-id="a13c5-109">Agregue un control <xref:System.Windows.Forms.StatusBar> al formulario.</span><span class="sxs-lookup"><span data-stu-id="a13c5-109">Add a <xref:System.Windows.Forms.StatusBar> control to your form.</span></span> <span data-ttu-id="a13c5-110">Para ver detalles, consulte [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a13c5-110">For details, see [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
3. <span data-ttu-id="a13c5-111">Agregue un panel de barra de estado al control <xref:System.Windows.Forms.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="a13c5-111">Add a status bar panel to your <xref:System.Windows.Forms.StatusBar> control.</span></span> <span data-ttu-id="a13c5-112">Para ver detalles, consulte [Cómo: Agregar paneles a un control StatusBar](how-to-add-panels-to-a-statusbar-control.md).</span><span class="sxs-lookup"><span data-stu-id="a13c5-112">For details, see [How to: Add Panels to a StatusBar Control](how-to-add-panels-to-a-statusbar-control.md).</span></span>  
  
4. <span data-ttu-id="a13c5-113">Para el control <xref:System.Windows.Forms.StatusBar> que ha agregado al formulario, establezca la propiedad <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="a13c5-113">For the <xref:System.Windows.Forms.StatusBar> control you added to your form, set the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true`.</span></span>  
  
5. <span data-ttu-id="a13c5-114">Agregue un componente de <xref:System.Windows.Forms.Timer> de Windows Forms al formulario.</span><span class="sxs-lookup"><span data-stu-id="a13c5-114">Add a Windows Forms <xref:System.Windows.Forms.Timer> component to the form.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a13c5-115">El componente de <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> de Windows Forms está diseñado para un entorno de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a13c5-115">The Windows Forms <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="a13c5-116">Si necesita un temporizador que sea adecuado para un entorno de servidor, consulte [Introducción a los temporizadores basados en servidor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="a13c5-116">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
6. <span data-ttu-id="a13c5-117">Establezca la propiedad <xref:System.Windows.Forms.Timer.Enabled%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="a13c5-117">Set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true`.</span></span>  
  
7. <span data-ttu-id="a13c5-118">Establezca la propiedad <xref:System.Windows.Forms.Timer.Interval%2A> del <xref:System.Windows.Forms.Timer> en 30000.</span><span class="sxs-lookup"><span data-stu-id="a13c5-118">Set the <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> to 30000.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a13c5-119">La propiedad <xref:System.Windows.Forms.Timer.Interval%2A> del componente <xref:System.Windows.Forms.Timer> se establece en 30 segundos (30.000 milisegundos) para asegurarse de que se refleja una hora precisa en el tiempo mostrado.</span><span class="sxs-lookup"><span data-stu-id="a13c5-119">The <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> component is set to 30 seconds (30,000 milliseconds) to ensure that an accurate time is reflected in the time displayed.</span></span>  
  
### <a name="to-implement-the-timer-to-update-the-status-bar"></a><span data-ttu-id="a13c5-120">Para implementar el temporizador para que se actualice la barra de estado</span><span class="sxs-lookup"><span data-stu-id="a13c5-120">To implement the timer to update the status bar</span></span>  
  
1. <span data-ttu-id="a13c5-121">Inserte el código siguiente en el controlador de eventos del componente <xref:System.Windows.Forms.Timer> para actualizar el panel del control <xref:System.Windows.Forms.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="a13c5-121">Insert the following code into the event handler of the <xref:System.Windows.Forms.Timer> component to update the panel of the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
    ```vb  
    Private Sub Timer1_Tick(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
       StatusBar1.Panels(0).Text = Now.ToShortTimeString  
    End Sub  
    ```  
  
    ```csharp  
    private void timer1_Tick(object sender, System.EventArgs e)  
    {  
       statusBar1.Panels[0].Text = DateTime.Now.ToShortTimeString();  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void timer1_Tick(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        statusBar1->Panels[0]->Text =  
          DateTime::Now.ToShortTimeString();  
      }  
    ```  
  
     <span data-ttu-id="a13c5-122">Ahora está listo para ejecutar la aplicación y observar el reloj en ejecución en el panel de la barra de estado.</span><span class="sxs-lookup"><span data-stu-id="a13c5-122">At this point, you are ready to run the application and observe the clock running in the status bar panel.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="a13c5-123">Para probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="a13c5-123">To test the application</span></span>  
  
1. <span data-ttu-id="a13c5-124">Depure la aplicación y presione F5 para ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="a13c5-124">Debug the application and press F5 to run it.</span></span> <span data-ttu-id="a13c5-125">Para más detalles sobre la depuración, consulte [Depurar en Visual Studio](/visualstudio/debugger/debugger-feature-tour).</span><span class="sxs-lookup"><span data-stu-id="a13c5-125">For details about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugger-feature-tour).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a13c5-126">El reloj tardará aproximadamente 30 segundos en aparecer en la barra de estado.</span><span class="sxs-lookup"><span data-stu-id="a13c5-126">It will take approximately 30 seconds for the clock to appear in the status bar.</span></span> <span data-ttu-id="a13c5-127">El objetivo es obtener la hora más precisa posible.</span><span class="sxs-lookup"><span data-stu-id="a13c5-127">This is to get the most accurate time possible.</span></span> <span data-ttu-id="a13c5-128">Por el contrario, para que el reloj aparezca antes, puede reducir el valor de la propiedad <xref:System.Windows.Forms.Timer.Interval%2A> establecida en el paso 7 del procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="a13c5-128">Conversely, to make the clock appear sooner, you can reduce the value of the <xref:System.Windows.Forms.Timer.Interval%2A> property you set in step 7 in the previous procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a13c5-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="a13c5-129">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="a13c5-130">Agregar paneles a un control StatusBar</span><span class="sxs-lookup"><span data-stu-id="a13c5-130">How to: Add Panels to a StatusBar Control</span></span>](how-to-add-panels-to-a-statusbar-control.md)
- [<span data-ttu-id="a13c5-131">Determinar en qué panel del control StatusBar de Windows Forms se hizo clic</span><span class="sxs-lookup"><span data-stu-id="a13c5-131">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [<span data-ttu-id="a13c5-132">Información general sobre StatusBar (Control)</span><span class="sxs-lookup"><span data-stu-id="a13c5-132">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
