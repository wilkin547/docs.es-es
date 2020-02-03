---
title: Agregar iconos de aplicación a la barra de tareas con el componente NotifyIcon
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
ms.openlocfilehash: 46b50ecaabe75dba08fea922d7b5639031692269
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746249"
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a>Cómo: Agregar iconos de aplicación a la barra de tareas con el componente NotifyIcon de formularios Windows Forms

El componente <xref:System.Windows.Forms.NotifyIcon> de Windows Forms muestra un solo icono en el área de notificación de estado de la barra de tareas. Para mostrar varios iconos en el área de estado, debe tener varios componentes <xref:System.Windows.Forms.NotifyIcon> en el formulario. Para establecer el icono mostrado para un control, use la propiedad <xref:System.Windows.Forms.NotifyIcon.Icon%2A>. También puede escribir código en el controlador de eventos <xref:System.Windows.Forms.NotifyIcon.DoubleClick> para que algo ocurra cuando el usuario hace doble clic en el icono. Por ejemplo, puede hacer que aparezca un cuadro de diálogo para que el usuario configure el proceso en segundo plano representado por el icono.

> [!NOTE]
> El componente de <xref:System.Windows.Forms.NotifyIcon> se usa solo con fines informativos, para alertar a los usuarios de que se ha producido una acción o un evento o que ha habido un cambio en el estado de algún tipo. Debe usar menús, barras de herramientas y otros elementos de la interfaz de usuario para la interacción estándar con las aplicaciones.

### <a name="to-set-the-icon"></a>Para establecer el icono

1. Asigne un valor a la propiedad <xref:System.Windows.Forms.NotifyIcon.Icon%2A>. El valor debe ser de tipo `System.Drawing.Icon` y se puede cargar desde un archivo. ico. Puede especificar el archivo de icono en el código o haciendo clic en el botón de puntos suspensivos (![el botón de puntos suspensivos (...) del ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) junto a la propiedad <xref:System.Windows.Forms.NotifyIcon.Icon%2A> en la ventana **propiedades** y, a continuación, seleccionando el archivo en el cuadro de diálogo **abrir** que aparece.

2. Establezca la propiedad <xref:System.Windows.Forms.NotifyIcon.Visible%2A> en `true`.

3. Establezca la propiedad <xref:System.Windows.Forms.NotifyIcon.Text%2A> en una cadena de información sobre herramientas adecuada.

     En el ejemplo de código siguiente, la ruta de acceso establecida para la ubicación del icono es la carpeta **Mis documentos** . Esta ubicación se usa porque puede suponer que la mayoría de los equipos que ejecutan el sistema operativo Windows incluirán esta carpeta. La elección de esta ubicación también permite a los usuarios con niveles de acceso mínimos del sistema ejecutar la aplicación de forma segura. En el ejemplo siguiente se requiere un formulario con un control <xref:System.Windows.Forms.NotifyIcon> ya agregado. También requiere un archivo de icono denominado `Icon.ico`.

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

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [Asociar un menú contextual con un componente NotifyIcon de formularios Windows Forms](how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)
- [NotifyIcon (componente)](notifyicon-component-windows-forms.md)
- [Información general sobre el componente NotifyIcon](notifyicon-component-overview-windows-forms.md)
