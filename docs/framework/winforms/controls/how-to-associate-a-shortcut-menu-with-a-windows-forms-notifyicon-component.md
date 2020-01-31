---
title: Asociar un menú contextual con el componente NotifyIcon
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
ms.openlocfilehash: 392c04f73feaec201033ad76f9419a0e070bec70
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742047"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a>Cómo: Asociar un menú contextual con un componente NotifyIcon de formularios Windows Forms
> [!NOTE]
> Aunque <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> reemplazan y agregan funcionalidad a los controles <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> de versiones anteriores, <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> se conservan por compatibilidad con versiones anteriores y uso futuro, si así lo decide.  
  
 El componente <xref:System.Windows.Forms.NotifyIcon> muestra un icono en el área de notificación de estado de la barra de tareas. Normalmente, las aplicaciones permiten hacer clic con el botón secundario en este icono para enviar comandos a la aplicación que representa. Al asociar un componente <xref:System.Windows.Forms.ContextMenu> al componente <xref:System.Windows.Forms.NotifyIcon>, puede Agregar esta funcionalidad a sus aplicaciones.  
  
> [!NOTE]
> Si desea que la aplicación se minimice en el inicio mientras se muestra una instancia del componente <xref:System.Windows.Forms.NotifyIcon> en la barra de tareas, establezca la propiedad <xref:System.Windows.Forms.Form.WindowState%2A> del formulario principal en <xref:System.Windows.Forms.FormWindowState.Minimized> y asegúrese de que la propiedad <xref:System.Windows.Forms.NotifyIcon.Visible%2A> del componente <xref:System.Windows.Forms.NotifyIcon> esté establecida en `true`.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a>Para asociar un menú contextual con el componente NotifyIcon en tiempo de diseño  
  
1. Agregue un componente de <xref:System.Windows.Forms.NotifyIcon> al formulario y establezca las propiedades importantes, como las propiedades <xref:System.Windows.Forms.NotifyIcon.Icon%2A> y <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.  
  
     Para obtener más información, consulte [Cómo: agregar iconos de aplicación a la barra de tareas con el componente NotifyIcon Windows Forms](app-icons-to-the-taskbar-with-wf-notifyicon.md).  
  
2. Agregue un componente de <xref:System.Windows.Forms.ContextMenu> a su Windows Form.  
  
     Agregue elementos de menú al menú contextual que representa los comandos que desea que estén disponibles en tiempo de ejecución. También es un buen momento para agregar mejoras de menú a estos elementos de menú, como las teclas de acceso.  
  
3. Establezca la propiedad <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> del componente <xref:System.Windows.Forms.NotifyIcon> en el menú contextual que ha agregado.  
  
     Con esta propiedad establecida, el menú contextual se mostrará cuando se haga clic en el icono de la barra de tareas.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a>Para asociar un menú contextual con el componente NotifyIcon mediante programación  
  
1. Cree una instancia de la clase <xref:System.Windows.Forms.NotifyIcon> y una clase <xref:System.Windows.Forms.ContextMenu>, con los valores de propiedad necesarios para la aplicación (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> y <xref:System.Windows.Forms.NotifyIcon.Visible%2A> las propiedades para el componente <xref:System.Windows.Forms.NotifyIcon>, los elementos de menú del componente <xref:System.Windows.Forms.ContextMenu>).  
  
2. Establezca la propiedad <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> del componente <xref:System.Windows.Forms.NotifyIcon> en el menú contextual que ha agregado.  
  
     Con esta propiedad establecida, el menú contextual se mostrará cuando se haga clic en el icono de la barra de tareas.  
  
    > [!NOTE]
    > En el ejemplo de código siguiente se crea una estructura de menú básica. Tendrá que personalizar las opciones de menú a las que se ajustan a la aplicación que está desarrollando. Además, querrá escribir código para controlar los eventos de <xref:System.Windows.Forms.MenuItem.Click> para estos elementos de menú.  
  
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
> Debe inicializar `notifyIcon1` y `contextMenu1,` que puede realizar mediante la inclusión de las siguientes instrucciones en el constructor del formulario:  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [Agregar iconos de aplicación a la barra de tareas con el componente NotifyIcon de formularios Windows Forms](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [NotifyIcon (componente)](notifyicon-component-windows-forms.md)
- [Información general sobre el componente NotifyIcon](notifyicon-component-overview-windows-forms.md)
