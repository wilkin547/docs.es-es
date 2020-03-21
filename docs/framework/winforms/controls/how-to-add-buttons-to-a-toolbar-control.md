---
title: 'Cómo: Agregar botones a un control ToolBar'
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
ms.openlocfilehash: 1bb6de58010e70a4edafacafe3dc00b511fc63de
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182335"
---
# <a name="how-to-add-buttons-to-a-toolbar-control"></a><span data-ttu-id="88fba-102">Cómo: Agregar botones a un control ToolBar</span><span class="sxs-lookup"><span data-stu-id="88fba-102">How to: Add Buttons to a ToolBar Control</span></span>
> [!NOTE]
> <span data-ttu-id="88fba-103">El control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>; sin embargo, el control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="88fba-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="88fba-104">Una parte integral <xref:System.Windows.Forms.ToolBar> del control son los botones que se le agregan.</span><span class="sxs-lookup"><span data-stu-id="88fba-104">An integral part of the <xref:System.Windows.Forms.ToolBar> control is the buttons you add to it.</span></span> <span data-ttu-id="88fba-105">Se pueden usar para facilitar el acceso a los comandos de menú o, alternativamente, se pueden colocar en otra área de la interfaz de usuario de la aplicación para exponer comandos a los usuarios que no están disponibles en la estructura de menús.</span><span class="sxs-lookup"><span data-stu-id="88fba-105">These can be used to provide easy access to menu commands or, alternately, they can be placed in another area of the user interface of your application to expose commands to your users that are not available in the menu structure.</span></span>  
  
 <span data-ttu-id="88fba-106">En los ejemplos <xref:System.Windows.Forms.ToolBar> siguientes se supone que se`Form1`ha agregado un control a un formulario Windows Forms ( ).</span><span class="sxs-lookup"><span data-stu-id="88fba-106">The examples below assume that a <xref:System.Windows.Forms.ToolBar> control has been added to a Windows Form (`Form1`).</span></span>  
  
### <a name="to-add-buttons-programmatically"></a><span data-ttu-id="88fba-107">Para agregar botones mediante programación</span><span class="sxs-lookup"><span data-stu-id="88fba-107">To add buttons programmatically</span></span>  
  
1. <span data-ttu-id="88fba-108">En un procedimiento, cree botones <xref:System.Windows.Forms.ToolBar.Buttons%2A?displayProperty=nameWithType> de barra de herramientas agregándolos a la colección.</span><span class="sxs-lookup"><span data-stu-id="88fba-108">In a procedure, create toolbar buttons by adding them to the <xref:System.Windows.Forms.ToolBar.Buttons%2A?displayProperty=nameWithType> collection.</span></span>  
  
2. <span data-ttu-id="88fba-109">Especifique la configuración de propiedades de un botón <xref:System.Windows.Forms.ToolBar.Buttons%2A> individual pasando el índice del botón a través de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="88fba-109">Specify property settings for an individual button by passing the button's index via the <xref:System.Windows.Forms.ToolBar.Buttons%2A> property.</span></span>  
  
     <span data-ttu-id="88fba-110">En el ejemplo siguiente se <xref:System.Windows.Forms.ToolBar> supone un formulario con un control ya agregado.</span><span class="sxs-lookup"><span data-stu-id="88fba-110">The example below assumes a form with a <xref:System.Windows.Forms.ToolBar> control already added.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="88fba-111">La <xref:System.Windows.Forms.ToolBar.Buttons%2A?displayProperty=nameWithType> colección es una colección de base cero, por lo que el código debe continuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="88fba-111">The <xref:System.Windows.Forms.ToolBar.Buttons%2A?displayProperty=nameWithType> collection is a zero-based collection, so code should proceed accordingly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="88fba-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="88fba-112">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="88fba-113">Definir un icono para un botón ToolBar</span><span class="sxs-lookup"><span data-stu-id="88fba-113">How to: Define an Icon for a ToolBar Button</span></span>](how-to-define-an-icon-for-a-toolbar-button.md)
- [<span data-ttu-id="88fba-114">Cómo: Desencadenar eventos de menú para los botones de la barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="88fba-114">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="88fba-115">Información general del control ToolBar</span><span class="sxs-lookup"><span data-stu-id="88fba-115">ToolBar Control Overview</span></span>](toolbar-control-overview-windows-forms.md)
- [<span data-ttu-id="88fba-116">Barra de herramientas (Control)</span><span class="sxs-lookup"><span data-stu-id="88fba-116">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
