---
title: 'Cómo: Definir y hacer referencia a un recurso'
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: e33c86b03d8b18113f3a15b3ab251753958ff5b2
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646509"
---
# <a name="how-to-define-and-reference-a-resource"></a>Cómo: Definir y hacer referencia a un recurso

En este ejemplo se muestra cómo definir un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]recurso y hacer referencia a él mediante un atributo en .

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se <xref:System.Windows.Media.SolidColorBrush> definen dos <xref:System.Windows.Style> tipos de recursos: un recurso y varios recursos. El <xref:System.Windows.Media.SolidColorBrush> `MyBrush` recurso se utiliza para proporcionar el valor <xref:System.Windows.Media.Brush> de varias propiedades que toman un valor de tipo. Los <xref:System.Windows.Style> `PageBackground`recursos `TitleText` `Label` y cada destino de un tipo de control determinado. Los estilos establecen una variedad de propiedades diferentes en los controles de destino, <xref:System.Windows.FrameworkElement.Style%2A> cuando la clave de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]recurso hace referencia a ese recurso de estilo y se utiliza para establecer la propiedad de varios elementos de control específicos definidos en .

Tenga en cuenta que una de las `Label` propiedades dentro `MyBrush` de los establecedores del estilo también hace referencia al recurso definido anteriormente. Esta es una técnica común, pero es importante recordar que los recursos se analizan y se introducen en un diccionario de recursos en el orden en que se proporcionan. Los recursos también son solicitados por el orden que se encuentra en el diccionario si usa la extensión de [marcado StaticResource](staticresource-markup-extension.md) para hacer referencia a ellos desde dentro de otro recurso. Asegúrese de que cualquier recurso al que haga referencia se define anteriormente dentro de la colección de recursos que donde se solicita ese recurso. Si es necesario, puede evitar el estricto orden de creación de referencias de recursos mediante una extensión de [marcado DynamicResource](dynamicresource-markup-extension.md) para hacer referencia al recurso en tiempo de ejecución en su lugar, pero debe tener en cuenta que esta técnica DynamicResource tiene consecuencias de rendimiento. Para obtener más información, consulta [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

[!code-xaml[FEResource#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]

## <a name="see-also"></a>Consulte también

- [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
