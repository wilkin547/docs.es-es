---
title: "C&#243;mo: Establecer la imagen que muestra un control de formularios Windows Forms | Microsoft Docs"
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
  - "control de botón [Windows Forms], imágenes"
  - "controles [Windows Forms], imágenes"
  - "ejemplos [Windows Forms], controles"
  - "imágenes [Windows Forms], controles de Windows Forms"
  - "controles de Windows Forms, imágenes"
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Establecer la imagen que muestra un control de formularios Windows Forms
Varios controles de formularios Windows Forms pueden mostrar imágenes.  Estas imágenes pueden ser iconos que clarifican el propósito del control, como un icono del disquete en un botón que denota el comando **Guardar**.  Como alternativa, los iconos pueden ser las imágenes de fondo para dar al control el aspecto y comportamiento que desea.  
  
### Para establecer la imagen que se muestra en un control  
  
1.  Establezca la propiedad `Image` del control o la propiedad `BackgroundImage` en un objeto de tipo <xref:System.Drawing.Image>.  Generalmente, se carga la imagen de un archivo utilizando el método <xref:System.Drawing.Image.FromFile%2A>.  
  
     En el ejemplo de código siguiente, la ruta de acceso establecida para la ubicación del icono es la carpeta **Mis imágenes**.  La mayoría de los equipos que ejecutan el sistema operativo Windows incluyen este directorio.  Esto permite también a los usuarios con niveles de acceso mínimos ejecutar la aplicación de un modo seguro.  El ejemplo de código siguiente requiere que ya tenga un formulario con un control <xref:System.Windows.Forms.PictureBox> agregado.  
  
    ```vb  
    ' Replace the image named below  
    ' with an icon of your own choosing.  
    PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.MyPictures) _  
       & "\Image.gif")  
  
    ```  
  
    ```csharp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.MyPictures)  
       + @"\Image.gif");  
  
    ```  
  
    ```cpp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    pictureBox1->Image = Image::FromFile(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::MyPictures),  
       "\\Image.gif"));  
    ```  
  
## Vea también  
 <xref:System.Drawing.Image.FromFile%2A>   
 <xref:System.Drawing.Image>   
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>