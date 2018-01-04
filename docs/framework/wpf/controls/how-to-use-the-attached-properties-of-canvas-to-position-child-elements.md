---
title: "Cómo: Utilizar las propiedades asociadas de Canvas para situar elementos secundarios"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- attached properties [WPF Designer]
- Canvas control [WPF], attached properties
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5314f39c3012826f25fa6c64baf7eb8e42329f58
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-attached-properties-of-canvas-to-position-child-elements"></a>Cómo: Utilizar las propiedades asociadas de Canvas para situar elementos secundarios
Este ejemplo muestra cómo utilizar las propiedades asociadas de <xref:System.Windows.Controls.Canvas> para colocar los elementos secundarios.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se agrega cuatro <xref:System.Windows.Controls.Button> elementos como elementos secundarios de un elemento primario <xref:System.Windows.Controls.Canvas>. Cada elemento secundario representa una propiedad adjunta distinta de <xref:System.Windows.Controls.Canvas>: <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, y <xref:System.Windows.Controls.Canvas.Top%2A>. Cada <xref:System.Windows.Controls.Button> se sitúa en relación con el elemento primario <xref:System.Windows.Controls.Canvas> y de acuerdo con su valor de propiedad asignado.  
  
 [!code-cpp[CanvasAttachedProperties#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.Canvas.Bottom%2A>  
 <xref:System.Windows.Controls.Canvas.Left%2A>  
 <xref:System.Windows.Controls.Canvas.Right%2A>  
 <xref:System.Windows.Controls.Canvas.Top%2A>  
 <xref:System.Windows.Controls.Button>  
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)  
 [Información general sobre propiedades asociadas](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)
