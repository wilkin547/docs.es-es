---
title: 'Cómo: Buscar elementos generados por un objeto ControlTemplate'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ControlTemplates [WPF], finding elements
- finding ControlTemplate elements [WPF]
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
ms.openlocfilehash: 232ee7d2859059591c9beff753f45781598a8127
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460706"
---
# <a name="how-to-find-controltemplate-generated-elements"></a>Cómo: Buscar elementos generados por un objeto ControlTemplate
En este ejemplo se muestra cómo buscar elementos generados por un <xref:System.Windows.Controls.ControlTemplate>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un estilo que crea un <xref:System.Windows.Controls.ControlTemplate> simple para la clase <xref:System.Windows.Controls.Button>:  
  
 [!code-xaml[FindGeneratedItems#CT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 Para buscar un elemento dentro de la plantilla una vez aplicada la plantilla, puede llamar al método <xref:System.Windows.FrameworkTemplate.FindName%2A> del <xref:System.Windows.Controls.Control.Template%2A>. En el ejemplo siguiente se crea un cuadro de mensaje que muestra el valor de ancho real del <xref:System.Windows.Controls.Grid> dentro de la plantilla de control:  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## <a name="see-also"></a>Vea también

- [Find DataTemplate-Generated Elements](../data/how-to-find-datatemplate-generated-elements.md) (Cómo buscar elementos generados por una clase DataTemplate)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Ámbitos de nombres XAML de WPF](../advanced/wpf-xaml-namescopes.md)
- [Árboles en WPF](../advanced/trees-in-wpf.md)
