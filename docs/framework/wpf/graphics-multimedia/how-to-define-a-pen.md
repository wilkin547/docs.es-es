---
title: "Cómo: Definir un lápiz"
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
helpviewer_keywords:
- pens [WPF], defining
- creating [WPF], pens
ms.assetid: 7a4f2900-cdf9-49de-84e0-ba5d0ded4d33
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c173b895f67164152d5930efc6a385bc480aaa81
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-define-a-pen"></a>Cómo: Definir un lápiz
En este ejemplo se muestra cómo utilizar un <xref:System.Windows.Media.Pen> para describir una forma. Para crear un sencillo <xref:System.Windows.Media.Pen>, tan sólo necesita especificar su <xref:System.Windows.Media.Pen.Thickness%2A> y <xref:System.Windows.Media.Pen.Brush%2A>. Puede crear más complejo lápiz especificando un <xref:System.Windows.Media.Pen.DashStyle%2A>, <xref:System.Windows.Media.Pen.DashCap%2A>, <xref:System.Windows.Media.Pen.LineJoin%2A>, <xref:System.Windows.Media.Pen.StartLineCap%2A>, y <xref:System.Windows.Media.Pen.EndLineCap%2A>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.Pen> para describir una forma definida por un <xref:System.Windows.Media.GeometryDrawing>.  
  
 [!code-csharp[PenExamples_snip#PenExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PenExamples_snip/CSharp/PenExample.cs#penexamplewholepage)]
 [!code-vb[PenExamples_snip#PenExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PenExamples_snip/VisualBasic/PenExample.vb#penexamplewholepage)]  
  
 ![Esquema producido por un lápiz](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-pen.jpg "graphicsmm_simple_pen")  
GeometryDrawing
