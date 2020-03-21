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
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a>Cómo: Asociar un menú contextual con un componente NotifyIcon de formularios Windows Forms
> [!NOTE]
> Aunque <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> y reemplazar y agregar <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> funcionalidad a los <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> controles y los controles de versiones anteriores, y se conservan tanto para la compatibilidad con versiones anteriores como para el uso futuro si lo desea.  
  
 El <xref:System.Windows.Forms.NotifyIcon> componente muestra un icono en el área de notificación de estado de la barra de tareas. Normalmente, las aplicaciones le permiten hacer clic con el botón derecho en este icono para enviar comandos a la aplicación que representa. Al asociar <xref:System.Windows.Forms.ContextMenu> un componente <xref:System.Windows.Forms.NotifyIcon> con el componente, puede agregar esta funcionalidad a las aplicaciones.  
  
> [!NOTE]
> Si desea que la aplicación se minimice al <xref:System.Windows.Forms.NotifyIcon> inicio mientras se muestra una instancia <xref:System.Windows.Forms.Form.WindowState%2A> del <xref:System.Windows.Forms.FormWindowState.Minimized> componente en <xref:System.Windows.Forms.NotifyIcon> la <xref:System.Windows.Forms.NotifyIcon.Visible%2A> barra de `true`tareas, establezca la propiedad del formulario principal en y asegúrese de que la propiedad del componente está establecida en .  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a>Para asociar un menú contextual con el componente NotifyIcon en tiempo de diseño  
  
1. Agregue <xref:System.Windows.Forms.NotifyIcon> un componente al formulario y establezca las <xref:System.Windows.Forms.NotifyIcon.Icon%2A> propiedades <xref:System.Windows.Forms.NotifyIcon.Visible%2A> importantes, como las propiedades y.  
  
     Para obtener más información, vea Cómo: Agregar iconos de aplicación a la barra de [tareas con el componente NotifyIcon](app-icons-to-the-taskbar-with-wf-notifyicon.md)de formularios Windows Forms .  
  
2. Agregue <xref:System.Windows.Forms.ContextMenu> un componente a su formulario Windows Forms.  
  
     Agregue elementos de menú al menú contextual que representan los comandos que desea que estén disponibles en tiempo de ejecución. También es un buen momento para agregar mejoras de menú a estos elementos de menú, como las teclas de acceso.  
  
3. Establezca <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> la propiedad <xref:System.Windows.Forms.NotifyIcon> del componente en el menú contextual que agregó.  
  
     Con este conjunto de propiedades, el menú contextual se mostrará cuando se haga clic en el icono de la barra de tareas.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a>Para asociar un menú contextual con el componente NotifyIcon mediante programación  
  
1. Cree una instancia <xref:System.Windows.Forms.NotifyIcon> de <xref:System.Windows.Forms.ContextMenu> la clase y una clase, con<xref:System.Windows.Forms.NotifyIcon.Icon%2A> <xref:System.Windows.Forms.NotifyIcon.Visible%2A> cualquier configuración <xref:System.Windows.Forms.NotifyIcon> de propiedad que <xref:System.Windows.Forms.ContextMenu> sea necesaria para la aplicación (y las propiedades para el componente, elementos de menú para el componente).  
  
2. Establezca <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> la propiedad <xref:System.Windows.Forms.NotifyIcon> del componente en el menú contextual que agregó.  
  
     Con este conjunto de propiedades, el menú contextual se mostrará cuando se haga clic en el icono de la barra de tareas.  
  
    > [!NOTE]
    > En el ejemplo de código siguiente se crea una estructura de menú básica. Tendrá que personalizar las opciones de menú a las que se ajusten a la aplicación que está desarrollando. Además, querrá escribir código para <xref:System.Windows.Forms.MenuItem.Click> controlar los eventos de estos elementos de menú.  
  
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
> Debe inicializar `notifyIcon1` `contextMenu1,` y lo que puede hacer incluyendo las siguientes instrucciones en el constructor del formulario:  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [Cómo: Agregar iconos de aplicación a la barra de tareas con el componente NotifyIcon de formularios Windows Forms](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [Componente NotifyIcon](notifyicon-component-windows-forms.md)
- [Información general sobre el componente NotifyIcon](notifyicon-component-overview-windows-forms.md)
