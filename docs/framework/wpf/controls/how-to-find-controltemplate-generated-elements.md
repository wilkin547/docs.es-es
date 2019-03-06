---
title: Procedimiento Buscar elementos generados por el objeto ControlTemplate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ControlTemplates [WPF], finding elements
- finding ControlTemplate elements [WPF]
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
ms.openlocfilehash: 9a6609d70a6b863f16533aac81ffce4daf171bcf
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364510"
---
# <a name="how-to-find-controltemplate-generated-elements"></a>Filtrar Buscar elementos generados por el objeto ControlTemplate
En este ejemplo se muestra cómo buscar elementos generados por un <xref:System.Windows.Controls.ControlTemplate>.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra un estilo que se crea un simple <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Button> clase:  
  
 [!code-xaml[FindGeneratedItems#CT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 Para buscar un elemento dentro de la plantilla se haya aplicado la plantilla, puede llamar a la <xref:System.Windows.FrameworkTemplate.FindName%2A> método de la <xref:System.Windows.Controls.Control.Template%2A>. En el ejemplo siguiente se crea un cuadro de mensaje que muestra el valor de ancho real de la <xref:System.Windows.Controls.Grid> dentro de la plantilla de control:  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## <a name="see-also"></a>Vea también
- [Find DataTemplate-Generated Elements](../data/how-to-find-datatemplate-generated-elements.md) (Cómo buscar elementos generados por una clase DataTemplate)
- [Aplicar estilos y plantillas](styling-and-templating.md)
- [Ámbitos de nombres XAML de WPF](../advanced/wpf-xaml-namescopes.md)
- [Árboles en WPF](../advanced/trees-in-wpf.md)
