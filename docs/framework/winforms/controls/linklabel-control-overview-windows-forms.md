---
title: Información general sobre el control LinkLabel (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
ms.openlocfilehash: b39c682ccb73a71da1752e6e9f3f79e5916d106c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54503994"
---
# <a name="linklabel-control-overview-windows-forms"></a>Información general sobre el control LinkLabel (formularios Windows Forms)
Los formularios de Windows <xref:System.Windows.Forms.LinkLabel> control le permite agregar vínculos de estilo Web a aplicaciones de Windows Forms. Puede usar el <xref:System.Windows.Forms.LinkLabel> control para todo lo que puede usar el <xref:System.Windows.Forms.Label> de control para; también puede establecer parte del texto como un vínculo a un archivo, carpeta o página Web.  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a>¿Qué puede hacer con el Control LinkLabel  
 Además de todas las propiedades, métodos y eventos de la <xref:System.Windows.Forms.Label> (control), el <xref:System.Windows.Forms.LinkLabel> control tiene propiedades para los hipervínculos y los colores de vínculo. El <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> propiedad establece el área de texto que activa el vínculo. El <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, y <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> propiedades establecen los colores del vínculo. El <xref:System.Windows.Forms.LinkLabel.LinkClicked> evento determina qué ocurre cuando se selecciona el texto del vínculo.  
  
 El uso más simple de la <xref:System.Windows.Forms.LinkLabel> control consiste en mostrar un vínculo único utilizando el <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> propiedad, pero también puede mostrar varios hipervínculos con el <xref:System.Windows.Forms.LinkLabel.Links%2A> propiedad. El <xref:System.Windows.Forms.LinkLabel.Links%2A> propiedad permite obtener acceso a una colección de vínculos. También puede especificar los datos en el <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> propiedad de cada persona <xref:System.Windows.Forms.LinkLabel.Link> objeto. El valor de la <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> propiedad puede usarse para almacenar la ubicación de un archivo para mostrar o la dirección de un sitio Web.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.LinkLabel>
- [Información general sobre el control Label](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)
- [Cómo: Vincular a un objeto o página con el Control LinkLabel de formularios Windows Forms Web](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [Cómo: Cambiar la apariencia del Control LinkLabel de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
