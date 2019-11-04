---
title: 'Cómo: Definir y hacer referencia a un recurso'
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: 89471c45aabd9f3415c45a2e8af41d1a52900324
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460177"
---
# <a name="how-to-define-and-reference-a-resource"></a>Cómo: Definir y hacer referencia a un recurso

En este ejemplo se muestra cómo definir un recurso y hacer referencia a él mediante un atributo en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se definen dos tipos de recursos: un <xref:System.Windows.Media.SolidColorBrush> recurso y varios recursos <xref:System.Windows.Style>. El `MyBrush` de recursos <xref:System.Windows.Media.SolidColorBrush> se utiliza para proporcionar el valor de varias propiedades, cada una de las cuales toma un valor de tipo <xref:System.Windows.Media.Brush>. Los recursos <xref:System.Windows.Style> `PageBackground`, `TitleText` y `Label` cada uno de ellos tiene como destino un tipo de control determinado. Los estilos establecen una variedad de propiedades diferentes en los controles de destino, cuando se hace referencia a ese recurso de estilo por clave de recurso y se usa para establecer la propiedad <xref:System.Windows.FrameworkElement.Style%2A> de varios elementos de control concretos definidos en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

Tenga en cuenta que una de las propiedades de los establecedores del estilo `Label` también hace referencia al recurso `MyBrush` definido anteriormente. Se trata de una técnica común, pero es importante recordar que los recursos se analizan y se escriben en un diccionario de recursos en el orden en que se proporcionan. Los recursos también se solicitan mediante el orden que se encuentra en el Diccionario si usa la [extensión de marcado StaticResource](staticresource-markup-extension.md) para hacer referencia a ellos desde otro recurso. Asegúrese de que todos los recursos a los que hace referencia se hayan definido previamente dentro de la colección de recursos que la ubicación a la que se solicita ese recurso. Si es necesario, puede solucionar el orden de creación estricto de las referencias de recursos mediante una [extensión de marcado DynamicResource](dynamicresource-markup-extension.md) para hacer referencia al recurso en tiempo de ejecución, pero debe tener en cuenta que esta técnica de DynamicResource tiene rendimiento derivada. Para obtener más información, vea [recursos XAML](xaml-resources.md).

[!code-xaml[FEResource#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]

## <a name="see-also"></a>Vea también

- [Recursos XAML](xaml-resources.md)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
