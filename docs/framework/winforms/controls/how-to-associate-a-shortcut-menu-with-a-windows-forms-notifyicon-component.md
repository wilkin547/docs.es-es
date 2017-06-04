---
title: "C&#243;mo: Asociar un men&#250; contextual con un componente NotifyIcon de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "menús contextuales, para procesos en segundo plano"
  - "NotifyIcon (componente), asociar menús contextuales"
  - "menús contextuales, para procesos en segundo plano"
ms.assetid: d68f3926-08d3-4f7d-949f-1981b29cf188
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# C&#243;mo: Asociar un men&#250; contextual con un componente NotifyIcon de formularios Windows Forms
> [!NOTE]
>  Aunque los controles <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> reemplazan los controles <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> de versiones anteriores y les agregan funcionalidad, los controles <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> se conservan a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  
  
 El componente <xref:System.Windows.Forms.NotifyIcon> de los formularios Windows Forms muestra un único icono en el área de notificación de estado de la barra de herramientas.  Normalmente, las aplicaciones permiten hacer clic con el botón secundario en este icono para enviar comandos a la aplicación que representa.  Al asociar un componente <xref:System.Windows.Forms.ContextMenu> al componente <xref:System.Windows.Forms.NotifyIcon>, puede agregar esta funcionalidad a sus aplicaciones.  
  
> [!NOTE]
>  Si desea que la aplicación se minimice al inicio mientras muestra una instancia del componente <xref:System.Windows.Forms.NotifyIcon> en la barra de tareas, establezca la propiedad <xref:System.Windows.Forms.Form.WindowState%2A> del formulario principal en <xref:System.Windows.Forms.FormWindowState> y asegúrese de que la propiedad <xref:System.Windows.Forms.NotifyIcon.Visible%2A> del componente <xref:System.Windows.Forms.NotifyIcon> está establecida en `true`.  
  
### Para asociar un menú contextual con el componente NotifyIcon en tiempo de diseño  
  
1.  Agregue un componente <xref:System.Windows.Forms.NotifyIcon> al formulario y establezca las principales propiedades, como las propiedades <xref:System.Windows.Forms.NotifyIcon.Icon%2A> y <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.  
  
     Para obtener más información, vea [Cómo: Agregar iconos de aplicación a la barra de tareas con el componente NotifyIcon de formularios Windows Forms](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).  
  
2.  Agregue un componente <xref:System.Windows.Forms.ContextMenu> al Windows Form.  
  
     Agregue elementos de menú al menú contextual que representa los comandos que desea que estén disponibles en tiempo de ejecución.  Éste es también un buen momento para agregar mejoras a estos elementos de menú, como teclas de acceso.  
  
3.  Establezca la propiedad <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> del <xref:System.Windows.Forms.NotifyIcon> adecuado al menú contextual que agregue.  
  
     Con esta propiedad definida, el menú contextual se mostrará cuando se haga clic en el botón de la barra de tareas.  
  
### Para asociar un menú contextual con el componente NotifyIcon mediante programación  
  
1.  Cree una instancia de la clase <xref:System.Windows.Forms.NotifyIcon> y una clase <xref:System.Windows.Forms.ContextMenu>, con los valores de las propiedades necesarias para la aplicación \(propiedades <xref:System.Windows.Forms.NotifyIcon.Icon%2A> y <xref:System.Windows.Forms.NotifyIcon.Visible%2A> para el componente <xref:System.Windows.Forms.NotifyIcon>, elementos de menú para el componente <xref:System.Windows.Forms.ContextMenu>\).  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> del <xref:System.Windows.Forms.NotifyIcon> adecuado al menú contextual que agregue.  
  
     Con esta propiedad definida, el menú contextual se mostrará cuando se haga clic en el botón de la barra de tareas.  
  
    > [!NOTE]
    >  El ejemplo de código siguiente crea una estructura de menú básica.  Deberá personalizar las opciones de menú para ajustarlas a la aplicación que está desarrollando.  De manera adicional, podría escribir código para controlar los eventos <xref:System.Windows.Forms.MenuItem.Click> de estos elementos de menú.  
  
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
>  Debe inicializar `notifyIcon1` y `contextMenu1,`; para ello, puede incluir las siguientes instrucciones en el constructor del formulario:  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## Vea también  
 <xref:System.Windows.Forms.NotifyIcon>   
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>   
 [Cómo: Agregar iconos de aplicación a la barra de tareas con el componente NotifyIcon de formularios Windows Forms](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md)   
 [NotifyIcon](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)   
 [Información general sobre el componente NotifyIcon](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)