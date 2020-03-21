---
title: 'Cómo: Definir un icono para un botón ToolBar'
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
ms.openlocfilehash: 84c67c7d2584390ba3e48cb83820c65c6bb45d1f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182207"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button"></a><span data-ttu-id="33821-102">Cómo: Definir un icono para un botón ToolBar</span><span class="sxs-lookup"><span data-stu-id="33821-102">How to: Define an Icon for a ToolBar Button</span></span>
> [!NOTE]
> <span data-ttu-id="33821-103">El control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>; sin embargo, el control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="33821-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="33821-104"><xref:System.Windows.Forms.ToolBar>botones son capaces de mostrar iconos dentro de ellos para facilitar la identificación por parte de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="33821-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="33821-105">Esto se logra mediante la adición de imágenes <xref:System.Windows.Forms.ImageList> al <xref:System.Windows.Forms.ToolBar> componente [ImageList componente](imagelist-component-windows-forms.md) y, a continuación, asociar el componente con el control.</span><span class="sxs-lookup"><span data-stu-id="33821-105">This is achieved through adding images to the [ImageList Component](imagelist-component-windows-forms.md) component and then associating the <xref:System.Windows.Forms.ImageList> component with the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
### <a name="to-set-an-icon-for-a-toolbar-button-programmatically"></a><span data-ttu-id="33821-106">Para establecer un icono para un botón de barra de herramientas mediante programación</span><span class="sxs-lookup"><span data-stu-id="33821-106">To set an icon for a toolbar button programmatically</span></span>  
  
1. <span data-ttu-id="33821-107">En un procedimiento, <xref:System.Windows.Forms.ImageList> cree <xref:System.Windows.Forms.ToolBar> una instancia de un componente y un control.</span><span class="sxs-lookup"><span data-stu-id="33821-107">In a procedure, instantiate an <xref:System.Windows.Forms.ImageList> component and a <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
2. <span data-ttu-id="33821-108">En el mismo procedimiento, asigne <xref:System.Windows.Forms.ImageList> una imagen al componente.</span><span class="sxs-lookup"><span data-stu-id="33821-108">In the same procedure, assign an image to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
3. <span data-ttu-id="33821-109">En el mismo procedimiento, asigne el <xref:System.Windows.Forms.ImageList> control al <xref:System.Windows.Forms.ToolBar> control y asigne la <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> propiedad de los botones de barra de herramientas individuales.</span><span class="sxs-lookup"><span data-stu-id="33821-109">In the same procedure, assign the <xref:System.Windows.Forms.ImageList> control to the <xref:System.Windows.Forms.ToolBar> control and assign the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of the individual toolbar buttons.</span></span>  
  
     <span data-ttu-id="33821-110">En el ejemplo de código siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta **Mis documentos.**</span><span class="sxs-lookup"><span data-stu-id="33821-110">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="33821-111">Esto se hace, porque puede suponer que la mayoría de los equipos que ejecutan el sistema operativo Windows incluirán este directorio.</span><span class="sxs-lookup"><span data-stu-id="33821-111">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="33821-112">Esto permite también a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura.</span><span class="sxs-lookup"><span data-stu-id="33821-112">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="33821-113">En el ejemplo siguiente se <xref:System.Windows.Forms.PictureBox> supone un formulario con un control ya agregado.</span><span class="sxs-lookup"><span data-stu-id="33821-113">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
     <span data-ttu-id="33821-114">Siguiendo los pasos anteriores, debería haber escrito código similar al que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="33821-114">Following the steps above, you should have written code similar to that displayed below.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="33821-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33821-115">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="33821-116">Cómo: Desencadenar eventos de menú para los botones de la barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="33821-116">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="33821-117">Barra de herramientas (Control)</span><span class="sxs-lookup"><span data-stu-id="33821-117">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="33821-118">Componente ImageList</span><span class="sxs-lookup"><span data-stu-id="33821-118">ImageList Component</span></span>](imagelist-component-windows-forms.md)
