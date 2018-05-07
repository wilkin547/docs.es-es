---
title: 'Cómo: Agregar iconos de aplicación a la barra de tareas con el componente NotifyIcon de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TrayIcon
helpviewer_keywords:
- status area icons
- icons [Windows Forms], adding to taskbar
- NotifyIcon component
- taskbar [Windows Forms], adding icons
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
ms.openlocfilehash: c7658a3a1c72c3fed4033e644d0dd776b06ee1a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a>Cómo: Agregar iconos de aplicación a la barra de tareas con el componente NotifyIcon de formularios Windows Forms
Los formularios de Windows <xref:System.Windows.Forms.NotifyIcon> componente muestra un único icono en el área de notificación de estado de la barra de tareas. Para mostrar múltiples iconos en el área de estado, debe tener varios <xref:System.Windows.Forms.NotifyIcon> componentes en el formulario. Para establecer el icono que se muestra para un control, utilice la <xref:System.Windows.Forms.NotifyIcon.Icon%2A> propiedad. También puede escribir código en el <xref:System.Windows.Forms.NotifyIcon.DoubleClick> controlador de eventos para que algo se produce cuando el usuario hace doble clic en el icono. Por ejemplo, podría realizar un cuadro de diálogo aparece para que el usuario configurar el proceso en segundo plano representado por el icono.  
  
> [!NOTE]
>  El <xref:System.Windows.Forms.NotifyIcon> componente se utiliza solo, con fines de notificación para avisar a los usuarios que se ha producido una acción o un evento o se ha producido un cambio en el estado de algún tipo. Debe usar los menús, barras de herramientas y otros elementos de interfaz de usuario para la interacción estándar con las aplicaciones.  
  
### <a name="to-set-the-icon"></a>Para establecer el icono  
  
1.  Asignar un valor a la <xref:System.Windows.Forms.NotifyIcon.Icon%2A> propiedad. El valor debe ser de tipo `System.Drawing.Icon` y se pueda cargar desde un archivo .ico. Puede especificar el archivo de icono en el código o haciendo clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) junto a la <xref:System.Windows.Forms.NotifyIcon.Icon%2A> propiedad en el  **Propiedades** ventana y, a continuación, seleccione el archivo en el **abiertos** cuadro de diálogo que aparece.  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.NotifyIcon.Visible%2A> en `true`.  
  
3.  Establecer el <xref:System.Windows.Forms.NotifyIcon.Text%2A> propiedad a una cadena adecuada de la información sobre herramientas.  
  
     En el ejemplo de código siguiente, la ruta de acceso establecida para la ubicación del icono es la **Mis documentos** carpeta. Se utiliza esta ubicación porque se puede asumir que la mayoría de los equipos ejecutan el sistema operativo Windows incluirá esta carpeta. Al elegir esta ubicación también permite a los usuarios con niveles de acceso de sistema mínimos ejecutar la aplicación de forma segura. En el ejemplo siguiente, se requiere un formulario con un <xref:System.Windows.Forms.NotifyIcon> control ya se ha agregado. También requiere un archivo de icono denominado `Icon.ico`.  
  
    ```vb  
    ' You should replace the bold icon in the sample below  
    ' with an icon of your own choosing.  
    NotifyIcon1.Icon = New _   
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
    NotifyIcon1.Visible = True  
    NotifyIcon1.Text = "Antivirus program"  
    ```  
  
    ```csharp  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    notifyIcon1.Icon =   
       new System.Drawing.Icon (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Icon.ico");  
    notifyIcon1.Visible = true;  
    notifyIcon1.Text = "Antivirus program";  
    ```  
  
    ```cpp  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    notifyIcon1->Icon = gcnew   
       System::Drawing::Icon(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Icon.ico"));  
    notifyIcon1->Visible = true;  
    notifyIcon1->Text = "Antivirus program";  
    ```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.NotifyIcon>  
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>  
 [Asociar un menú contextual con un componente NotifyIcon de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)  
 [NotifyIcon (componente)](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)  
 [Información general sobre el componente NotifyIcon](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)
