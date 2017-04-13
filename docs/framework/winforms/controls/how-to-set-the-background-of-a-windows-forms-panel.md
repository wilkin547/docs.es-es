---
title: "C&#243;mo: Establecer el fondo de un control Panel de formularios Windows Forms | Microsoft Docs"
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
  - "colores de fondo, controles de panel de Windows Forms"
  - "imágenes de fondo, controles de panel de Windows Forms"
  - "colores, controles de panel de Windows Forms"
  - "Panel (control) [Windows Forms], fondo"
ms.assetid: 096cbd8d-45cc-47b8-b1ef-a27f60ea8be0
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Establecer el fondo de un control Panel de formularios Windows Forms
Un control <xref:System.Windows.Forms.Panel> de un formulario Windows Forms puede mostrar tanto un color como una imagen de fondo.  La propiedad <xref:System.Windows.Forms.Control.BackColor%2A> establece el color de fondo para los controles que contiene, como, por ejemplo, etiquetas y botones de radio.  Si la propiedad <xref:System.Windows.Forms.Control.BackgroundImage%2A> no está establecida, la selección <xref:System.Windows.Forms.Control.BackColor%2A> llenará todo el panel.  Si la propiedad <xref:System.Windows.Forms.Control.BackgroundImage%2A> está establecida, la imagen se mostrará detrás de los controles contenidos.  
  
### Para establecer el fondo mediante programación  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.Control.BackColor%2A> del panel en un valor de tipo <xref:System.Drawing.Color?displayProperty=fullName>.  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.Control.BackgroundImage%2A> del panel mediante el método <xref:System.Drawing.Image.FromFile%2A> de la clase <xref:System.Drawing.Image?displayProperty=fullName>.  
  
    ```vb  
    ' You should replace the bolded image   
    ' in the sample below with an image of your own choosing.  
    Panel1.BackgroundImage = Image.FromFile _  
        (System.Environment.GetFolderPath _  
        (System.Environment.SpecialFolder.Personal) _  
        & "\Image.gif")  
  
    ```  
  
    ```csharp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    panel1.BackgroundImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
  
    ```  
  
    ```cpp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    panel1->BackgroundImage = Image::FromFile(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Image.gif"));  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.Control.BackColor%2A>   
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>   
 [Control Panel](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)   
 [Información general del control Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)