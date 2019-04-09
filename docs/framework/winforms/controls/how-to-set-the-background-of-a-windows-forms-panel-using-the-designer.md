---
title: Filtrar para establecer el fondo de un control Panel de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: e66d8c81114a4550f0473f75a8101e79e8db2c76
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103719"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a>Filtrar para establecer el fondo de un control Panel de formularios Windows Forms mediante el diseñador
Un formulario Windows Forms <xref:System.Windows.Forms.Panel> control puede mostrar un color de fondo y una imagen de fondo. El <xref:System.Windows.Forms.Control.BackColor%2A> propiedad establece el color de fondo para los controles que se encuentran en el panel, como etiquetas y botones de radio. Si el <xref:System.Windows.Forms.Control.BackgroundImage%2A> no se establece la propiedad, el <xref:System.Windows.Forms.Control.BackColor%2A> selección llenará el panel. Si el <xref:System.Windows.Forms.Control.BackgroundImage%2A> propiedad está establecida, la imagen se mostrará detrás de los controles que se encuentran en el panel.  
  
 El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contiene un <xref:System.Windows.Forms.Panel> control. Para obtener información acerca de cómo configurar un proyecto de este tipo, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-the-background-in-the-windows-forms-designer"></a>Para establecer el fondo en el Diseñador de Windows Forms  
  
1.  Seleccione el control <xref:System.Windows.Forms.Panel>.  
  
2.  En el **propiedades** ventana, haga clic en el botón de flecha situado junto a la <xref:System.Windows.Forms.Control.BackColor%2A> propiedad para mostrar una ventana con tres fichas.  
  
3.  Seleccione el **personalizado** ficha para mostrar una paleta de colores.  
  
4.  Seleccione el **Web** o **sistema** ficha para mostrar una lista de nombres de colores predefinidos y, a continuación, seleccione un color.  
  
5.  En el **propiedades** ventana, haga clic en el botón de flecha situado junto a la <xref:System.Windows.Forms.Control.BackgroundImage%2A> propiedad.  
  
6.  En el **abierto** cuadro de diálogo, seleccione el archivo que desea mostrar.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Control Panel](panel-control-windows-forms.md)
- [Información general sobre el control Panel](panel-control-overview-windows-forms.md)
- [Filtrar para agrupar controles con el control Panel de formularios Windows Forms mediante el diseñador](group-controls-with-wf-panel-control-using-the-designer.md)
