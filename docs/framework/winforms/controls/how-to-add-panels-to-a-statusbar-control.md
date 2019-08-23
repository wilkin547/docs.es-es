---
title: Procedimiento para agregar paneles a un control StatusBar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- panels [Windows Forms], status bars
- status bars [Windows Forms], adding panels
- StatusBar control [Windows Forms], adding panels
ms.assetid: 835e3902-288c-4c38-9d69-0696d8695009
ms.openlocfilehash: 27d65c07f0a6ec4a25d057e2c16a8b59933bb8fd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925105"
---
# <a name="how-to-add-panels-to-a-statusbar-control"></a><span data-ttu-id="1fcc2-102">Procedimiento para agregar paneles a un control StatusBar</span><span class="sxs-lookup"><span data-stu-id="1fcc2-102">How to: Add Panels to a StatusBar Control</span></span>
> [!IMPORTANT]
> <span data-ttu-id="1fcc2-103">Los <xref:System.Windows.Forms.StatusStrip> controles <xref:System.Windows.Forms.ToolStripStatusLabel> y reemplazan y agregan funcionalidad <xref:System.Windows.Forms.StatusBar> a <xref:System.Windows.Forms.StatusBarPanel> los controles y; sin <xref:System.Windows.Forms.StatusBar> embargo <xref:System.Windows.Forms.StatusBarPanel> , los controles y se conservan por compatibilidad con versiones anteriores y uso futuro, si Elija.</span><span class="sxs-lookup"><span data-stu-id="1fcc2-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="1fcc2-104">El área programable dentro de un control de [control StatusBar](statusbar-control-windows-forms.md) se compone de <xref:System.Windows.Forms.StatusBarPanel> instancias de la clase.</span><span class="sxs-lookup"><span data-stu-id="1fcc2-104">The programmable area within a [StatusBar Control](statusbar-control-windows-forms.md) control consists of instances of the <xref:System.Windows.Forms.StatusBarPanel> class.</span></span> <span data-ttu-id="1fcc2-105">Estos se agregan a través de adiciones a la <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> clase.</span><span class="sxs-lookup"><span data-stu-id="1fcc2-105">These are added through additions to the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> class.</span></span>  
  
### <a name="to-add-panels-to-a-status-bar"></a><span data-ttu-id="1fcc2-106">Para agregar paneles a una barra de estado</span><span class="sxs-lookup"><span data-stu-id="1fcc2-106">To add panels to a status bar</span></span>  
  
1. <span data-ttu-id="1fcc2-107">En un procedimiento, cree paneles de barra de estado agregándolos a <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span><span class="sxs-lookup"><span data-stu-id="1fcc2-107">In a procedure, create status-bar panels by adding them to the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span> <span data-ttu-id="1fcc2-108">Especifique la configuración de las propiedades de los paneles individuales mediante su índice <xref:System.Windows.Forms.StatusBar.Panels%2A> pasado a través de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1fcc2-108">Specify property settings for individual panels by using its index passed through the <xref:System.Windows.Forms.StatusBar.Panels%2A> property.</span></span>  
  
     <span data-ttu-id="1fcc2-109">En el ejemplo de código siguiente, la ruta de acceso establecida para la ubicación del icono es la carpeta **Mis documentos** .</span><span class="sxs-lookup"><span data-stu-id="1fcc2-109">In the following code example, the path set for the location of the icon is the **My Documents** folder.</span></span> <span data-ttu-id="1fcc2-110">Esta ubicación se usa porque puede suponer que la mayoría de los equipos que ejecutan el sistema operativo Windows incluirán esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="1fcc2-110">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="1fcc2-111">La elección de esta ubicación también permite a los usuarios con niveles de acceso mínimos del sistema ejecutar la aplicación de forma segura.</span><span class="sxs-lookup"><span data-stu-id="1fcc2-111">Choosing this location also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="1fcc2-112">En el ejemplo siguiente se requiere un formulario <xref:System.Windows.Forms.StatusBar> con un control ya agregado.</span><span class="sxs-lookup"><span data-stu-id="1fcc2-112">The following example requires a form with a <xref:System.Windows.Forms.StatusBar> control already added.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1fcc2-113">Es <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> una colección basada en cero, por lo que el código debe continuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="1fcc2-113">The <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> is a zero-based collection, so code should proceed accordingly.</span></span>  
  
    ```vb  
    Public Sub CreateStatusBarPanels()  
    ' Create panels and set text property.  
       StatusBar1.Panels.Add("One")  
       StatusBar1.Panels.Add("Two")  
       StatusBar1.Panels.Add("Three")  
    ' Set properties of StatusBar panels.  
    ' Set AutoSize property of panels.  
       StatusBar1.Panels(0).AutoSize = StatusBarPanelAutoSize.Spring  
       StatusBar1.Panels(1).AutoSize = StatusBarPanelAutoSize.Contents  
       StatusBar1.Panels(2).AutoSize = StatusBarPanelAutoSize.Contents  
    ' Set BorderStyle property of panels.  
       StatusBar1.Panels(0).BorderStyle = StatusBarPanelBorderStyle.Raised  
       StatusBar1.Panels(1).BorderStyle = StatusBarPanelBorderStyle.Sunken  
       StatusBar1.Panels(2).BorderStyle = StatusBarPanelBorderStyle.Raised  
    ' Set Icon property of third panel. You should replace the bolded  
    ' icon in the sample below with an icon of your own choosing.  
       StatusBar1.Panels(2).Icon = New _   
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
       StatusBar1.ShowPanels = True  
    End Sub  
    ```  
  
    ```csharp  
    public void CreateStatusBarPanels()  
    {  
       // Create panels and set text property.  
       statusBar1.Panels.Add("One");  
       statusBar1.Panels.Add("Two");  
       statusBar1.Panels.Add("Three");  
       // Set properties of StatusBar panels.  
       // Set AutoSize property of panels.  
       statusBar1.Panels[0].AutoSize = StatusBarPanelAutoSize.Spring;  
       statusBar1.Panels[1].AutoSize = StatusBarPanelAutoSize.Contents;  
       statusBar1.Panels[2].AutoSize = StatusBarPanelAutoSize.Contents;  
       // Set BorderStyle property of panels.  
       statusBar1.Panels[0].BorderStyle =  
          StatusBarPanelBorderStyle.Raised;  
       statusBar1.Panels[1].BorderStyle = StatusBarPanelBorderStyle.Sunken;  
       statusBar1.Panels[2].BorderStyle = StatusBarPanelBorderStyle.Raised;  
       // Set Icon property of third panel. You should replace the bolded  
       // icon in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       statusBar1.Panels[2].Icon =   
          new System.Drawing.Icon (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Icon.ico");  
       statusBar1.ShowPanels = true;  
    }  
    ```  
  
    ```cpp  
    public:  
       void CreateStatusBarPanels()  
       {  
          // Create panels and set text property.  
          statusBar1->Panels->Add("One");  
          statusBar1->Panels->Add("Two");  
          statusBar1->Panels->Add("Three");  
          // Set properties of StatusBar panels.  
          // Set AutoSize property of panels.  
          statusBar1->Panels[0]->AutoSize =  
             StatusBarPanelAutoSize::Spring;  
          statusBar1->Panels[1]->AutoSize =  
             StatusBarPanelAutoSize::Contents;  
          statusBar1->Panels[2]->AutoSize =  
             StatusBarPanelAutoSize::Contents;  
          // Set BorderStyle property of panels.  
          statusBar1->Panels[0]->BorderStyle =  
             StatusBarPanelBorderStyle::Raised;  
          statusBar1->Panels[1]->BorderStyle =  
             StatusBarPanelBorderStyle::Sunken;  
          statusBar1->Panels[2]->BorderStyle =  
             StatusBarPanelBorderStyle::Raised;  
          // Set Icon property of third panel.  
          // You should replace the bolded image   
          // in the sample below with an icon of your own choosing.  
          statusBar1->Panels[2]->Icon =  
             gcnew System::Drawing::Icon(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Icon.ico"));  
          statusBar1->ShowPanels = true;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1fcc2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1fcc2-114">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- <span data-ttu-id="1fcc2-115">[Cuadro de diálogo Editor de colecciones](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/xc4yyekt(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1fcc2-115">[Collection Editor Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/xc4yyekt(v=vs.100))</span></span>
- [<span data-ttu-id="1fcc2-116">Cómo: Establecer el tamaño de los paneles de la barra de estado</span><span class="sxs-lookup"><span data-stu-id="1fcc2-116">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)
- [<span data-ttu-id="1fcc2-117">Tutorial: Actualizar la información de la barra de estado en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="1fcc2-117">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)
- [<span data-ttu-id="1fcc2-118">Cómo: Determinar en qué panel del control Windows Forms StatusBar se hizo clic</span><span class="sxs-lookup"><span data-stu-id="1fcc2-118">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [<span data-ttu-id="1fcc2-119">Información general sobre StatusBar (Control)</span><span class="sxs-lookup"><span data-stu-id="1fcc2-119">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
