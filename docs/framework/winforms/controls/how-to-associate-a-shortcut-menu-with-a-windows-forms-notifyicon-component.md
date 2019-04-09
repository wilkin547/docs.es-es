---
title: Filtrar para asociar un menú contextual con un componente NotifyIcon de formularios Windows Forms
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
ms.openlocfilehash: 702a848631ce45c0efcb8eadfdf64074b454ac7d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097995"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a>Filtrar para asociar un menú contextual con un componente NotifyIcon de formularios Windows Forms
> [!NOTE]
>  Aunque <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> reemplazan y agregan funcionalidad a la <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> controles de versiones anteriores, <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> se conservan para compatibilidad con versiones anteriores y uso futuro, si elige.  
  
 El <xref:System.Windows.Forms.NotifyIcon> componente muestra un icono en el área de notificación de estado de la barra de tareas. Normalmente, las aplicaciones permiten que hace clic en este icono para enviar comandos a la aplicación que representa. Asociando un <xref:System.Windows.Forms.ContextMenu> componente con el <xref:System.Windows.Forms.NotifyIcon> , componente, puede agregar esta funcionalidad a sus aplicaciones.  
  
> [!NOTE]
>  Si desea que la aplicación que se debe minimizar al inicio mientras se muestra una instancia de la <xref:System.Windows.Forms.NotifyIcon> conjunto de componentes en la barra de tareas, el formulario principal <xref:System.Windows.Forms.Form.WindowState%2A> propiedad <xref:System.Windows.Forms.FormWindowState.Minimized> y asegúrese del <xref:System.Windows.Forms.NotifyIcon> del componente <xref:System.Windows.Forms.NotifyIcon.Visible%2A> propiedad se establece en `true`.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a>Para asociar un menú contextual con el componente NotifyIcon en tiempo de diseño  
  
1.  Agregar un <xref:System.Windows.Forms.NotifyIcon> al formulario y establecer las propiedades importantes, como el <xref:System.Windows.Forms.NotifyIcon.Icon%2A> y <xref:System.Windows.Forms.NotifyIcon.Visible%2A> propiedades.  
  
     Para obtener más información, vea [Cómo: Agregar iconos de aplicación a la barra de tareas con el Windows Forms control NotifyIcon](app-icons-to-the-taskbar-with-wf-notifyicon.md).  
  
2.  Agregar un <xref:System.Windows.Forms.ContextMenu> al formulario de Windows.  
  
     Agregar elementos de menú al menú contextual que representan los comandos que desea que estén disponibles en tiempo de ejecución. También es un buen momento para agregar mejoras a estos elementos de menú, como las claves de acceso.  
  
3.  Establecer el <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> propiedad de la <xref:System.Windows.Forms.NotifyIcon> componente en el menú contextual que agregó.  
  
     Con esta propiedad establecida, se mostrará el menú contextual cuando se hace clic en el icono de la barra de tareas.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a>Para asociar un menú contextual con el componente NotifyIcon mediante programación  
  
1.  Cree una instancia de la <xref:System.Windows.Forms.NotifyIcon> clase y un <xref:System.Windows.Forms.ContextMenu> (clase), con cualquier configuración de propiedad es necesarios para la aplicación (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> y <xref:System.Windows.Forms.NotifyIcon.Visible%2A> propiedades para el <xref:System.Windows.Forms.NotifyIcon> componente, elementos de menú para el <xref:System.Windows.Forms.ContextMenu> componente).  
  
2.  Establecer el <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> propiedad de la <xref:System.Windows.Forms.NotifyIcon> componente en el menú contextual que agregó.  
  
     Con esta propiedad establecida, se mostrará el menú contextual cuando se hace clic en el icono de la barra de tareas.  
  
    > [!NOTE]
    >  En el ejemplo de código siguiente se crea una estructura de menú básico. Debe personalizar las opciones de menú a los que se ajusten a la aplicación que está desarrollando. Además, desea escribir código para controlar la <xref:System.Windows.Forms.MenuItem.Click> eventos para estos elementos de menú.  
  
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
>  Se debe inicializar `notifyIcon1` y `contextMenu1,` lo que puede hacer mediante la inclusión de las siguientes instrucciones en el constructor del formulario:  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [Filtrar para agregar iconos de aplicación a la barra de tareas con el componente NotifyIcon de formularios Windows Forms](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [Componente NotifyIcon](notifyicon-component-windows-forms.md)
- [Información general sobre el componente NotifyIcon](notifyicon-component-overview-windows-forms.md)
