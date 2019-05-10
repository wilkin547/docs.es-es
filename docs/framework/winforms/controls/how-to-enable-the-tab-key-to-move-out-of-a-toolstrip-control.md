---
title: Procedimiento para habilitar la tecla TAB para salir de un control ToolStrip
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
ms.openlocfilehash: 7fee9f685b9a9b402cbfe9c265669f7905434986
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64609833"
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a>Procedimiento para habilitar la tecla TAB para salir de un control ToolStrip
Utilice el procedimiento siguiente para habilitar el usuario presione la tecla TAB para desplazarse de un <xref:System.Windows.Forms.ToolStrip> al siguiente control en el orden de tabulación.  
  
 El <xref:System.Windows.Forms.ToolStrip> acepta la primera pulsación de la tecla TAB y la selección de elementos de teclas de flecha dentro de la <xref:System.Windows.Forms.ToolStrip>. Cuando el usuario presiona la tecla TAB una segunda vez, lleva al usuario al siguiente control en el orden de tabulación.  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a>Para habilitar el usuario presione la tecla TAB para salir de un control ToolStrip al control siguiente  
  
- Establecer el <xref:System.Windows.Forms.ToolStrip.TabStop%2A> propiedad de la <xref:System.Windows.Forms.ToolStrip> a `true`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.TabStop%2A>
- [Información sobre el control ToolStrip](toolstrip-control-overview-windows-forms.md)
