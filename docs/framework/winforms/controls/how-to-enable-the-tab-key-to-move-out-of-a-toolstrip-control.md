---
title: Procedimiento Habilitar la tecla TAB para salir de un Control ToolStrip
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
ms.openlocfilehash: a98c8a54389daa898c877a08f8cc2cae46a11da9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663097"
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a>Procedimiento Habilitar la tecla TAB para salir de un Control ToolStrip
Utilice el procedimiento siguiente para habilitar el usuario presione la tecla TAB para desplazarse de un <xref:System.Windows.Forms.ToolStrip> al siguiente control en el orden de tabulación.  
  
 El <xref:System.Windows.Forms.ToolStrip> acepta la primera pulsación de la tecla TAB y la selección de elementos de teclas de flecha dentro de la <xref:System.Windows.Forms.ToolStrip>. Cuando el usuario presiona la tecla TAB una segunda vez, lleva al usuario al siguiente control en el orden de tabulación.  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a>Para habilitar el usuario presione la tecla TAB para salir de un control ToolStrip al control siguiente  
  
-   Establecer el <xref:System.Windows.Forms.ToolStrip.TabStop%2A> propiedad de la <xref:System.Windows.Forms.ToolStrip> a `true`.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.TabStop%2A>
- [Información sobre el control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
