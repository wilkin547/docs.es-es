---
title: "Información general del control Panel (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Panel
helpviewer_keywords:
- grouping controls [Windows Forms], Panel control
- Panel control [Windows Forms], about Panel control
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a8855c88a0ec60cd0d44d73046e44c9614347d90
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="panel-control-overview-windows-forms"></a>Información general del control Panel (formularios Windows Forms)
Formularios Windows Forms <xref:System.Windows.Forms.Panel> controles se utilizan para proporcionar un agrupamiento identificable para otros controles. Por lo general, utilice los paneles para subdividir un formulario por funciones. Por ejemplo, podría tener un formulario de pedido que especifica las opciones de envío de correo directo, como el servicio de transporte urgente que se va a usar. Agrupar todas las opciones en un panel proporciona al usuario una pista visual lógica. En tiempo de diseño todos los controles se pueden mover fácilmente: al mover el <xref:System.Windows.Forms.Panel> controlar, todos los controles que contiene se desplazan también. Pueden tener acceso a los controles agrupados en un panel a través de su <xref:System.Windows.Forms.Control.Controls%2A> propiedad. Esta propiedad devuelve una colección de <xref:System.Windows.Forms.Control> instancias, por lo que normalmente deberá convertir un control recuperan de esta manera a su tipo específico.  
  
## <a name="panel-versus-groupbox"></a>Panel frente a GroupBox  
 El <xref:System.Windows.Forms.Panel> control es similar a la <xref:System.Windows.Forms.GroupBox> control; sin embargo, solo la <xref:System.Windows.Forms.Panel> control puede tener barras de desplazamiento y solo el <xref:System.Windows.Forms.GroupBox> control muestra un título.  
  
## <a name="key-properties"></a>Propiedades clave  
 Para mostrar las barras de desplazamiento, establezca la <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> propiedad `true`. También puede personalizar la apariencia del panel estableciendo la <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, y <xref:System.Windows.Forms.Panel.BorderStyle%2A> propiedades. Para obtener más información sobre la <xref:System.Windows.Forms.Control.BackColor%2A> y <xref:System.Windows.Forms.Control.BackgroundImage%2A> propiedades, consulte [Cómo: establecer el fondo de un Panel de](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md). El <xref:System.Windows.Forms.Panel.BorderStyle%2A> propiedad determina si el panel está rodeado por ningún borde visible (<xref:System.Windows.Forms.BorderStyle.None>), una línea simple (<xref:System.Windows.Forms.BorderStyle.FixedSingle>), o una línea sombreada (<xref:System.Windows.Forms.BorderStyle.Fixed3D>).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Panel>  
 [GroupBox (control)](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)  
 [Agrupar controles con el control Panel de Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)  
 [Establecer el fondo de un control Panel de formularios Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)
