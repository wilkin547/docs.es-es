---
title: Información general sobre el control Panel
ms.date: 03/30/2017
f1_keywords:
- Panel
helpviewer_keywords:
- grouping controls [Windows Forms], Panel control
- Panel control [Windows Forms], about Panel control
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
ms.openlocfilehash: 3ea86e898e8a3e1ca90ba8e0a6240414702a1a73
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744307"
---
# <a name="panel-control-overview-windows-forms"></a>Información general del control Panel (formularios Windows Forms)
Windows Forms controles de <xref:System.Windows.Forms.Panel> se utilizan para proporcionar una agrupación identificable para otros controles. Normalmente, los paneles se usan para subdividir un formulario por función. Por ejemplo, puede tener un formulario de pedido que especifique opciones de envío de correo electrónico, como la portadora de la noche que se va a usar. Al agrupar todas las opciones de un panel, se proporciona al usuario una indicación visual lógica. En tiempo de diseño, todos los controles se pueden trasladar fácilmente; cuando se mueve el control de <xref:System.Windows.Forms.Panel>, también se mueven todos los controles incluidos. Se puede tener acceso a los controles agrupados en un panel a través de su propiedad <xref:System.Windows.Forms.Control.Controls%2A>. Esta propiedad devuelve una colección de instancias de <xref:System.Windows.Forms.Control>, por lo que normalmente tendrá que convertir un control recuperado de esta manera a su tipo específico.  
  
## <a name="panel-versus-groupbox"></a>Panel frente a GroupBox  
 El control <xref:System.Windows.Forms.Panel> es similar al control <xref:System.Windows.Forms.GroupBox>; sin embargo, solo el control <xref:System.Windows.Forms.Panel> puede tener barras de desplazamiento y solo el control <xref:System.Windows.Forms.GroupBox> muestra un título.  
  
## <a name="key-properties"></a>Propiedades clave  
 Para mostrar las barras de desplazamiento, establezca la propiedad <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> en `true`. También puede personalizar la apariencia del panel si establece las propiedades <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>y <xref:System.Windows.Forms.Panel.BorderStyle%2A>. Para obtener más información sobre las propiedades <xref:System.Windows.Forms.Control.BackColor%2A> y <xref:System.Windows.Forms.Control.BackgroundImage%2A>, vea [Cómo: establecer el fondo de un panel](how-to-set-the-background-of-a-windows-forms-panel.md). La propiedad <xref:System.Windows.Forms.Panel.BorderStyle%2A> determina si el panel se describe sin borde visible (<xref:System.Windows.Forms.BorderStyle.None>), una línea simple (<xref:System.Windows.Forms.BorderStyle.FixedSingle>) o una línea sombreada (<xref:System.Windows.Forms.BorderStyle.Fixed3D>).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Panel>
- [GroupBox (control)](groupbox-control-windows-forms.md)
- [Agrupar controles con el control Panel de Windows Forms mediante el Diseñador](group-controls-with-wf-panel-control-using-the-designer.md)
- [Establecer el fondo de un control Panel de formularios Windows Forms mediante el Diseñador](how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)
