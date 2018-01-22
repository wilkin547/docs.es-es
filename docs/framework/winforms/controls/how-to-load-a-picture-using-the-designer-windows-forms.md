---
title: "Cómo: Cargar una imagen mediante el Diseñador (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1dec3c71c0c93ce580925744fe55f05cd2e5f383
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Cómo: Cargar una imagen mediante el Diseñador (formularios Windows Forms)
Con los formularios Windows Forms <xref:System.Windows.Forms.PictureBox> (control), puede cargar y mostrar una imagen en un formulario en tiempo de diseño estableciendo la <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad en una imagen válida. En la tabla siguiente muestra los tipos de archivo aceptables.  
  
|Tipo|Extensión de nombre de archivo|  
|----------|-------------------------|  
|Bitmap|.bmp|  
|Iconos|.ico|  
|GIF|.gif|  
|Metarchivo|.wmf|  
|JPEG|.jpg|  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-display-a-picture-at-design-time"></a>Para mostrar una imagen en tiempo de diseño  
  
1.  Dibujar un <xref:System.Windows.Forms.PictureBox> control en un formulario.  
  
2.  En la ventana Propiedades, seleccione la <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad y, a continuación, haga clic en botón de los puntos suspensivos para mostrar el **abiertos** cuadro de diálogo.  
  
3.  Si desea obtener un tipo de archivo específico (por ejemplo, archivos .gif), selecciónela en la **archivos de tipo** cuadro.  
  
4.  Seleccione el archivo que desea mostrar.  
  
### <a name="to-clear-the-picture-at-design-time"></a>Para borrar la imagen en tiempo de diseño  
  
1.  En el **propiedades** ventana, seleccione el <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad y menú contextual de la imagen en miniatura que aparece a la izquierda del nombre del objeto de imagen. Elija **restablecer**.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.PictureBox>  
 [Información general del control PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [Modificar el tamaño o la situación de una imagen en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)  
 [Establecer imágenes en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [PictureBox (control)](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
