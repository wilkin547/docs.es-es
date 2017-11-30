---
title: "Cómo: Invalidar el árbol lógico"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- overriding the logical tree [WPF]
- logical tree [WPF], overriding
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4cc6045d3505981d93f07347ebd49d57cd759774
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-override-the-logical-tree"></a>Cómo: Invalidar el árbol lógico
Aunque no es necesario en la mayoría de casos, los autores de controles avanzados tienen la opción de invalidar el árbol lógico.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se describe cómo crear subclases de <xref:System.Windows.Controls.StackPanel> para invalidar el árbol lógico, en este caso para aplicar un comportamiento que el panel solo puede tener y solo representará un único elemento secundario. No es necesariamente un comportamiento deseable desde un punto de vista práctico, pero se muestra a continuación para ilustrar el escenario de invalidación del árbol lógico normal de un elemento.  
  
 [!code-csharp[LogicalOverride#SingletonPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 Para más información acerca del árbol lógico, consulte [Árboles en WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).
