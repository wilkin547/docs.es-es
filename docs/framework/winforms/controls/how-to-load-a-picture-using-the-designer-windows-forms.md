---
title: Procedimiento Cargar una imagen mediante el diseñador (formularios Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 6142474c2009e0998852dc28d346e73f4abbf1b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539095"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Procedimiento Cargar una imagen mediante el diseñador (formularios Windows Forms)
Con los formularios de Windows <xref:System.Windows.Forms.PictureBox> control, puede cargar y mostrar una imagen en un formulario en tiempo de diseño estableciendo el <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad en una imagen válida. En la tabla siguiente se muestra los tipos de archivo aceptables.  
  
|Tipo|Extensión de nombre de archivo|  
|----------|-------------------------|  
|Bitmap|.bmp|  
|Iconos|.ico|  
|GIF|.gif|  
|Metarchivo|.wmf|  
|JPEG|.jpg|  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-display-a-picture-at-design-time"></a>Para mostrar una imagen en tiempo de diseño  
  
1.  Dibujar un <xref:System.Windows.Forms.PictureBox> control en un formulario.  
  
2.  En la ventana Propiedades, seleccione la <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad y, a continuación, haga clic en botón de puntos suspensivos para mostrar el **abierto** cuadro de diálogo.  
  
3.  Si busca un tipo de archivo específico (por ejemplo, archivos .gif), selecciónelo en la **archivos de tipo** cuadro.  
  
4.  Seleccione el archivo que desea mostrar.  
  
### <a name="to-clear-the-picture-at-design-time"></a>Para borrar la imagen en tiempo de diseño  
  
1.  En el **propiedades** ventana, seleccione el <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad y con el botón secundario en la imagen en miniatura que aparece a la izquierda del nombre del objeto de imagen. Elija **restablecer**.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.PictureBox>
- [Información general del control PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)
- [Cómo: Modificar el tamaño o la ubicación de una imagen en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Cómo: Establecer imágenes en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox (control)](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
