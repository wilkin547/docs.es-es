---
title: 'Cómo: Cambiar la propiedad FlowDirection de contenido mediante programación'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- FlowDirection property [WPF], changing programmatically
- documents [WPF], changing FlowDirection property programmatically
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
ms.openlocfilehash: 97a64ad54384077a15a643dc528d043b2ef6627a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-change-the-flowdirection-of-content-programmatically"></a>Cómo: Cambiar la propiedad FlowDirection de contenido mediante programación
Este ejemplo muestra cómo cambiar mediante programación el <xref:System.Windows.FrameworkElement.FlowDirection%2A> propiedad de un <xref:System.Windows.Controls.FlowDocumentReader>.  
  
## <a name="example"></a>Ejemplo  
 Dos <xref:System.Windows.Controls.Button> se crea ningún elemento, cada uno representa uno de los valores posibles de <xref:System.Windows.FlowDirection>. Cuando se hace clic en un botón, el valor de la propiedad asociada se aplica al contenido de un <xref:System.Windows.Controls.FlowDocumentReader> denominado `tf1`.  El valor de propiedad también se escribe en un <xref:System.Windows.Controls.TextBlock> denominado `txt1`.  
  
 [!code-xaml[FlowDirectionSnippets#_FlowDirectionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## <a name="example"></a>Ejemplo  
 Los eventos asociados a los clics de botón definidos anteriormente se administran en un archivo de código subyacente de C#.  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]
