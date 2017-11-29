---
title: "Cómo: Asociar un menú contextual con un componente NotifyIcon de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], for background processes
- NotifyIcon component [Windows Forms], associating shortcut menus
- shortcut menus [Windows Forms], for background processes
ms.assetid: d68f3926-08d3-4f7d-949f-1981b29cf188
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 985aa58056f4c4ec8f3042c682291508f1434ee0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a><span data-ttu-id="2702b-102">Cómo: Asociar un menú contextual con un componente NotifyIcon de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2702b-102">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>
> [!NOTE]
>  <span data-ttu-id="2702b-103">Aunque <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> reemplazar y agregar funcionalidad a la <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> controles de versiones anteriores, <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> se conservan por compatibilidad con versiones anteriores y uso futuro, si elige.</span><span class="sxs-lookup"><span data-stu-id="2702b-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="2702b-104">El <xref:System.Windows.Forms.NotifyIcon> componente muestra un icono en el área de notificación de estado de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="2702b-104">The <xref:System.Windows.Forms.NotifyIcon> component displays an icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="2702b-105">Normalmente, las aplicaciones permiten haga clic en este icono para enviar comandos a la aplicación que representa.</span><span class="sxs-lookup"><span data-stu-id="2702b-105">Commonly, applications enable you to right-click this icon to send commands to the application it represents.</span></span> <span data-ttu-id="2702b-106">Asociando un <xref:System.Windows.Forms.ContextMenu> componente con el <xref:System.Windows.Forms.NotifyIcon> , componente, puede agregar esta funcionalidad a sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="2702b-106">By associating a <xref:System.Windows.Forms.ContextMenu> component with the <xref:System.Windows.Forms.NotifyIcon> component, you can add this functionality to your applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2702b-107">Si desea que la aplicación a reducirse durante el inicio al mostrar una instancia de la <xref:System.Windows.Forms.NotifyIcon> conjunto de componentes en la barra de tareas, el formulario principal <xref:System.Windows.Forms.Form.WindowState%2A> propiedad <xref:System.Windows.Forms.FormWindowState.Minimized> y asegúrese del <xref:System.Windows.Forms.NotifyIcon> del componente <xref:System.Windows.Forms.NotifyIcon.Visible%2A> propiedad se establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="2702b-107">If you want your application to be minimized at startup while displaying an instance of the <xref:System.Windows.Forms.NotifyIcon> component in the taskbar, set the main form's <xref:System.Windows.Forms.Form.WindowState%2A> property to <xref:System.Windows.Forms.FormWindowState.Minimized> and be sure the <xref:System.Windows.Forms.NotifyIcon> component's <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property is set to `true`.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a><span data-ttu-id="2702b-108">Para asociar un menú contextual con el componente NotifyIcon en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="2702b-108">To associate a shortcut menu with the NotifyIcon component at design time</span></span>  
  
1.  <span data-ttu-id="2702b-109">Agregar un <xref:System.Windows.Forms.NotifyIcon> componente al formulario y establezca las propiedades importantes, como la <xref:System.Windows.Forms.NotifyIcon.Icon%2A> y <xref:System.Windows.Forms.NotifyIcon.Visible%2A> propiedades.</span><span class="sxs-lookup"><span data-stu-id="2702b-109">Add a <xref:System.Windows.Forms.NotifyIcon> component to your form, and set the important properties, such as the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties.</span></span>  
  
     <span data-ttu-id="2702b-110">Para obtener más información, consulte [Cómo: agregar iconos de aplicación a la barra de tareas con el componente NotifyIcon de formularios Windows Forms](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span><span class="sxs-lookup"><span data-stu-id="2702b-110">For more information, see [How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
2.  <span data-ttu-id="2702b-111">Agregar un <xref:System.Windows.Forms.ContextMenu> componente al formulario Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2702b-111">Add a <xref:System.Windows.Forms.ContextMenu> component to your Windows Form.</span></span>  
  
     <span data-ttu-id="2702b-112">Agregar elementos de menú al menú contextual que representa los comandos que desea que estén disponibles en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2702b-112">Add menu items to the shortcut menu representing the commands you want to make available at run time.</span></span> <span data-ttu-id="2702b-113">También es un buen momento para agregar mejoras a estos elementos de menú, como teclas de acceso.</span><span class="sxs-lookup"><span data-stu-id="2702b-113">This is also a good time to add menu enhancements to these menu items, such as access keys.</span></span>  
  
3.  <span data-ttu-id="2702b-114">Establecer el <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> propiedad de la <xref:System.Windows.Forms.NotifyIcon> componente en el menú contextual que agregó.</span><span class="sxs-lookup"><span data-stu-id="2702b-114">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="2702b-115">Con este conjunto de propiedades, se mostrará el menú contextual cuando se hace clic en el icono de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="2702b-115">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a><span data-ttu-id="2702b-116">Para asociar un menú contextual con el componente NotifyIcon mediante programación</span><span class="sxs-lookup"><span data-stu-id="2702b-116">To associate a shortcut menu with the NotifyIcon component programmatically</span></span>  
  
1.  <span data-ttu-id="2702b-117">Cree una instancia de la <xref:System.Windows.Forms.NotifyIcon> clase y un <xref:System.Windows.Forms.ContextMenu> (clase), con los valores de las propiedades necesarios para la aplicación (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> y <xref:System.Windows.Forms.NotifyIcon.Visible%2A> propiedades para la <xref:System.Windows.Forms.NotifyIcon> componente, elementos de menú para el <xref:System.Windows.Forms.ContextMenu> componente).</span><span class="sxs-lookup"><span data-stu-id="2702b-117">Create an instance of the <xref:System.Windows.Forms.NotifyIcon> class and a <xref:System.Windows.Forms.ContextMenu> class, with whatever property settings are necessary for the application (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties for the <xref:System.Windows.Forms.NotifyIcon> component, menu items for the <xref:System.Windows.Forms.ContextMenu> component).</span></span>  
  
2.  <span data-ttu-id="2702b-118">Establecer el <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> propiedad de la <xref:System.Windows.Forms.NotifyIcon> componente en el menú contextual que agregó.</span><span class="sxs-lookup"><span data-stu-id="2702b-118">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="2702b-119">Con este conjunto de propiedades, se mostrará el menú contextual cuando se hace clic en el icono de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="2702b-119">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2702b-120">En el ejemplo de código siguiente se crea una estructura de menú básica.</span><span class="sxs-lookup"><span data-stu-id="2702b-120">The following code example creates a basic menu structure.</span></span> <span data-ttu-id="2702b-121">Debe personalizar las opciones de menú a los que se ajusten a la aplicación que está desarrollando.</span><span class="sxs-lookup"><span data-stu-id="2702b-121">You will need to customize the menu choices to those that fit the application you are developing.</span></span> <span data-ttu-id="2702b-122">Además, desea escribir código para controlar la <xref:System.Windows.Forms.MenuItem.Click> eventos para estos elementos de menú.</span><span class="sxs-lookup"><span data-stu-id="2702b-122">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.MenuItem.Click> events for these menu items.</span></span>  
  
    ```vb  
    Public ContextMenu1 As New ContextMenu  
    Public NotifyIcon1 As New NotifyIcon  
  
    Public Sub CreateIconMenuStructure()  
       ' Add menu items to shortcut menu.  
       ContextMenu1.MenuItems.Add("&Open Application")  
       ContextMenu1.MenuItems.Add("S&uspend Application")  
       ContextMenu1.MenuItems.Add("E&xit")  
  
       ' Set properties of NotifyIcon component.  
       NotifyIcon1.Icon = New System.Drawing.Icon _   
          (System.Environment.GetFolderPath _   
          (System.Environment.SpecialFolder.Personal)  _   
          & "\Icon.ico")  
       NotifyIcon1.Text = "Right-click me!"  
       NotifyIcon1.Visible = True  
       NotifyIcon1.ContextMenu = ContextMenu1  
    End Sub  
    ```  
  
```csharp  
public NotifyIcon notifyIcon1 = new NotifyIcon();  
public ContextMenu contextMenu1 = new ContextMenu();  
  
public void createIconMenuStructure()  
{  
   // Add menu items to shortcut menu.  
   contextMenu1.MenuItems.Add("&Open Application");  
   contextMenu1.MenuItems.Add("S&uspend Application");  
   contextMenu1.MenuItems.Add("E&xit");  
  
   // Set properties of NotifyIcon component.  
   notifyIcon1.Icon = new System.Drawing.Icon  
      (System.Environment.GetFolderPath  
      (System.Environment.SpecialFolder.Personal)  
      + @"\Icon.ico");  
   notifyIcon1.Visible = true;  
   notifyIcon1.Text = "Right-click me!";  
   notifyIcon1.Visible = true;  
   notifyIcon1.ContextMenu = contextMenu1;  
}  
```  
  
```cpp  
public:  
   System::Windows::Forms::NotifyIcon ^ notifyIcon1;  
   System::Windows::Forms::ContextMenu ^ contextMenu1;  
  
   void createIconMenuStructure()  
   {  
      // Add menu items to shortcut menu.  
      contextMenu1->MenuItems->Add("&Open Application");  
      contextMenu1->MenuItems->Add("S&uspend Application");  
      contextMenu1->MenuItems->Add("E&xit");  
  
      // Set properties of NotifyIcon component.  
      notifyIcon1->Icon = gcnew System::Drawing::Icon  
          (String::Concat(System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::Personal),  
          "\\Icon.ico"));  
      notifyIcon1->Text = "Right-click me!";  
      notifyIcon1->Visible = true;  
      notifyIcon1->ContextMenu = contextMenu1;  
   }  
```  
  
> [!NOTE]
>  <span data-ttu-id="2702b-123">Debe inicializar `notifyIcon1` y `contextMenu1,` lo que puede hacer mediante la inclusión de las siguientes instrucciones en el constructor del formulario:</span><span class="sxs-lookup"><span data-stu-id="2702b-123">You must initialize `notifyIcon1` and `contextMenu1,` which you can do by including the following statements in the constructor of your form:</span></span>  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a><span data-ttu-id="2702b-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="2702b-124">See Also</span></span>  
 <xref:System.Windows.Forms.NotifyIcon>  
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>  
 [<span data-ttu-id="2702b-125">Agregar iconos de aplicación a la barra de tareas con el componente NotifyIcon de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2702b-125">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md)  
 [<span data-ttu-id="2702b-126">NotifyIcon (componente)</span><span class="sxs-lookup"><span data-stu-id="2702b-126">NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)  
 [<span data-ttu-id="2702b-127">Información general sobre el componente NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="2702b-127">NotifyIcon Component Overview</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)
