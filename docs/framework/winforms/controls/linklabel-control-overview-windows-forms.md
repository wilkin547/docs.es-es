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
ms.openlocfilehash: 9837902bf56a402d623adbcf41558dcc568b7105
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745224"
---
# <a name="linklabel-control-overview-windows-forms"></a>Información general sobre el control LinkLabel (formularios Windows Forms)
El control Windows Forms <xref:System.Windows.Forms.LinkLabel> permite agregar vínculos de estilo Web a aplicaciones Windows Forms. Puede usar el control <xref:System.Windows.Forms.LinkLabel> para todo lo que pueda usar el control <xref:System.Windows.Forms.Label> para; también puede establecer parte del texto como un vínculo a un archivo, una carpeta o una página web.  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a>Qué puede hacer con el control LinkLabel  
 Además de todas las propiedades, métodos y eventos del control <xref:System.Windows.Forms.Label>, el control <xref:System.Windows.Forms.LinkLabel> tiene propiedades para los hipervínculos y los colores de los vínculos. La propiedad <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> establece el área del texto que activa el vínculo. Las propiedades <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>y <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> establecen los colores del vínculo. El evento <xref:System.Windows.Forms.LinkLabel.LinkClicked> determina lo que ocurre cuando se selecciona el texto del vínculo.  
  
 El uso más simple del control <xref:System.Windows.Forms.LinkLabel> es mostrar un solo vínculo mediante la propiedad <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, pero también puede mostrar varios hipervínculos mediante la propiedad <xref:System.Windows.Forms.LinkLabel.Links%2A>. La propiedad <xref:System.Windows.Forms.LinkLabel.Links%2A> permite tener acceso a una colección de vínculos. También puede especificar datos en la propiedad <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> de cada objeto de <xref:System.Windows.Forms.LinkLabel.Link> individual. El valor de la propiedad <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> se puede utilizar para almacenar la ubicación de un archivo que se va a mostrar o la dirección de un sitio Web.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.LinkLabel>
- [Información general sobre el control Label](label-control-overview-windows-forms.md)
- [Establecer vínculos con un objeto o página Web mediante el control LinkLabel de formularios Windows Forms](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [Cambiar la apariencia del control LinkLabel de formularios Windows Forms](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
