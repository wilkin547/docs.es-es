---
title: "Cómo: Buscar elementos generados por un objeto ControlTemplate"
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
- ControlTemplates [WPF], finding elements
- finding ControlTemplate elements [WPF]
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e4e06de393fa9020277d01f24a332cddb9683bce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-find-controltemplate-generated-elements"></a>Cómo: Buscar elementos generados por un objeto ControlTemplate
Este ejemplo muestra cómo buscar elementos generados por un <xref:System.Windows.Controls.ControlTemplate>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un estilo que se crea un simple <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Button> clase:  
  
 [!code-xaml[FindGeneratedItems#CT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 Para buscar un elemento dentro de la plantilla se haya aplicado la plantilla, puede llamar a la <xref:System.Windows.FrameworkTemplate.FindName%2A> método de la <xref:System.Windows.Controls.Control.Template%2A>. En el ejemplo siguiente se crea un cuadro de mensaje que muestra el valor de ancho real de la <xref:System.Windows.Controls.Grid> dentro de la plantilla de control:  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## <a name="see-also"></a>Vea también  
 [Find DataTemplate-Generated Elements](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md) (Cómo buscar elementos generados por una clase DataTemplate)  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Ámbitos de nombres XAML de WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)  
 [Árboles en WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)
