---
title: Información general del control Panel (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Panel
helpviewer_keywords:
- grouping controls [Windows Forms], Panel control
- Panel control [Windows Forms], about Panel control
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
ms.openlocfilehash: d4976b3725d04162ac10242c486f57c4d2598769
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086369"
---
# <a name="panel-control-overview-windows-forms"></a>Información general del control Panel (formularios Windows Forms)
Windows Forms <xref:System.Windows.Forms.Panel> controles se usan para proporcionar un agrupamiento identificable para otros controles. Por lo general, utilice paneles para subdividir un formulario mediante la función. Por ejemplo, puede tener un formulario de pedido que especifica las opciones de envío de correo directo como transporte urgente que utilizar. Agrupar todas las opciones en un panel proporciona al usuario una indicación visual de lógica. En tiempo de diseño todos los controles se pueden mover fácilmente, al mover el <xref:System.Windows.Forms.Panel> controlar todos los controles que contiene se desplazan también. Se pueden tener acceso a los controles agrupados en un panel a través de su <xref:System.Windows.Forms.Control.Controls%2A> propiedad. Esta propiedad devuelve una colección de <xref:System.Windows.Forms.Control> instancias, por lo que normalmente necesitará convertir un control recuperan de esta manera a su tipo específico.  
  
## <a name="panel-versus-groupbox"></a>Panel frente a GroupBox  
 El <xref:System.Windows.Forms.Panel> control es similar a la <xref:System.Windows.Forms.GroupBox> controlar; sin embargo, solo el <xref:System.Windows.Forms.Panel> control puede tener barras de desplazamiento y solo el <xref:System.Windows.Forms.GroupBox> control muestra un título.  
  
## <a name="key-properties"></a>Propiedades clave  
 Para mostrar las barras de desplazamiento, establezca la <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> propiedad `true`. También puede personalizar la apariencia del panel estableciendo el <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, y <xref:System.Windows.Forms.Panel.BorderStyle%2A> propiedades. Para obtener más información sobre la <xref:System.Windows.Forms.Control.BackColor%2A> y <xref:System.Windows.Forms.Control.BackgroundImage%2A> propiedades, consulte [Cómo: Establecer el fondo de un Panel](how-to-set-the-background-of-a-windows-forms-panel.md). El <xref:System.Windows.Forms.Panel.BorderStyle%2A> propiedad determina si el panel está rodeado por ningún borde visible (<xref:System.Windows.Forms.BorderStyle.None>), una línea sin formato (<xref:System.Windows.Forms.BorderStyle.FixedSingle>), o una línea sombreada (<xref:System.Windows.Forms.BorderStyle.Fixed3D>).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Panel>
- [GroupBox (control)](groupbox-control-windows-forms.md)
- [Cómo: Agrupar controles con el Control de Panel de Windows Forms mediante el diseñador](group-controls-with-wf-panel-control-using-the-designer.md)
- [Cómo: Establecer el fondo de un Panel de Windows Forms mediante el diseñador](how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)
