---
title: 'Cómo: Hacer una prueba de posicionamiento en Viewport3D'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3D visuals [WPF], hit-testing for
- hit tests [WPF], for 3D visuals
- Viewport3D [WPF]
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
ms.openlocfilehash: 34bc86349332293e40aca5743cbabb2a48634da6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112094"
---
# <a name="how-to-hit-test-in-a-viewport3d"></a>Cómo: Hacer una prueba de posicionamiento en Viewport3D

Este ejemplo muestra cómo realizar una prueba <xref:System.Windows.Controls.Viewport3D>de posicionación para objetos visuales 3D en un archivo .

Dado <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> que devuelve información 2D y 3D, es posible recorrer en iteración los resultados de la prueba para leer solo los resultados 3D.

[!code-csharp[HitTest3D#HitTest3D3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
[!code-vb[HitTest3D#HitTest3D3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]

El <xref:System.Windows.Media.HitTestResultBehavior> código siguiente determina cómo se procesan los resultados de la prueba de posicionación. `UpdateResultInfo`y `UpdateMaterial` son métodos definidos localmente.

[!code-csharp[HitTest3D#HitTest3D3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
[!code-vb[HitTest3D#HitTest3D3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]
