---
title: Establecer el fondo de un panel mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 8bdefba433632f7ba02f549a549c52c7aa56c2d7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731917"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a>Cómo: establecer el fondo de un panel de Windows Forms mediante el diseñador

Un control de <xref:System.Windows.Forms.Panel> de Windows Forms puede mostrar un color de fondo y una imagen de fondo. La propiedad <xref:System.Windows.Forms.Control.BackColor%2A> establece el color de fondo de los controles contenidos en el panel, como etiquetas y botones de radio. Si no se establece la propiedad <xref:System.Windows.Forms.Control.BackgroundImage%2A>, la selección de <xref:System.Windows.Forms.Control.BackColor%2A> rellenará todo el panel. Si se establece la propiedad <xref:System.Windows.Forms.Control.BackgroundImage%2A>, la imagen se mostrará detrás de los controles contenidos en el panel.

El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.Panel>. Para obtener información sobre cómo configurar este tipo de proyecto en Visual Studio, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="set-the-background-in-the-windows-forms-designer"></a>Establecer el fondo en el Diseñador de Windows Forms

1. Abra el proyecto en Visual Studio y seleccione el control <xref:System.Windows.Forms.Panel>.

2. En la ventana **propiedades** , haga clic en el botón de flecha situado junto a la propiedad <xref:System.Windows.Forms.Control.BackColor%2A> para mostrar una ventana con tres pestañas.

3. Seleccione la pestaña **personalizado** para mostrar una paleta de colores.

4. Seleccione la pestaña **Web** o **sistema** para mostrar una lista de nombres predefinidos para los colores y, a continuación, seleccione un color.

5. En la ventana **propiedades** , haga clic en el botón de flecha situado junto a la propiedad <xref:System.Windows.Forms.Control.BackgroundImage%2A>.

6. En el cuadro de diálogo **abrir** , seleccione el archivo que desea mostrar.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Panel (control)](panel-control-windows-forms.md)
- [Información general del control Panel](panel-control-overview-windows-forms.md)
- [Agrupar controles con el control Panel de Windows Forms mediante el Diseñador](group-controls-with-wf-panel-control-using-the-designer.md)
