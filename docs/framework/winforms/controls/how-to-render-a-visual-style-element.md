---
title: "Cómo: Representar un elemento de estilo visual"
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
- visual themes [Windows Forms], applying to elements of Windows Forms applications
- professional appearance [Windows Forms], applying to elements of Windows Forms applications
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: a207781b-1baa-4ce9-b788-1e951bd4b5df
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 350b6969cfa4ae1b378c574acee73d87ff1dffca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-render-a-visual-style-element"></a>Cómo: Representar un elemento de estilo visual
El <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> expone el espacio de nombres <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> elementos (UI) compatibles con estilos visuales de la interfaz de objetos que representan el usuario de Windows. Este tema muestra cómo utilizar el <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> clase para representar la <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> que representa el **cerrar sesión** y **apagar** botones del menú Inicio.  
  
### <a name="to-render-a-visual-style-element"></a>Para representar un elemento de estilo visual  
  
1.  Crear un <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> y establézcalo en el elemento que va a dibujar. Tenga en cuenta el uso de la <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> propiedad y el <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> método; el <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> constructor iniciará una excepción si los estilos visuales están deshabilitados o un elemento no está definido.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#4)]  
  
2.  Llame a la <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> método para representar el elemento que el <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> representa actualmente.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#6)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control personalizado derivado de la <xref:System.Windows.Forms.Control> clase.  
  
-   Un <xref:System.Windows.Forms.Form> que hospeda el control personalizado.  
  
-   Las referencias a la <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, y <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> los espacios de nombres.  
  
## <a name="see-also"></a>Vea también  
 [Representar controles con estilos visuales](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)
