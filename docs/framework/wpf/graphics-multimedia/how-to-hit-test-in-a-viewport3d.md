---
title: Procedimiento Hacer una prueba de posicionamiento en Viewport3D
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D visuals [WPF], hit-testing for
- hit tests [WPF], for 3-D visuals
- Viewport3D [WPF]
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
ms.openlocfilehash: 54d3ee859a50ed348308b083c48f2dd73d312bbe
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106939"
---
# <a name="how-to-hit-test-in-a-viewport3d"></a>Procedimiento Hacer una prueba de posicionamiento en Viewport3D
En este ejemplo se muestra cómo hacer una prueba de posicionamiento para objetos <xref:System.Windows.Controls.Viewport3D>visuales 3D en un.  
  
 Dado <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> que devuelve información en 2D y 3D, es posible recorrer en iteración los resultados de pruebas para leer solo los resultados 3D.  
  
 [!code-csharp[HitTest3D#HitTest3D3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
 [!code-vb[HitTest3D#HitTest3D3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]  
  
 <xref:System.Windows.Media.HitTestResultBehavior> En el código siguiente se determina cómo se procesan los resultados de las pruebas de posicionamiento.  `UpdateResultInfo`y `UpdateMaterial` son métodos definidos localmente.  
  
 [!code-csharp[HitTest3D#HitTest3D3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
 [!code-vb[HitTest3D#HitTest3D3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]  
 
