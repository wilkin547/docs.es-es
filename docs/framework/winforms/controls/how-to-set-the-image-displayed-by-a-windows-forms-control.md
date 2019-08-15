---
title: Procedimiento para establecer la imagen mostrada por un control de formularios Windows Forms
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
ms.openlocfilehash: 99bde4fac7b3057358c7e6a8550efdb4cc351eb0
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69037880"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>Procedimiento Establecer la imagen mostrada por un control Windows Forms

Varios controles Windows Forms pueden mostrar imágenes. Estas imágenes pueden ser iconos que clarifican el propósito del control, como un icono de disquete en un botón que denota el comando **Save** . Como alternativa, los iconos pueden ser imágenes de fondo para dar al control la apariencia y el comportamiento que desea.

## <a name="to-set-the-image-displayed-by-a-control"></a>Para establecer la imagen mostrada por un control

1. Establezca la propiedad o `Image` `BackgroundImage` del control en un objeto de tipo <xref:System.Drawing.Image>. Por lo general, se cargará la imagen desde un archivo mediante el <xref:System.Drawing.Image.FromFile%2A> método.

     En el ejemplo de código siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta **Mis imágenes** . La mayoría de los equipos que ejecutan el sistema operativo Windows incluirán este directorio. Esto también permite a los usuarios con niveles de acceso mínimos del sistema ejecutar la aplicación de forma segura. El siguiente ejemplo de código requiere que ya tenga un formulario con un <xref:System.Windows.Forms.PictureBox> control agregado.

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
