---
title: Asocie un menú contextual con el componente NotifyIcon
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], for background processes
- NotifyIcon component [Windows Forms], associating shortcut menus
- shortcut menus [Windows Forms], for background processes
ms.assetid: d68f3926-08d3-4f7d-949f-1981b29cf188
ms.openlocfilehash: 15a4a06726de348745e5eef03217d693db496a42
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182265"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a><span data-ttu-id="d082c-102">Cómo: Asociar un menú contextual con un componente NotifyIcon de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d082c-102">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>
> [!NOTE]
> <span data-ttu-id="d082c-103">Aunque <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> y reemplazar y agregar <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> funcionalidad a los <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> controles y los controles de versiones anteriores, y se conservan tanto para la compatibilidad con versiones anteriores como para el uso futuro si lo desea.</span><span class="sxs-lookup"><span data-stu-id="d082c-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="d082c-104">El <xref:System.Windows.Forms.NotifyIcon> componente muestra un icono en el área de notificación de estado de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="d082c-104">The <xref:System.Windows.Forms.NotifyIcon> component displays an icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="d082c-105">Normalmente, las aplicaciones le permiten hacer clic con el botón derecho en este icono para enviar comandos a la aplicación que representa.</span><span class="sxs-lookup"><span data-stu-id="d082c-105">Commonly, applications enable you to right-click this icon to send commands to the application it represents.</span></span> <span data-ttu-id="d082c-106">Al asociar <xref:System.Windows.Forms.ContextMenu> un componente <xref:System.Windows.Forms.NotifyIcon> con el componente, puede agregar esta funcionalidad a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d082c-106">By associating a <xref:System.Windows.Forms.ContextMenu> component with the <xref:System.Windows.Forms.NotifyIcon> component, you can add this functionality to your applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d082c-107">Si desea que la aplicación se minimice al <xref:System.Windows.Forms.NotifyIcon> inicio mientras se muestra una instancia <xref:System.Windows.Forms.Form.WindowState%2A> del <xref:System.Windows.Forms.FormWindowState.Minimized> componente en <xref:System.Windows.Forms.NotifyIcon> la <xref:System.Windows.Forms.NotifyIcon.Visible%2A> barra de `true`tareas, establezca la propiedad del formulario principal en y asegúrese de que la propiedad del componente está establecida en .</span><span class="sxs-lookup"><span data-stu-id="d082c-107">If you want your application to be minimized at startup while displaying an instance of the <xref:System.Windows.Forms.NotifyIcon> component in the taskbar, set the main form's <xref:System.Windows.Forms.Form.WindowState%2A> property to <xref:System.Windows.Forms.FormWindowState.Minimized> and be sure the <xref:System.Windows.Forms.NotifyIcon> component's <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property is set to `true`.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a><span data-ttu-id="d082c-108">Para asociar un menú contextual con el componente NotifyIcon en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="d082c-108">To associate a shortcut menu with the NotifyIcon component at design time</span></span>  
  
1. <span data-ttu-id="d082c-109">Agregue <xref:System.Windows.Forms.NotifyIcon> un componente al formulario y establezca las <xref:System.Windows.Forms.NotifyIcon.Icon%2A> propiedades <xref:System.Windows.Forms.NotifyIcon.Visible%2A> importantes, como las propiedades y.</span><span class="sxs-lookup"><span data-stu-id="d082c-109">Add a <xref:System.Windows.Forms.NotifyIcon> component to your form, and set the important properties, such as the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties.</span></span>  
  
     <span data-ttu-id="d082c-110">Para obtener más información, vea Cómo: Agregar iconos de aplicación a la barra de [tareas con el componente NotifyIcon](app-icons-to-the-taskbar-with-wf-notifyicon.md)de formularios Windows Forms .</span><span class="sxs-lookup"><span data-stu-id="d082c-110">For more information, see [How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
2. <span data-ttu-id="d082c-111">Agregue <xref:System.Windows.Forms.ContextMenu> un componente a su formulario Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d082c-111">Add a <xref:System.Windows.Forms.ContextMenu> component to your Windows Form.</span></span>  
  
     <span data-ttu-id="d082c-112">Agregue elementos de menú al menú contextual que representan los comandos que desea que estén disponibles en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d082c-112">Add menu items to the shortcut menu representing the commands you want to make available at run time.</span></span> <span data-ttu-id="d082c-113">También es un buen momento para agregar mejoras de menú a estos elementos de menú, como las teclas de acceso.</span><span class="sxs-lookup"><span data-stu-id="d082c-113">This is also a good time to add menu enhancements to these menu items, such as access keys.</span></span>  
  
3. <span data-ttu-id="d082c-114">Establezca <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> la propiedad <xref:System.Windows.Forms.NotifyIcon> del componente en el menú contextual que agregó.</span><span class="sxs-lookup"><span data-stu-id="d082c-114">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="d082c-115">Con este conjunto de propiedades, el menú contextual se mostrará cuando se haga clic en el icono de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="d082c-115">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a><span data-ttu-id="d082c-116">Para asociar un menú contextual con el componente NotifyIcon mediante programación</span><span class="sxs-lookup"><span data-stu-id="d082c-116">To associate a shortcut menu with the NotifyIcon component programmatically</span></span>  
  
1. <span data-ttu-id="d082c-117">Cree una instancia <xref:System.Windows.Forms.NotifyIcon> de <xref:System.Windows.Forms.ContextMenu> la clase y una clase, con<xref:System.Windows.Forms.NotifyIcon.Icon%2A> <xref:System.Windows.Forms.NotifyIcon.Visible%2A> cualquier configuración <xref:System.Windows.Forms.NotifyIcon> de propiedad que <xref:System.Windows.Forms.ContextMenu> sea necesaria para la aplicación (y las propiedades para el componente, elementos de menú para el componente).</span><span class="sxs-lookup"><span data-stu-id="d082c-117">Create an instance of the <xref:System.Windows.Forms.NotifyIcon> class and a <xref:System.Windows.Forms.ContextMenu> class, with whatever property settings are necessary for the application (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties for the <xref:System.Windows.Forms.NotifyIcon> component, menu items for the <xref:System.Windows.Forms.ContextMenu> component).</span></span>  
  
2. <span data-ttu-id="d082c-118">Establezca <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> la propiedad <xref:System.Windows.Forms.NotifyIcon> del componente en el menú contextual que agregó.</span><span class="sxs-lookup"><span data-stu-id="d082c-118">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="d082c-119">Con este conjunto de propiedades, el menú contextual se mostrará cuando se haga clic en el icono de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="d082c-119">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d082c-120">En el ejemplo de código siguiente se crea una estructura de menú básica.</span><span class="sxs-lookup"><span data-stu-id="d082c-120">The following code example creates a basic menu structure.</span></span> <span data-ttu-id="d082c-121">Tendrá que personalizar las opciones de menú a las que se ajusten a la aplicación que está desarrollando.</span><span class="sxs-lookup"><span data-stu-id="d082c-121">You will need to customize the menu choices to those that fit the application you are developing.</span></span> <span data-ttu-id="d082c-122">Además, querrá escribir código para <xref:System.Windows.Forms.MenuItem.Click> controlar los eventos de estos elementos de menú.</span><span class="sxs-lookup"><span data-stu-id="d082c-122">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.MenuItem.Click> events for these menu items.</span></span>  
  
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
> <span data-ttu-id="d082c-123">Debe inicializar `notifyIcon1` `contextMenu1,` y lo que puede hacer incluyendo las siguientes instrucciones en el constructor del formulario:</span><span class="sxs-lookup"><span data-stu-id="d082c-123">You must initialize `notifyIcon1` and `contextMenu1,` which you can do by including the following statements in the constructor of your form:</span></span>  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a><span data-ttu-id="d082c-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d082c-124">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="d082c-125">Cómo: Agregar iconos de aplicación a la barra de tareas con el componente NotifyIcon de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d082c-125">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [<span data-ttu-id="d082c-126">Componente NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="d082c-126">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
- [<span data-ttu-id="d082c-127">Información general sobre el componente NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="d082c-127">NotifyIcon Component Overview</span></span>](notifyicon-component-overview-windows-forms.md)
