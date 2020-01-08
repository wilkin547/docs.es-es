---
title: Diccionarios de recursos combinados
ms.date: 03/30/2017
helpviewer_keywords:
- merged resource dictionaries [WPF]
- dictionaries [WPF], merged resources
ms.assetid: d159531f-05d4-49fd-b951-c332de51e5bc
ms.openlocfilehash: 899955a9f3302e67de4efa0ce0cb6baf6bf0ec5d
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559786"
---
# <a name="merged-resource-dictionaries"></a>Diccionarios de recursos combinados
Los recursos [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] admiten una característica de diccionario de recursos combinados. Esta característica proporciona una manera de definir la parte de recursos de una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fuera de la aplicación [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compilada. Los recursos se pueden compartir entre aplicaciones y también se aíslan de forma más conveniente para la localización.  
  
## <a name="introducing-a-merged-resource-dictionary"></a>Introducir un diccionario de recursos combinados  
 En la marcación, se usa la sintaxis siguiente para introducir un diccionario de recursos combinados en una página:  
  
 [!code-xaml[ResourceMergeDictionary#MergedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceMergeDictionary/CS/default.xaml#mergedxaml)]  
  
 Tenga en cuenta que el elemento <xref:System.Windows.ResourceDictionary> no tiene una [Directiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md), que normalmente es necesaria para todos los elementos de una colección de recursos. Pero otra referencia <xref:System.Windows.ResourceDictionary> dentro de la colección <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> es un caso especial, reservado para este escenario de Diccionario de recursos combinados. El <xref:System.Windows.ResourceDictionary> que introduce un diccionario de recursos combinados no puede tener una [Directiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md). Normalmente, cada <xref:System.Windows.ResourceDictionary> dentro de la colección <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> especifica un atributo <xref:System.Windows.ResourceDictionary.Source%2A>. El valor de <xref:System.Windows.ResourceDictionary.Source%2A> debe ser un identificador uniforme de recursos (URI) que se resuelva en la ubicación del archivo de recursos que se va a combinar. El destino de ese URI debe ser otro archivo de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], con <xref:System.Windows.ResourceDictionary> como su elemento raíz.  
  
> [!NOTE]
> Es válido definir recursos dentro de una <xref:System.Windows.ResourceDictionary> que se especifica como un diccionario combinado, como alternativa a especificar <xref:System.Windows.ResourceDictionary.Source%2A>, o además de los recursos incluidos en el origen especificado. Sin embargo, esto no es un escenario común: el escenario principal para los diccionarios combinados es combinar recursos desde ubicaciones de archivo externas. Si desea especificar recursos dentro del marcado de una página, normalmente debe definirlos en el <xref:System.Windows.ResourceDictionary> principal y no en los diccionarios combinados.  
  
## <a name="merged-dictionary-behavior"></a>Comportamiento del diccionario combinado  
 Los recursos de un diccionario combinado ocupan una ubicación en el ámbito de búsqueda de recursos que está justo después del ámbito del diccionario de recursos principal en el que se combinan. Aunque una clave de recurso debe ser única dentro de un diccionario individual, una clave puede existir varias veces en un conjunto de diccionarios combinados. En este caso, el recurso que se devuelve procederá del último diccionario encontrado secuencialmente en la colección de <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A>. Si la colección de <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> se definió en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], el orden de los diccionarios combinados en la colección es el orden de los elementos que se proporcionan en el marcado. Si se define una clave en el diccionario principal y también en un diccionario combinado, el recurso que se devuelve procederá del diccionario principal. Estas reglas de ámbito se aplican igualmente para referencias de recursos estáticos y dinámicos.  
  
### <a name="merged-dictionaries-and-code"></a>Diccionarios combinados y código  
 Los diccionarios combinados se pueden agregar a un diccionario `Resources` mediante código. El valor predeterminado, inicialmente vacío <xref:System.Windows.ResourceDictionary> que existe para cualquier propiedad de `Resources` también tiene una propiedad de colección predeterminada, inicialmente <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> vacía. Para agregar un diccionario combinado a través de código, se obtiene una referencia al <xref:System.Windows.ResourceDictionary>principal deseado, se obtiene su valor de propiedad <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> y se llama a `Add` en el `Collection` genérico que se incluye en <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A>. El objeto que agregue debe ser un nuevo <xref:System.Windows.ResourceDictionary>. En el código, no se establece la propiedad <xref:System.Windows.ResourceDictionary.Source%2A>. En su lugar, debe obtener un objeto <xref:System.Windows.ResourceDictionary> creando uno o cargando uno. Una manera de cargar una <xref:System.Windows.ResourceDictionary> existente para llamar a <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> en una secuencia de archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] existente que tiene una raíz <xref:System.Windows.ResourceDictionary> y, a continuación, convertir el valor devuelto de <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> en <xref:System.Windows.ResourceDictionary>.  
  
### <a name="merged-resource-dictionary-uris"></a>URI de diccionarios de recursos combinados  
 Hay varias técnicas para incluir un diccionario de recursos combinados, que se indica mediante el formato de identificador uniforme de recursos (URI) que se va a usar. En términos generales, estas técnicas pueden dividirse en dos categorías: recursos que se compilan como parte del proyecto y recursos que no se compilan como parte del proyecto.  
  
 Para los recursos que se compilan como parte del proyecto, puede usar una ruta de acceso relativa que haga referencia a la ubicación del recurso. La ruta de acceso relativa se evalúa durante la compilación. El recurso debe definirse como parte del proyecto como una acción de compilación de recursos. Si incluye un archivo .xaml de recursos en el proyecto como recurso, no tendrá que copiar el archivo de recursos en el directorio de salida, dado que el recurso ya está incluido en la aplicación compilada. También puede usar la acción de compilación de contenido, pero debe copiar los archivos en el directorio de salida e implementar los archivos de recursos en la misma relación de ruta de acceso que el ejecutable.  
  
> [!NOTE]
> No use la acción de compilación de recurso incrustado. La propia acción de compilación es compatible con las aplicaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], pero la resolución de <xref:System.Windows.ResourceDictionary.Source%2A> no incorpora <xref:System.Resources.ResourceManager>y, por tanto, no puede separar el recurso individual de la secuencia. Puede seguir usando el recurso incrustado para otros propósitos, siempre y cuando use también <xref:System.Resources.ResourceManager> para tener acceso a los recursos.  
  
 Una técnica relacionada es usar un Pack URI en un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y hacer referencia a él como origen. Pack URI habilita las referencias a componentes de ensamblados de referencia y otras técnicas. Para obtener más información sobre Pack URI, consulte [Archivos de recursos, contenido y datos de aplicaciones de WPF](../app-development/wpf-application-resource-content-and-data-files.md).  
  
 Para los recursos que no se compilan como parte del proyecto, el URI se evalúa en tiempo de ejecución. Puede usar un transporte URI común, como file: o http:, para hacer referencia al archivo de recursos. La desventaja de usar el enfoque de recursos no compilados es que el acceso file: requiere pasos de implementación adicionales y el acceso http: implica la zona de seguridad de Internet.  
  
### <a name="reusing-merged-dictionaries"></a>Reutilizar diccionarios combinados  
 Puede reutilizar o compartir diccionarios de recursos combinados entre aplicaciones, ya que se puede hacer referencia al Diccionario de recursos para combinar a través de un identificador uniforme de recursos (URI) válido. Cómo hacerlo exactamente dependerá de la estrategia de implementación de aplicaciones y de qué modelo de aplicación siga. La estrategia Pack URI mencionada anteriormente proporciona una forma de obtener normalmente un recurso combinado entre varios proyectos durante el desarrollo mediante el uso compartido de una referencia de ensamblado. En este escenario, el cliente distribuye los recursos y al menos una de las aplicaciones debe implementar el ensamblado de referencia. También es posible hacer referencia a recursos combinados mediante un URI distribuido que usa el protocolo http.  
  
 Escribir diccionarios combinados como archivos de aplicación locales o en almacenamiento compartido local es otro escenario posible de diccionario combinado o implementación de aplicación.  
  
### <a name="localization"></a>Localización  
 Si los recursos que deben localizarse están aislados en diccionarios que se combinan en diccionarios principales y se mantienen como [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] separados, estos archivos se pueden localizar por separado. Esta técnica es una alternativa ligera a la localización de los ensamblados de recursos satélite. Para obtener más información, consulte [Información general sobre la globalización y la localización de WPF](wpf-globalization-and-localization-overview.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.ResourceDictionary>
- [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Recursos y código](resources-and-code.md)
- [Archivos de recursos, contenido y datos de aplicaciones de WPF](../app-development/wpf-application-resource-content-and-data-files.md)
