---
title: "Cómo: Establecer la imagen que muestra un control de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6d9f4d806b39e6e1272ddbb60befdaf8c76e46b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>Cómo: Establecer la imagen que muestra un control de formularios Windows Forms
Varios controles de formularios Windows Forms pueden mostrar imágenes. Estas imágenes pueden ser iconos que clarifican el propósito del control, como un icono del disquete en un botón que denota el **guardar** comando. Como alternativa, los iconos pueden ser imágenes de fondo para proporcionar el control de la apariencia y el comportamiento que desee.  
  
### <a name="to-set-the-image-displayed-by-a-control"></a>Para establecer la imagen que muestra un control  
  
1.  Establecer el control `Image` o `BackgroundImage` propiedad a un objeto de tipo <xref:System.Drawing.Image>. Por lo general, se carga la imagen desde un archivo mediante el uso de la <xref:System.Drawing.Image.FromFile%2A> método.  
  
     En el ejemplo de código siguiente, la ruta de acceso establecida para la ubicación de la imagen es la **Mis imágenes** carpeta. Mayoría de los equipos ejecutan el sistema operativo Windows tendrán este directorio. Esto también permite a los usuarios con niveles de acceso de sistema mínimos ejecutar la aplicación de forma segura. El siguiente ejemplo de código requiere que ya tenga un formulario con un <xref:System.Windows.Forms.PictureBox> control agregado.  
  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Image.FromFile%2A>  
 <xref:System.Drawing.Image>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>
