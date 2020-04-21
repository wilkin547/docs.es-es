---
title: Información general sobre el control LinkLabel
ms.date: 03/30/2017
f1_keywords:
- LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
ms.openlocfilehash: 3e8607644c858ae804e384c974b5e81c1786c6a1
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739519"
---
# <a name="linklabel-control-overview-windows-forms"></a>Información general sobre el control LinkLabel (formularios Windows Forms)
El control <xref:System.Windows.Forms.LinkLabel> de formularios Windows Forms permite agregar vínculos de estilo Web a aplicaciones de formularios Windows Forms. Puede usar <xref:System.Windows.Forms.LinkLabel> el control para todo <xref:System.Windows.Forms.Label> para lo que puede usar el control; También puede establecer parte del texto como un vínculo a un archivo, carpeta o página web.  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a>Qué puede hacer con el control LinkLabel  
 Además de todas las propiedades, <xref:System.Windows.Forms.Label> métodos <xref:System.Windows.Forms.LinkLabel> y eventos del control, el control tiene propiedades para hipervínculos y colores de vínculo. La <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> propiedad establece el área del texto que activa el vínculo. Las <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>propiedades <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> , , y establecen los colores del vínculo. El <xref:System.Windows.Forms.LinkLabel.LinkClicked> evento determina lo que sucede cuando se selecciona el texto del vínculo.  
  
 El uso más <xref:System.Windows.Forms.LinkLabel> sencillo del control es <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> mostrar un único vínculo mediante la <xref:System.Windows.Forms.LinkLabel.Links%2A> propiedad, pero también puede mostrar varios hipervínculos mediante la propiedad. La <xref:System.Windows.Forms.LinkLabel.Links%2A> propiedad permite tener acceso a una colección de vínculos. También puede especificar datos <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> en la <xref:System.Windows.Forms.LinkLabel.Link> propiedad de cada objeto individual. El valor <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> de la propiedad se puede utilizar para almacenar la ubicación de un archivo para mostrar o la dirección de un sitio Web.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.LinkLabel>
- [Información general sobre el control Label](label-control-overview-windows-forms.md)
- [Procedimiento para establecer vínculos con un objeto o página web mediante el control LinkLabel de formularios Windows Forms](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [Procedimiento para cambiar el aspecto del control LinkLabel de formularios Windows Forms](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
