---
title: Procedimiento para definir un icono para un botón de la barra de herramientas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- buttons [Windows Forms], icons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: 84db98b4-8566-49ce-b2c8-1fd66a5eb3a0
ms.openlocfilehash: 2b85f734a5f8b31531cfe48f87681d98304db09b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929627"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button"></a><span data-ttu-id="b6265-102">Procedimiento para definir un icono para un botón de la barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="b6265-102">How to: Define an Icon for a ToolBar Button</span></span>
> [!NOTE]
> <span data-ttu-id="b6265-103">El control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>; sin embargo, el control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="b6265-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="b6265-104"><xref:System.Windows.Forms.ToolBar>los botones pueden mostrar iconos dentro de ellos para facilitar su identificación por parte de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b6265-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="b6265-105">Esto se consigue mediante la adición de imágenes al componente [ImageList](imagelist-component-windows-forms.md) y, a continuación, la Asociación <xref:System.Windows.Forms.ImageList> del componente <xref:System.Windows.Forms.ToolBar> al control.</span><span class="sxs-lookup"><span data-stu-id="b6265-105">This is achieved through adding images to the [ImageList Component](imagelist-component-windows-forms.md) component and then associating the <xref:System.Windows.Forms.ImageList> component with the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
### <a name="to-set-an-icon-for-a-toolbar-button-programmatically"></a><span data-ttu-id="b6265-106">Para establecer un icono para un botón de la barra de herramientas mediante programación</span><span class="sxs-lookup"><span data-stu-id="b6265-106">To set an icon for a toolbar button programmatically</span></span>  
  
1. <span data-ttu-id="b6265-107">En un procedimiento, cree una instancia <xref:System.Windows.Forms.ImageList> de un componente <xref:System.Windows.Forms.ToolBar> y un control.</span><span class="sxs-lookup"><span data-stu-id="b6265-107">In a procedure, instantiate an <xref:System.Windows.Forms.ImageList> component and a <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
2. <span data-ttu-id="b6265-108">En el mismo procedimiento, asigne una imagen al <xref:System.Windows.Forms.ImageList> componente.</span><span class="sxs-lookup"><span data-stu-id="b6265-108">In the same procedure, assign an image to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
3. <span data-ttu-id="b6265-109">En el mismo procedimiento, asigne el <xref:System.Windows.Forms.ImageList> control <xref:System.Windows.Forms.ToolBar> al control y asigne la <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> propiedad de los botones de la barra de herramientas individuales.</span><span class="sxs-lookup"><span data-stu-id="b6265-109">In the same procedure, assign the <xref:System.Windows.Forms.ImageList> control to the <xref:System.Windows.Forms.ToolBar> control and assign the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of the individual toolbar buttons.</span></span>  
  
     <span data-ttu-id="b6265-110">En el ejemplo de código siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta **Mis documentos** .</span><span class="sxs-lookup"><span data-stu-id="b6265-110">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="b6265-111">Esto se hace porque puede suponer que la mayoría de los equipos que ejecutan el sistema operativo Windows incluirán este directorio.</span><span class="sxs-lookup"><span data-stu-id="b6265-111">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="b6265-112">Esto permite también a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura.</span><span class="sxs-lookup"><span data-stu-id="b6265-112">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="b6265-113">En el ejemplo siguiente se supone que ya <xref:System.Windows.Forms.PictureBox> se ha agregado un formulario con un control.</span><span class="sxs-lookup"><span data-stu-id="b6265-113">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
     <span data-ttu-id="b6265-114">Siguiendo los pasos anteriores, debe haber escrito código similar al que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="b6265-114">Following the steps above, you should have written code similar to that displayed below.</span></span>  
  
    ```vb  
    Public Sub InitializeMyToolBar()  
    ' Instantiate an ImageList component and a ToolBar control.  
       Dim ToolBar1 as New ToolBar  
       Dim ImageList1 as New ImageList  
    ' Assign an image to the ImageList component.  
    ' You should replace the bold image  
    ' in the sample below with an icon of your own choosing.  
       Dim myImage As System.Drawing.Image = _   
          Image.FromFile Image.FromFile _  
          (System.Environment.GetFolderPath _  
          (System.Environment.SpecialFolder.Personal) _  
          & "\Image.gif")  
       ImageList1.Images.Add(myImage)  
    ' Create a ToolBarButton.  
       Dim ToolBarButton1 As New ToolBarButton()  
    ' Add the ToolBarButton to the ToolBar.  
       ToolBar1.Buttons.Add(toolBarButton1)  
    ' Assign an ImageList to the ToolBar.  
       ToolBar1.ImageList = ImageList1  
    ' Assign the ImageIndex property of the ToolBarButton.  
       ToolBarButton1.ImageIndex = 0  
    End Sub  
    ```  
  
    ```csharp  
    public void InitializeMyToolBar()  
    {  
       // Instantiate an ImageList component and a ToolBar control.  
       ToolBar toolBar1 = new  ToolBar();   
       ImageList imageList1 = new ImageList();  
       // Assign an image to the ImageList component.  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       Image myImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
       imageList1.Images.Add(myImage);  
       // Create a ToolBarButton.  
       ToolBarButton toolBarButton1 = new ToolBarButton();  
       // Add the ToolBarButton to the ToolBar.  
       toolBar1.Buttons.Add(toolBarButton1);  
       // Assign an ImageList to the ToolBar.  
       toolBar1.ImageList = imageList1;  
       // Assign ImageIndex property of the ToolBarButton.  
       toolBarButton1.ImageIndex = 0;  
    }  
    ```  
  
    ```cpp  
    public:  
       void InitializeMyToolBar()  
       {  
          // Instantiate an ImageList component and a ToolBar control.  
          ToolBar ^ toolBar1 = gcnew  ToolBar();   
          ImageList ^ imageList1 = gcnew ImageList();  
          // Assign an image to the ImageList component.  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          Image ^ myImage = Image::FromFile(String::Concat  
             (System::Environment::GetFolderPath  
             (System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
          imageList1->Images->Add(myImage);  
          // Create a ToolBarButton.  
          ToolBarButton ^ toolBarButton1 = gcnew ToolBarButton();  
          // Add the ToolBarButton to the ToolBar.  
          toolBar1->Buttons->Add(toolBarButton1);  
          // Assign an ImageList to the ToolBar.  
          toolBar1->ImageList = imageList1;  
          // Assign ImageIndex property of the ToolBarButton.  
          toolBarButton1->ImageIndex = 0;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b6265-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6265-115">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="b6265-116">Cómo: Desencadenar eventos de menú para botones de barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="b6265-116">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="b6265-117">ToolBar (control)</span><span class="sxs-lookup"><span data-stu-id="b6265-117">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="b6265-118">ImageList (componente)</span><span class="sxs-lookup"><span data-stu-id="b6265-118">ImageList Component</span></span>](imagelist-component-windows-forms.md)
