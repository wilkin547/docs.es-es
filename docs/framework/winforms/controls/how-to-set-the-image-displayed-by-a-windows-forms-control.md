---
title: Establecer la imagen mostrada por un control
ms.date: 08/20/2019
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
ms.openlocfilehash: 5df0068c8462bbaab0cb0135de1dd1b91ababe06
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746873"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>Cómo: establecer la imagen mostrada por un control Windows Forms

Varios controles Windows Forms pueden mostrar imágenes. Estas imágenes pueden ser iconos que clarifican el propósito del control, como un icono de disquete en un botón que denota el comando Save. Como alternativa, los iconos pueden ser imágenes de fondo para dar al control la apariencia y el comportamiento que desea.

## <a name="programmatic"></a>Programas

Establezca la propiedad `Image` o `BackgroundImage` del control en un objeto de tipo <xref:System.Drawing.Image>. Por lo general, se cargará la imagen desde un archivo mediante el método <xref:System.Drawing.Image.FromFile%2A>.

En el ejemplo de código siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta **Mis imágenes** . La mayoría de los equipos que ejecutan el sistema operativo Windows incluyen este directorio. Esto también permite a los usuarios con niveles de acceso mínimos del sistema ejecutar la aplicación de forma segura. El siguiente ejemplo de código requiere que ya tenga un formulario con un control <xref:System.Windows.Forms.PictureBox> agregado.

```vb
' Replace the image named below with your own icon.
PictureBox1.Image = Image.FromFile _
   (System.Environment.GetFolderPath _
   (System.Environment.SpecialFolder.MyPictures) _
   & "\Image.gif")
```

```csharp
// Replace the image named below with your own icon.
// Note the escape character used (@) when specifying the path.
pictureBox1.Image = Image.FromFile
   (System.Environment.GetFolderPath
   (System.Environment.SpecialFolder.MyPictures)
   + @"\Image.gif");
```

```cpp
// Replace the image named below with your own icon.
pictureBox1->Image = Image::FromFile(String::Concat
   (System::Environment::GetFolderPath
   (System::Environment::SpecialFolder::MyPictures),
   "\\Image.gif"));
```

## <a name="designer"></a>Diseñador de

1. En la ventana **propiedades** de Visual Studio, seleccione la propiedad **Image** o **BackgroundImage** del control y, a continuación, seleccione el botón de puntos suspensivos (![puntos suspensivos en Visual Studio](./media/visual-studio-ellipsis-button.png)) para mostrar el cuadro de diálogo **seleccionar recurso** .

2. Seleccione la imagen que desea mostrar.

## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
