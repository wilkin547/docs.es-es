---
title: "Cómo: Establecer el fondo de un control Panel de formularios Windows Forms mediante el Diseñador"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 995dd5982601ba92a2ec23b82acd7131db183835
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a>Cómo: Establecer el fondo de un control Panel de formularios Windows Forms mediante el Diseñador
Un formulario Windows Forms <xref:System.Windows.Forms.Panel> control puede mostrar un color de fondo y una imagen de fondo. El <xref:System.Windows.Forms.Control.BackColor%2A> propiedad establece el color de fondo para los controles que están contenidos en el panel, como las etiquetas y botones de radio. Si el <xref:System.Windows.Forms.Control.BackgroundImage%2A> propiedad no está establecida, la <xref:System.Windows.Forms.Control.BackColor%2A> selección llenará todo el panel. Si el <xref:System.Windows.Forms.Control.BackgroundImage%2A> propiedad está establecida, la imagen se mostrará detrás de los controles que se encuentran en el panel.  
  
 El procedimiento siguiente requiere un **aplicación de Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.Panel> control. Para obtener información acerca de cómo configurar un proyecto de este tipo, consulte [Cómo: crear un proyecto de aplicación de Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, consulte [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-set-the-background-in-the-windows-forms-designer"></a>Para establecer el fondo en el Diseñador de Windows Forms  
  
1.  Seleccione el control <xref:System.Windows.Forms.Panel>.  
  
2.  En el **propiedades** (ventana), haga clic en el botón de flecha junto a la <xref:System.Windows.Forms.Control.BackColor%2A> propiedad para mostrar una ventana con tres fichas.  
  
3.  Seleccione el **personalizado** ficha para mostrar una paleta de colores.  
  
4.  Seleccione el **Web** o **System** ficha para mostrar una lista de nombres de colores predefinidos y, a continuación, seleccione un color.  
  
5.  En el **propiedades** (ventana), haga clic en el botón de flecha junto a la <xref:System.Windows.Forms.Control.BackgroundImage%2A> propiedad.  
  
6.  En el **abiertos** cuadro de diálogo, seleccione el archivo que desea mostrar.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Control.BackColor%2A>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>  
 [Panel (control)](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [Información general del control Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [Agrupar controles con el control Panel de Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)
