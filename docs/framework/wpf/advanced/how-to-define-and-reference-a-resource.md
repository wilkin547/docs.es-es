---
title: Filtrar Definir y hacer referencia a un recurso
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: c429e3373ef1b78fba12dd5125af653f66cf5d74
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371585"
---
# <a name="how-to-define-and-reference-a-resource"></a>Filtrar Definir y hacer referencia a un recurso
En este ejemplo se muestra cómo definir un recurso y haga referencia a él mediante el uso de un atributo en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo define dos tipos de recursos: un <xref:System.Windows.Media.SolidColorBrush> recursos y varios <xref:System.Windows.Style> recursos. El <xref:System.Windows.Media.SolidColorBrush> recursos `MyBrush` se usa para proporcionar el valor de varias propiedades que cada toma un <xref:System.Windows.Media.Brush> tipo de valor. El <xref:System.Windows.Style> recursos `PageBackground`, `TitleText` y `Label` tengan como destino un tipo de control determinado. Los estilos establecen diversas propiedades diferentes en los controles de destino, cuando se hace referencia mediante la clave de recurso de ese recurso de estilo y se usa para establecer el <xref:System.Windows.FrameworkElement.Style%2A> propiedad de varios elementos de control específicos definidos en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Tenga en cuenta que una de las propiedades dentro de los establecedores de la `Label` estilo también hace referencia a la `MyBrush` recurso definido anteriormente. Esta es una técnica común, pero es importante recordar que se analizan y se celebra un diccionario de recursos en el orden en que se les asigna los recursos. También se solicitan los recursos por el orden en que se encuentra en el diccionario si usas el [StaticResource Markup Extension](staticresource-markup-extension.md) para hacer referencia a ellos desde dentro de otro recurso. Asegúrese de que cualquier recurso que se hace referencia se definió anteriormente dentro de la colección de recursos que donde se solicita a continuación, ese recurso. Si es necesario, puede evitar el orden estricto de creación de referencias a recursos mediante el uso de un [DynamicResource Markup Extension](dynamicresource-markup-extension.md) para hacer referencia al recurso en tiempo de ejecución en su lugar, pero debe tener en cuenta que este DynamicResource técnica tiene consecuencias en el rendimiento. Para obtener más información, consulte [recursos XAML](xaml-resources.md).  
  
 [!code-xaml[FEResource#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]  
  
## <a name="see-also"></a>Vea también
- [Recursos XAML](xaml-resources.md)
- [Aplicar estilos y plantillas](../controls/styling-and-templating.md)
