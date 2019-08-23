---
title: Procedimiento para agregar botones a un control de la barra de herramientas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: 78a58a8d-1041-4e38-9219-4096fa6a5c5c
ms.openlocfilehash: 8ab1fa8fc163ed50e51801769d40e61483e8ed5b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912629"
---
# <a name="how-to-add-buttons-to-a-toolbar-control"></a><span data-ttu-id="fb6c1-102">Procedimiento para agregar botones a un control de la barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="fb6c1-102">How to: Add Buttons to a ToolBar Control</span></span>
> [!NOTE]
> <span data-ttu-id="fb6c1-103">El control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>; sin embargo, el control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="fb6c1-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="fb6c1-104">Una parte integral del <xref:System.Windows.Forms.ToolBar> control son los botones que se agregan a él.</span><span class="sxs-lookup"><span data-stu-id="fb6c1-104">An integral part of the <xref:System.Windows.Forms.ToolBar> control is the buttons you add to it.</span></span> <span data-ttu-id="fb6c1-105">Se pueden usar para facilitar el acceso a los comandos de menú o, como alternativa, se pueden colocar en otra área de la interfaz de usuario de la aplicación para exponer comandos a los usuarios que no están disponibles en la estructura de menús.</span><span class="sxs-lookup"><span data-stu-id="fb6c1-105">These can be used to provide easy access to menu commands or, alternately, they can be placed in another area of the user interface of your application to expose commands to your users that are not available in the menu structure.</span></span>  
  
 <span data-ttu-id="fb6c1-106">En los ejemplos siguientes se supone <xref:System.Windows.Forms.ToolBar> que se ha agregado un control a un formulario`Form1`de Windows Forms ().</span><span class="sxs-lookup"><span data-stu-id="fb6c1-106">The examples below assume that a <xref:System.Windows.Forms.ToolBar> control has been added to a Windows Form (`Form1`).</span></span>  
  
### <a name="to-add-buttons-programmatically"></a><span data-ttu-id="fb6c1-107">Para agregar botones mediante programación</span><span class="sxs-lookup"><span data-stu-id="fb6c1-107">To add buttons programmatically</span></span>  
  
1. <span data-ttu-id="fb6c1-108">En un procedimiento, cree botones de barra de herramientas agregándolos a <xref:System.Windows.Forms.ToolBar.Buttons%2A?displayProperty=nameWithType> la colección.</span><span class="sxs-lookup"><span data-stu-id="fb6c1-108">In a procedure, create toolbar buttons by adding them to the <xref:System.Windows.Forms.ToolBar.Buttons%2A?displayProperty=nameWithType> collection.</span></span>  
  
2. <span data-ttu-id="fb6c1-109">Especifique la configuración de propiedades para un botón individual pasando el índice del botón a <xref:System.Windows.Forms.ToolBar.Buttons%2A> través de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="fb6c1-109">Specify property settings for an individual button by passing the button's index via the <xref:System.Windows.Forms.ToolBar.Buttons%2A> property.</span></span>  
  
     <span data-ttu-id="fb6c1-110">En el ejemplo siguiente se supone que ya <xref:System.Windows.Forms.ToolBar> se ha agregado un formulario con un control.</span><span class="sxs-lookup"><span data-stu-id="fb6c1-110">The example below assumes a form with a <xref:System.Windows.Forms.ToolBar> control already added.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="fb6c1-111">La <xref:System.Windows.Forms.ToolBar.Buttons%2A?displayProperty=nameWithType> colección es una colección basada en cero, por lo que el código debe continuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="fb6c1-111">The <xref:System.Windows.Forms.ToolBar.Buttons%2A?displayProperty=nameWithType> collection is a zero-based collection, so code should proceed accordingly.</span></span>  
  
    ```vb  
    Public Sub CreateToolBarButtons()  
    ' Create buttons and set text property.  
       ToolBar1.Buttons.Add("One")  
       ToolBar1.Buttons.Add("Two")  
       ToolBar1.Buttons.Add("Three")  
       ToolBar1.Buttons.Add("Four")  
    ' Set properties of StatusBar panels.  
    ' Set Style property.  
       ToolBar1.Buttons(0).Style = ToolBarButtonStyle.PushButton  
       ToolBar1.Buttons(1).Style = ToolBarButtonStyle.Separator  
       ToolBar1.Buttons(2).Style = ToolBarButtonStyle.ToggleButton  
       ToolBar1.Buttons(3).Style = ToolBarButtonStyle.DropDownButton  
    ' Set the ToggleButton's PartialPush property.  
       ToolBar1.Buttons(2).PartialPush = True  
    ' Instantiate a ContextMenu component and menu items.  
    ' Set the DropDownButton's DropDownMenu property to the context menu.  
       Dim cm As New ContextMenu()  
       Dim miOne As New MenuItem("One")  
       Dim miTwo As New MenuItem("Two")  
       Dim miThree As New MenuItem("Three")  
       cm.MenuItems.Add(miOne)  
       cm.MenuItems.Add(miTwo)  
       cm.MenuItems.Add(miThree)  
       ToolBar1.Buttons(3).DropDownMenu = cm  
    ' Set the PushButton's Pushed property.  
       ToolBar1.Buttons(0).Pushed = True  
    ' Set the ToolTipText property of one of the buttons.  
       ToolBar1.Buttons(1).ToolTipText = "Button 2"  
    End Sub  
    ```  
  
    ```csharp  
    public void CreateToolBarButtons()  
    {  
       // Create buttons and set text property.  
       toolBar1.Buttons.Add("One");  
       toolBar1.Buttons.Add("Two");  
       toolBar1.Buttons.Add("Three");  
       toolBar1.Buttons.Add("Four");  
  
       // Set properties of StatusBar panels.  
       // Set Style property.  
       toolBar1.Buttons[0].Style = ToolBarButtonStyle.PushButton;  
       toolBar1.Buttons[1].Style = ToolBarButtonStyle.Separator;  
       toolBar1.Buttons[2].Style = ToolBarButtonStyle.ToggleButton;  
       toolBar1.Buttons[3].Style = ToolBarButtonStyle.DropDownButton;  
  
       // Set the ToggleButton's PartialPush property.  
       toolBar1.Buttons[2].PartialPush = true;  
  
       // Instantiate a ContextMenu component and menu items.  
       // Set the DropDownButton's DropDownMenu property to   
       // the context menu.  
       ContextMenu cm = new ContextMenu();  
       MenuItem miOne = new MenuItem("One");  
       MenuItem miTwo = new MenuItem("Two");  
       MenuItem miThree = new MenuItem("Three");  
       cm.MenuItems.Add(miOne);  
       cm.MenuItems.Add(miTwo);  
       cm.MenuItems.Add(miThree);  
  
       toolBar1.Buttons[3].DropDownMenu = cm;  
       // Set the PushButton's Pushed property.  
       toolBar1.Buttons[0].Pushed = true;  
       // Set the ToolTipText property of 1 of the buttons.  
       toolBar1.Buttons[1].ToolTipText = "Button 2";  
    }  
    ```  
  
    ```cpp  
    public:  
       void CreateToolBarButtons()  
       {  
          // Create buttons and set text property.  
          toolBar1->Buttons->Add( "One" );  
          toolBar1->Buttons->Add( "Two" );  
          toolBar1->Buttons->Add( "Three" );  
          toolBar1->Buttons->Add( "Four" );  
  
          // Set properties of StatusBar panels.  
          // Set Style property.  
          toolBar1->Buttons[0]->Style = ToolBarButtonStyle::PushButton;  
          toolBar1->Buttons[1]->Style = ToolBarButtonStyle::Separator;  
          toolBar1->Buttons[2]->Style = ToolBarButtonStyle::ToggleButton;  
          toolBar1->Buttons[3]->Style = ToolBarButtonStyle::DropDownButton;  
  
          // Set the ToggleButton's PartialPush property.  
          toolBar1->Buttons[2]->PartialPush = true;  
  
          // Instantiate a ContextMenu component and menu items.  
          // Set the DropDownButton's DropDownMenu property to   
          // the context menu.  
          System::Windows::Forms::ContextMenu^ cm = gcnew System::Windows::Forms::ContextMenu;  
          MenuItem^ miOne = gcnew MenuItem( "One" );  
          MenuItem^ miTwo = gcnew MenuItem( "Two" );  
          MenuItem^ miThree = gcnew MenuItem( "Three" );  
          cm->MenuItems->Add( miOne );  
          cm->MenuItems->Add( miTwo );  
          cm->MenuItems->Add( miThree );  
          toolBar1->Buttons[3]->DropDownMenu = cm;  
  
          // Set the PushButton's Pushed property.  
          toolBar1->Buttons[0]->Pushed = true;  
  
          // Set the ToolTipText property of 1 of the buttons.  
          toolBar1->Buttons[1]->ToolTipText = "Button 2";  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fb6c1-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb6c1-112">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="fb6c1-113">Procedimientos: Definir un icono para un botón de la barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="fb6c1-113">How to: Define an Icon for a ToolBar Button</span></span>](how-to-define-an-icon-for-a-toolbar-button.md)
- [<span data-ttu-id="fb6c1-114">Cómo: Desencadenar eventos de menú para botones de barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="fb6c1-114">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="fb6c1-115">Información general del control ToolBar</span><span class="sxs-lookup"><span data-stu-id="fb6c1-115">ToolBar Control Overview</span></span>](toolbar-control-overview-windows-forms.md)
- [<span data-ttu-id="fb6c1-116">ToolBar (control)</span><span class="sxs-lookup"><span data-stu-id="fb6c1-116">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
