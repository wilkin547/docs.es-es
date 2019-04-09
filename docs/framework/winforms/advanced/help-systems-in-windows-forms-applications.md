---
title: Sistemas de ayuda en aplicaciones de Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], adding to Windows applications
- Windows applications [Windows Forms], providing Help systems
- What's This? Help
- Help [Windows Forms], Windows Forms
- HelpProvider component [Windows Forms], providing Help in Windows applications
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
ms.openlocfilehash: 1a02271d59a59f0a6e06a652a34922ba5dcdf1f3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087279"
---
# <a name="help-systems-in-windows-forms-applications"></a>Sistemas de ayuda en aplicaciones de Windows Forms
Una de las ventajas más importantes, como desarrollador de aplicaciones, puede ofrecer a los usuarios es un sistema de ayuda competente. Esto es donde activará cuando estén confundidos o normal desorientarse. Proporcionar un sistema de ayuda en una aplicación basada en Windows se realiza fácilmente mediante el [componente HelpProvider](../controls/helpprovider-component-windows-forms.md).  
  
## <a name="different-types-of-help"></a>Diferentes tipos de ayuda  
 El componente <xref:System.Windows.Forms.HelpProvider> de Windows Forms se utiliza para asociar un archivo de Ayuda HTML Help 1.x (ya sea un archivo .chm generado con HTML Help Workshop o un archivo .htm) con una aplicación basada en Windows. El <xref:System.Windows.Forms.HelpProvider> componente puede utilizarse para proporcionar ayuda contextual para los controles de Windows Forms o controles específicos. Además, el <xref:System.Windows.Forms.HelpProvider> componentes pueden abrir un archivo de ayuda en áreas específicas, como la página principal de una tabla de contenido, un índice o una función de búsqueda. Para obtener información general sobre la <xref:System.Windows.Forms.HelpProvider> componente, vea [información general del componente HelpProvider](../controls/helpprovider-component-overview-windows-forms.md). Para obtener información sobre cómo usar el <xref:System.Windows.Forms.HelpProvider> componente para mostrar Ayuda emergente en los formularios de Windows, vea [Cómo: Mostrar ayuda emergente](how-to-display-pop-up-help.md). Para obtener información sobre el uso de la <xref:System.Windows.Forms.ToolTip> componente para mostrar ayuda específica del control, vea [Control ayuda mediante información sobre herramientas](control-help-using-tooltips.md).  
  
 Puede generar archivos de Ayuda HTML 1.x con HTML Help Workshop. Para obtener más información sobre la Ayuda HTML, vea "HTML Help Workshop" o los otros temas de "HTML Help" en MSDN.  
  
## <a name="see-also"></a>Vea también

- [Integrar la Ayuda de usuario en formularios Windows Forms](integrating-user-help-in-windows-forms.md)
- [Componente HelpProvider](../controls/helpprovider-component-windows-forms.md)
- [ToolTip](../controls/tooltip-component-windows-forms.md)
- [Información general sobre formularios Windows Forms](../windows-forms-overview.md)
- [Windows Forms](../index.md)
