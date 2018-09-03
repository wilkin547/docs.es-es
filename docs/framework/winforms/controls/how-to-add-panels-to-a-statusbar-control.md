---
title: 'Cómo: Agregar paneles a un control StatusBar'
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
ms.openlocfilehash: dd006f669ab6f0186bbcc7d1c76f9852ab6e8f60
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43476042"
---
# <a name="how-to-add-panels-to-a-statusbar-control"></a><span data-ttu-id="08f6a-102">Cómo: Agregar paneles a un control StatusBar</span><span class="sxs-lookup"><span data-stu-id="08f6a-102">How to: Add Panels to a StatusBar Control</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="08f6a-103">El <xref:System.Windows.Forms.StatusStrip> y <xref:System.Windows.Forms.ToolStripStatusLabel> controles reemplazan y agregan funcionalidad a la <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel> controla; sin embargo, el <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel> controles se conservan por compatibilidad con versiones anteriores y uso futuro, si se Elija esta opción.</span><span class="sxs-lookup"><span data-stu-id="08f6a-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="08f6a-104">El área programable dentro de un [StatusBar Control](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) control consta de las instancias de la <xref:System.Windows.Forms.StatusBarPanel> clase.</span><span class="sxs-lookup"><span data-stu-id="08f6a-104">The programmable area within a [StatusBar Control](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) control consists of instances of the <xref:System.Windows.Forms.StatusBarPanel> class.</span></span> <span data-ttu-id="08f6a-105">Se agregan a través de las adiciones a la <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> clase.</span><span class="sxs-lookup"><span data-stu-id="08f6a-105">These are added through additions to the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> class.</span></span>  
  
### <a name="to-add-panels-to-a-status-bar"></a><span data-ttu-id="08f6a-106">Para agregar paneles a una barra de estado</span><span class="sxs-lookup"><span data-stu-id="08f6a-106">To add panels to a status bar</span></span>  
  
1.  <span data-ttu-id="08f6a-107">En un procedimiento, cree paneles de barra de estado agregándolos a la <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span><span class="sxs-lookup"><span data-stu-id="08f6a-107">In a procedure, create status-bar panels by adding them to the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span> <span data-ttu-id="08f6a-108">Especifique los valores de propiedad para paneles individuales utilizando su índice se pasan a través de la <xref:System.Windows.Forms.StatusBar.Panels%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="08f6a-108">Specify property settings for individual panels by using its index passed through the <xref:System.Windows.Forms.StatusBar.Panels%2A> property.</span></span>  
  
     <span data-ttu-id="08f6a-109">En el ejemplo de código siguiente establece la ruta de acceso para la ubicación del icono es el **Mis documentos** carpeta.</span><span class="sxs-lookup"><span data-stu-id="08f6a-109">In the following code example, the path set for the location of the icon is the **My Documents** folder.</span></span> <span data-ttu-id="08f6a-110">Se utiliza esta ubicación porque se puede suponer que la mayoría de los equipos que ejecutan el sistema operativo de Windows incluirá esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="08f6a-110">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="08f6a-111">Al elegir esta ubicación también permite a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura.</span><span class="sxs-lookup"><span data-stu-id="08f6a-111">Choosing this location also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="08f6a-112">El ejemplo siguiente requiere un formulario con un <xref:System.Windows.Forms.StatusBar> control ya se ha agregado.</span><span class="sxs-lookup"><span data-stu-id="08f6a-112">The following example requires a form with a <xref:System.Windows.Forms.StatusBar> control already added.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="08f6a-113">El <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> es una colección basada en cero, por lo que el código debería proceder en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="08f6a-113">The <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> is a zero-based collection, so code should proceed accordingly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="08f6a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="08f6a-114">See Also</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [<span data-ttu-id="08f6a-115">Cuadro de diálogo Editor de colección</span><span class="sxs-lookup"><span data-stu-id="08f6a-115">Collection Editor Dialog Box</span></span>](https://msdn.microsoft.com/library/53fb3aad-bffa-4da5-ac89-8438e6fc803c)  
 [<span data-ttu-id="08f6a-116">Establecer el tamaño de los paneles de la barra de estado</span><span class="sxs-lookup"><span data-stu-id="08f6a-116">How to: Set the Size of Status-Bar Panels</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)  
 [<span data-ttu-id="08f6a-117">Tutorial: Actualizar la información de la barra de estado en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="08f6a-117">Walkthrough: Updating Status Bar Information at Run Time</span></span>](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)  
 [<span data-ttu-id="08f6a-118">Determinar en qué panel del control StatusBar de Windows Forms se hizo clic</span><span class="sxs-lookup"><span data-stu-id="08f6a-118">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 [<span data-ttu-id="08f6a-119">Información general sobre StatusBar (Control)</span><span class="sxs-lookup"><span data-stu-id="08f6a-119">StatusBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
