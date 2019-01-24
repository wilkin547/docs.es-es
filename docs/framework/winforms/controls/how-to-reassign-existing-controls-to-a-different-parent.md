---
title: Procedimiento Reasignar controles existentes en un elemento primario diferente
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
ms.openlocfilehash: fa1bd6c0274fdf702072e062e6eeab7078375491
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600289"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a>Procedimiento Reasignar controles existentes en un elemento primario diferente
Puede asignar controles que existen en el formulario a un nuevo control contenedor.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-reassign-existing-controls-to-a-different-parent"></a>Para reasignar los controles existentes en un elemento primario diferente  
  
1.  Arrastre tres controles <xref:System.Windows.Forms.Button> del **cuadro de herramientas** al formulario.  
  
     Colóquelos cerca entre sí, pero sin alinearlos.  
  
2.  En el **cuadro de herramientas**, haga clic en el icono del control <xref:System.Windows.Forms.FlowLayoutPanel> .  
  
     No arrastre el icono hasta el formulario.  
  
3.  Mueva el puntero del mouse cerca de los tres controles <xref:System.Windows.Forms.Button> .  
  
     Observe que el puntero cambia a una cruz con el icono del control <xref:System.Windows.Forms.FlowLayoutPanel> agregado.  
  
4.  Haga clic y mantenga presionado el botón del mouse.  
  
5.  Arrastre el puntero del mouse para dibujar el contorno del control <xref:System.Windows.Forms.FlowLayoutPanel> .  
  
6.  Dibuje el contorno alrededor de los tres controles <xref:System.Windows.Forms.Button> .  
  
7.  Suelte el botón del mouse.  
  
     Observe que los tres controles <xref:System.Windows.Forms.Button> se insertan en el control <xref:System.Windows.Forms.FlowLayoutPanel> .  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Organizar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
- [Tutorial: Organizar controles en formularios de Windows Forms mediante TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Tutorial: Organizar controles en formularios de Windows Forms mediante líneas de ajuste](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
