---
title: Sistemas de ayuda
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], adding to Windows applications
- Windows applications [Windows Forms], providing Help systems
- What's This? Help
- Help [Windows Forms], Windows Forms
- HelpProvider component [Windows Forms], providing Help in Windows applications
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
ms.openlocfilehash: c97a22dbdbdcc0eb282b52e16c4ef40914b1d9e7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742247"
---
# <a name="help-systems-in-windows-forms-applications"></a>Sistemas de ayuda en aplicaciones de Windows Forms
Uno de los courtesies más importantes, como desarrollador de aplicaciones, puede proporcionar a los usuarios un sistema de ayuda competente. Aquí es donde se activan cuando se confunden o desorientan. Proporcionar un sistema de ayuda en una aplicación basada en Windows se realiza fácilmente mediante el [componente HelpProvider](../controls/helpprovider-component-windows-forms.md).  
  
## <a name="different-types-of-help"></a>Distintos tipos de ayuda  
 El componente <xref:System.Windows.Forms.HelpProvider> de Windows Forms se utiliza para asociar un archivo de Ayuda HTML Help 1.x (ya sea un archivo .chm generado con HTML Help Workshop o un archivo .htm) con una aplicación basada en Windows. El componente de <xref:System.Windows.Forms.HelpProvider> se puede usar para proporcionar ayuda contextual para los controles de Windows Forms o controles específicos. Además, el componente de <xref:System.Windows.Forms.HelpProvider> puede abrir un archivo de ayuda en áreas específicas, como la Página principal de una tabla de contenido, un índice o una función de búsqueda. Para obtener información general sobre el componente de <xref:System.Windows.Forms.HelpProvider>, vea [información general sobre el componente HelpProvider](../controls/helpprovider-component-overview-windows-forms.md). Para obtener información sobre cómo usar el componente <xref:System.Windows.Forms.HelpProvider> para mostrar ayuda emergente sobre Windows Forms, consulte [Cómo: Mostrar la ayuda emergente](how-to-display-pop-up-help.md). Para obtener información sobre el uso del componente <xref:System.Windows.Forms.ToolTip> para mostrar la ayuda específica del control, consulte [controlar la ayuda mediante información sobre herramientas](control-help-using-tooltips.md).  
  
 Puede generar archivos HTML de ayuda 1. x con el taller de ayuda HTML. Para obtener más información sobre la ayuda HTML, vea el tema "HTML Help Workshop" u otros temas de "ayuda HTML" en MSDN.  
  
## <a name="see-also"></a>Vea también

- [Integrar la Ayuda de usuario en Windows Forms](integrating-user-help-in-windows-forms.md)
- [HelpProvider (componente)](../controls/helpprovider-component-windows-forms.md)
- [ToolTip (componente)](../controls/tooltip-component-windows-forms.md)
- [Información general sobre formularios Windows Forms](../windows-forms-overview.md)
- [Windows Forms](../index.md)
