---
title: 'Cómo: Agrupar controles con el control Panel de Windows Forms mediante el Diseñador'
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: 99bfcd96dea1bb92866127095a422003bf01f7cd
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506879"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a>Cómo: Agrupar controles con el control Panel de Windows Forms mediante el Diseñador
Windows Forms <xref:System.Windows.Forms.Panel> controles se usan para agrupar otros controles. Existen tres razones para agrupar controles. Para agrupar elementos de formulario relacionados para una interfaz de usuario clara; forma visual otra es mediante programación de agrupación, de botones de radio, por ejemplo; el último es para mover los controles como una unidad de tiempo de diseño.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-group-of-controls"></a>Para crear un grupo de controles  
  
1.  Arrastre un <xref:System.Windows.Forms.Panel> controlar desde la **Windows Forms** ficha del cuadro de herramientas hasta un formulario.  
  
2.  Agregue otros controles al panel, cada uno dentro del panel de dibujo.  
  
     Si tiene controles que desee incluir en un panel, puede seleccionar todos los controles, cortarlos en el Portapapeles, seleccione el <xref:System.Windows.Forms.Panel> controlar y, a continuación, péguelos en el panel. También puede arrastrar al panel.  
  
3.  (Opcional) Si desea agregar un borde a un panel, establezca su <xref:System.Windows.Forms.BorderStyle> propiedad. Hay tres opciones: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, y <xref:System.Windows.Forms.BorderStyle.None>.  
  
## <a name="see-also"></a>Vea también  
 [Panel (control)](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [Información general del control Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [Establecer el fondo de un panel](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)
