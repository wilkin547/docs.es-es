---
title: 'Cómo: Definir y hacer referencia a un recurso'
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: 347804f0ce6dd3b907d3ac088248a64569a63695
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543499"
---
# <a name="how-to-define-and-reference-a-resource"></a>Cómo: Definir y hacer referencia a un recurso
Este ejemplo muestra cómo definir un recurso y hacer referencia a él mediante el uso de un atributo en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo define dos tipos de recursos: un <xref:System.Windows.Media.SolidColorBrush> recursos y varios <xref:System.Windows.Style> recursos. El <xref:System.Windows.Media.SolidColorBrush> recursos `MyBrush` se usa para proporcionar el valor de varias propiedades que toman cada uno un <xref:System.Windows.Media.Brush> tipo de valor. El <xref:System.Windows.Style> recursos `PageBackground`, `TitleText` y `Label` cada centrarse en un tipo de control determinado. Los estilos de establecen una serie de propiedades diferentes en los controles de destino, cuando ese recurso de estilo al que hace referencia la clave de recurso y se usa para establecer el <xref:System.Windows.FrameworkElement.Style%2A> propiedad de varios elementos de control concretos definidos en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Tenga en cuenta que una de las propiedades de los establecedores de la `Label` estilo también hace referencia el `MyBrush` recurso definido anteriormente. Ésta es una técnica común, pero es importante recordar que se analizan y se escribió en un diccionario de recursos en el orden en que se les asigna recursos. También se solicitan los recursos por el orden en que se encuentra en el diccionario si usas el [extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) para hacer referencia a ellos desde dentro de otro recurso. Asegúrese de que cualquier recurso que se hace referencia se definió anteriormente dentro de la colección de recursos que donde, a continuación, se solicita ese recurso. Si es necesario, se puede solucionar el orden estricto de creación de referencias a recursos utilizando una [extensión de marcado DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) hagan referencia al recurso en tiempo de ejecución en su lugar, pero debe tener en cuenta que este DynamicResource técnica tiene consecuencias en el rendimiento. Para obtener más información, consulte [recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 [!code-xaml[FEResource#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]  
  
## <a name="see-also"></a>Vea también  
 [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)
