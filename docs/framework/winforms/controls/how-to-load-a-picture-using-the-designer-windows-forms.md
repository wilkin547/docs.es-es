---
title: 'Cómo: Cargar una imagen mediante el Diseñador'
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 12b90d561a18fcffaafb9c45b7fa6be6dd060215
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736329"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Cómo: Cargar una imagen mediante el Diseñador (formularios Windows Forms)

Con el control Windows Forms <xref:System.Windows.Forms.PictureBox>, puede cargar y mostrar una imagen en un formulario en tiempo de diseño si establece la propiedad <xref:System.Windows.Forms.PictureBox.Image%2A> en una imagen válida. En la tabla siguiente se muestran los tipos de archivo aceptables.

|Tipo|Extensión de nombre de archivo|
|---|---|
|Bitmap|.bmp|
|Icono|.ico|
|GIF|.gif|
|CGM|.wmf|
|JPEG|.jpg|

## <a name="to-display-a-picture-at-design-time"></a>Para mostrar una imagen en tiempo de diseño

1. Dibuja un control de <xref:System.Windows.Forms.PictureBox> en un formulario.

2. En la ventana **propiedades** , seleccione la propiedad <xref:System.Windows.Forms.PictureBox.Image%2A> y, a continuación, seleccione el botón de puntos suspensivos para mostrar el cuadro de diálogo **abrir** .

3. Si está buscando un tipo de archivo específico (por ejemplo, archivos. gif), selecciónelo en el cuadro **archivos de tipo** .

4. Seleccione el archivo que desea mostrar.

## <a name="to-clear-the-picture-at-design-time"></a>Para borrar la imagen en tiempo de diseño

1. En la ventana **propiedades** , seleccione la propiedad <xref:System.Windows.Forms.PictureBox.Image%2A>. Haga clic con el botón secundario en la pequeña imagen en miniatura que aparece a la izquierda del nombre del objeto de imagen y, a continuación, elija **restablecer**.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.PictureBox>
- [Información general del control PictureBox](picturebox-control-overview-windows-forms.md)
- [Modificar el tamaño o la situación de una imagen en tiempo de ejecución](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Establecer imágenes en tiempo de ejecución](how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox (control)](picturebox-control-windows-forms.md)
