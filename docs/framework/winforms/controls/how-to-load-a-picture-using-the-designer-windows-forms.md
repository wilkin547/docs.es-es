---
title: Procedimiento para cargar una imagen mediante el diseñador
description: Aprenda a usar el control Windows Forms PictureBox para cargar y mostrar una imagen en un formulario en tiempo de diseño.
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: a05ffe19412fc7a4e3e02f01336d89cce39fac8a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325601"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Cómo: Cargar una imagen mediante el Diseñador (formularios Windows Forms)

Con el <xref:System.Windows.Forms.PictureBox> control Windows Forms, puede cargar y mostrar una imagen en un formulario en tiempo de diseño si establece la <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad en una imagen válida. En la tabla siguiente se muestran los tipos de archivo aceptables.

|Tipo|Extensión de nombre de archivo|
|---|---|
|Bitmap|.bmp|
|Icon|.ico|
|GIF|.gif|
|Metarchivo de |.wmf|
|JPEG|.jpg|

## <a name="to-display-a-picture-at-design-time"></a>Para mostrar una imagen en tiempo de diseño

1. Dibuje un <xref:System.Windows.Forms.PictureBox> control en un formulario.

2. En la ventana **propiedades** , seleccione la <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad y, a continuación, seleccione el botón de puntos suspensivos para mostrar el cuadro de diálogo **abrir** .

3. Si está buscando un tipo de archivo específico (por ejemplo, archivos. gif), selecciónelo en el cuadro **archivos de tipo** .

4. Seleccione el archivo que desea mostrar.

## <a name="to-clear-the-picture-at-design-time"></a>Para borrar la imagen en tiempo de diseño

1. En la ventana **propiedades** , seleccione la <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad. Haga clic con el botón secundario en la pequeña imagen en miniatura que aparece a la izquierda del nombre del objeto de imagen y, a continuación, elija **restablecer**.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.PictureBox>
- [Información general sobre el control PictureBox](picturebox-control-overview-windows-forms.md)
- [Procedimiento para modificar el tamaño o la situación de una imagen en tiempo de ejecución](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Procedimiento para establecer imágenes en tiempo de ejecución](how-to-set-pictures-at-run-time-windows-forms.md)
- [Control PictureBox](picturebox-control-windows-forms.md)
