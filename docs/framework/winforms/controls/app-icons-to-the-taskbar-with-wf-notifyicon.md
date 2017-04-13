---
title: "C&#243;mo: Agregar iconos de aplicaci&#243;n a la barra de tareas con el componente NotifyIcon de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TrayIcon"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "iconos, agregar a la barra de tareas"
  - "NotifyIcon (componente)"
  - "iconos del área de estado"
  - "barra de tareas, agregar iconos"
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Agregar iconos de aplicaci&#243;n a la barra de tareas con el componente NotifyIcon de formularios Windows Forms
El componente <xref:System.Windows.Forms.NotifyIcon> de formularios Windows Forms muestra un único icono en el área de notificación de estado de la barra de herramientas.  Para mostrar múltiples iconos en el área de estado, deberá tener múltiples componentes <xref:System.Windows.Forms.NotifyIcon> en el formulario.  Para establecer el icono que muestra un control, utilice la propiedad <xref:System.Windows.Forms.NotifyIcon.Icon%2A>.  También puede escribir código en el controlador de eventos <xref:System.Windows.Forms.NotifyIcon.DoubleClick>, de modo que ocurra algo cuando el usuario haga doble clic en el icono.  Por ejemplo, puede hacer que aparezca un cuadro de diálogo para que el usuario configure el proceso en segundo plano representado por el icono.  
  
> [!NOTE]
>  El componente <xref:System.Windows.Forms.NotifyIcon> se utiliza únicamente con fines informativos, para alertar a los usuarios de que ha tenido lugar una acción o evento, o para indicar que ha habido un cambio en el estado de algún tipo.  Utilice menús, barras de herramientas y otros elementos de interfaz de usuario para la interacción estándar con aplicaciones.  
  
### Para establecer el icono  
  
1.  Asigne un valor a la propiedad <xref:System.Windows.Forms.NotifyIcon.Icon%2A>.  El valor debe ser de tipo  `System.Drawing.Icon`  y se puede cargar desde un archivo .ico.  Puede especificar el archivo de icono en el código o hacer clic en el botón de puntos suspensivos \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) situado junto a la propiedad <xref:System.Windows.Forms.NotifyIcon.Icon%2A> de la ventana **Propiedades** y, a continuación, seleccionar el archivo en el cuadro de diálogo **Abrir** que aparece.  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.NotifyIcon.Visible%2A> en `true`.  
  
3.  Establezca la propiedad <xref:System.Windows.Forms.NotifyIcon.Text%2A> en una cadena ToolTip apropiada.  
  
     En el ejemplo siguiente, la ruta de acceso establecida para la ubicación del icono es la carpeta **Mis documentos**.  Se utiliza esta ubicación porque se puede asumir que la mayoría de los equipos que ejecuten el sistema operativo Windows tendrán esta carpeta.  Al elegir esta ubicación, también se permite a los usuarios con niveles de acceso mínimos ejecutar la aplicación de un modo seguro.  Para el ejemplo siguiente es imprescindible que ya se haya agregado un control <xref:System.Windows.Forms.NotifyIcon> al formulario.  También se necesita un archivo de icono con el nombre `Icon.ico`.  
  
     \[Visual Basic\]  
  
    ```  
    ' You should replace the bold icon in the sample below  
    ' with an icon of your own choosing.  
    NotifyIcon1.Icon = New _   
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
    NotifyIcon1.Visible = True  
    NotifyIcon1.Text = "Antivirus program"  
  
    ```  
  
     \[C\#\]  
  
    ```  
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
  
     \[cpp\]  
  
    ```  
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
  
## Vea también  
 <xref:System.Windows.Forms.NotifyIcon>   
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>   
 [Cómo: Asociar un menú contextual con un componente NotifyIcon de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)   
 [NotifyIcon](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)   
 [Información general sobre el componente NotifyIcon](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)