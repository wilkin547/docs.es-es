---
title: Procedimiento Cargar una imagen mediante el diseñador (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 1d95d5baafa42c7dea40933ba837b684d90b7b2b
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972369"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Procedimiento Cargar una imagen mediante el diseñador (Windows Forms)

Con el control <xref:System.Windows.Forms.PictureBox> Windows Forms, puede cargar y mostrar una imagen en un formulario en tiempo de diseño si establece la <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad en una imagen válida. En la tabla siguiente se muestran los tipos de archivo aceptables.

|Type|Extensión de nombre de archivo|
|----------|-------------------------|
|Bitmap|. bmp|
|Iconos|.ico|
|GIF|.gif|
|CGM|. WMF|
|JPEG|.jpg|

> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).

## <a name="to-display-a-picture-at-design-time"></a>Para mostrar una imagen en tiempo de diseño

1. Dibuje un <xref:System.Windows.Forms.PictureBox> control en un formulario.

2. En el ventana Propiedades, seleccione la <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad y haga clic en el botón de puntos suspensivos para mostrar el cuadro de diálogo **abrir** .

3. Si busca un tipo de archivo específico (por ejemplo, archivos. gif), selecciónelo en el cuadro **archivos de tipo** .

4. Seleccione el archivo que desea mostrar.

## <a name="to-clear-the-picture-at-design-time"></a>Para borrar la imagen en tiempo de diseño

1. En la ventana **propiedades** , seleccione la <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad y haga clic con el botón secundario en la pequeña imagen en miniatura que aparece a la izquierda del nombre del objeto de imagen. Elija **restablecer**.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.PictureBox>
- [Información general del control PictureBox](picturebox-control-overview-windows-forms.md)
- [Cómo: Modificar el tamaño o la posición de una imagen en tiempo de ejecución](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Procedimientos: Establecer imágenes en tiempo de ejecución](how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox (control)](picturebox-control-windows-forms.md)
