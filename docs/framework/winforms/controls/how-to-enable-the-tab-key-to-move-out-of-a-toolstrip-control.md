---
title: "Cómo: Habilitar la tecla TAB para salir de un control ToolStrip"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 38a2e331d9530c42be6b9047b11ea235ae81d58d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a>Cómo: Habilitar la tecla TAB para salir de un control ToolStrip
Utilice el procedimiento siguiente para permitir al usuario que presione la tecla TAB para desplazarse de un <xref:System.Windows.Forms.ToolStrip> al siguiente control en el orden de tabulación.  
  
 El <xref:System.Windows.Forms.ToolStrip> acepta la primera que presiona la tecla TAB y la selección de elementos de teclas de flecha dentro de la <xref:System.Windows.Forms.ToolStrip>. Cuando el usuario presiona la tecla TAB una segunda vez, lleva al usuario al siguiente control en el orden de tabulación.  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a>Para permitir al usuario que presione la tecla TAB para salir de un control ToolStrip al control siguiente  
  
-   Establecer el <xref:System.Windows.Forms.ToolStrip.TabStop%2A> propiedad de la <xref:System.Windows.Forms.ToolStrip> a `true`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStrip.TabStop%2A>  
 [Información sobre el control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
