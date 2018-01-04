---
title: "Cómo: Utilizar una clase de representación de controles"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- visual themes [Windows Forms], applying to Windows Forms controls
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bbf17ea84cb24d167975e6b918a0410a38c8ed3b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-control-rendering-class"></a>Cómo: Utilizar una clase de representación de controles
En este ejemplo se muestra cómo utilizar la <xref:System.Windows.Forms.ComboBoxRenderer> clase para representar la flecha de lista desplegable un combinado de control de cuadro. El ejemplo consta de los <xref:System.Windows.Forms.Control.OnPaint%2A> método de un control personalizado sencillo. El <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> propiedad se utiliza para determinar si están habilitados los estilos visuales en el área de cliente de windows de la aplicación. Si los estilos visuales están activos, la <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> método representará la flecha de lista desplegable con estilos visuales; en caso contrario, el <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> método representará la flecha de lista desplegable en el estilo clásico de Windows.  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control personalizado derivado de la <xref:System.Windows.Forms.Control> clase.  
  
-   Un <xref:System.Windows.Forms.Form> que hospeda el control personalizado.  
  
-   Las referencias a la <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, y <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> los espacios de nombres.  
  
## <a name="see-also"></a>Vea también  
 [Representar controles con estilos visuales](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)
