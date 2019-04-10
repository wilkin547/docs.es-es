---
title: Filtrar para establecer la imagen mostrada por un control de formularios Windows Forms
ms.date: 03/30/2017
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
ms.openlocfilehash: 1de835bda5ac906837ac3fbd97b87f68f14d1953
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59333930"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>Filtrar para establecer la imagen mostrada por un control de formularios Windows Forms
Varios controles de Windows Forms pueden mostrar imágenes. Estas imágenes pueden ser iconos que aclarar el propósito del control, como un icono de disquete en un botón que denota el **guardar** comando. Como alternativa, los iconos pueden ser las imágenes de fondo para proporcionar el control de la apariencia y comportamiento que desee.  
  
### <a name="to-set-the-image-displayed-by-a-control"></a>Para establecer la imagen que muestra un control  
  
1. Establecer el control `Image` o `BackgroundImage` propiedad a un objeto de tipo <xref:System.Drawing.Image>. Por lo general, se carga la imagen desde un archivo mediante el uso de la <xref:System.Drawing.Image.FromFile%2A> método.  
  
     En el ejemplo de código siguiente establece la ruta de acceso para la ubicación de la imagen es la **Mis imágenes** carpeta. Mayoría de los equipos que ejecutan el sistema operativo de Windows tendrán este directorio. Esto también permite a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura. El siguiente ejemplo de código requiere que ya tiene un formulario con un <xref:System.Windows.Forms.PictureBox> control agregado.  
  
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

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
