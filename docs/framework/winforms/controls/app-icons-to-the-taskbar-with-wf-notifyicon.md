---
title: Procedimiento Agregar iconos de aplicación a la barra de tareas con el componente NotifyIcon de formularios de Windows
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
ms.openlocfilehash: 04f6b98a2206371a2838b3a6952feeafcd788309
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714260"
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a>Filtrar Agregar iconos de aplicación a la barra de tareas con el componente NotifyIcon de formularios de Windows
Los formularios de Windows <xref:System.Windows.Forms.NotifyIcon> componente muestra un solo icono en el área de notificación de estado de la barra de tareas. Para mostrar varios iconos en el área de estado, debe tener varios <xref:System.Windows.Forms.NotifyIcon> componentes en el formulario. Para establecer el icono que aparece para un control, utilice el <xref:System.Windows.Forms.NotifyIcon.Icon%2A> propiedad. También puede escribir código el <xref:System.Windows.Forms.NotifyIcon.DoubleClick> controlador de eventos, por lo que algo se produce cuando el usuario hace doble clic en el icono. Por ejemplo, podría hacer que un cuadro de diálogo aparecen para que el usuario configurar el proceso en segundo plano representado por el icono.  
  
> [!NOTE]
>  El <xref:System.Windows.Forms.NotifyIcon> componente se utiliza únicamente con fines de notificación para avisar a los usuarios que se ha producido una acción o un evento o se ha producido un cambio en el estado de algún tipo. Debe usar los menús, barras de herramientas y otros elementos de interfaz de usuario para la interacción estándar con las aplicaciones.  
  
### <a name="to-set-the-icon"></a>Para establecer el icono  
  
1.  Asignar un valor a la <xref:System.Windows.Forms.NotifyIcon.Icon%2A> propiedad. El valor debe ser de tipo `System.Drawing.Icon` y se puede cargar desde un archivo .ico. Puede especificar el archivo de icono en el código o haciendo clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) junto a la <xref:System.Windows.Forms.NotifyIcon.Icon%2A> propiedad en el  **Propiedades** ventana y, a continuación, seleccione el archivo en el **abierto** cuadro de diálogo que aparece.  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.NotifyIcon.Visible%2A> en `true`.  
  
3.  Establecer el <xref:System.Windows.Forms.NotifyIcon.Text%2A> propiedad en una cadena adecuada de la información sobre herramientas.  
  
     En el ejemplo de código siguiente establece la ruta de acceso para la ubicación del icono es el **Mis documentos** carpeta. Se utiliza esta ubicación porque se puede suponer que la mayoría de los equipos que ejecutan el sistema operativo de Windows incluirá esta carpeta. Al elegir esta ubicación también permite a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura. El ejemplo siguiente requiere un formulario con un <xref:System.Windows.Forms.NotifyIcon> control ya se ha agregado. También requiere un archivo de icono denominado `Icon.ico`.  
  
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
- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [Cómo: Asociar un menú contextual con un componente NotifyIcon de formularios Windows Forms](how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)
- [NotifyIcon (componente)](notifyicon-component-windows-forms.md)
- [Información general sobre el componente NotifyIcon](notifyicon-component-overview-windows-forms.md)
