---
title: Diccionarios de recursos combinados
ms.date: 03/30/2017
helpviewer_keywords:
- merged resource dictionaries [WPF]
- dictionaries [WPF], merged resources
ms.assetid: d159531f-05d4-49fd-b951-c332de51e5bc
ms.openlocfilehash: ae6c8dc3669ed46165f3d78e78735187ebbc3776
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377065"
---
# <a name="merged-resource-dictionaries"></a>Diccionarios de recursos combinados
Los recursos [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] admiten una característica de diccionario de recursos combinados. Esta característica proporciona una manera de definir la parte de recursos de una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fuera de la aplicación [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compilada. Los recursos se pueden compartir entre aplicaciones y también se aíslan de forma más conveniente para la localización.  
  
## <a name="introducing-a-merged-resource-dictionary"></a>Introducir un diccionario de recursos combinados  
 En la marcación, se usa la sintaxis siguiente para introducir un diccionario de recursos combinados en una página:  
  
 [!code-xaml[ResourceMergeDictionary#MergedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceMergeDictionary/CS/default.xaml#mergedxaml)]  
  
 Tenga en cuenta que el <xref:System.Windows.ResourceDictionary> elemento no tiene un [Directiva x: Key](../../xaml-services/x-key-directive.md), que generalmente se necesita para todos los elementos de una colección de recursos. Pero otro <xref:System.Windows.ResourceDictionary> referencia dentro de la <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> colección es un caso especial, reservado para este escenario de diccionario de recursos combinados. El <xref:System.Windows.ResourceDictionary> que presenta un combinado diccionario de recursos no puede tener un [Directiva x: Key](../../xaml-services/x-key-directive.md). Normalmente, cada uno de ellos <xref:System.Windows.ResourceDictionary> dentro de la <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> colección especifica un <xref:System.Windows.ResourceDictionary.Source%2A> atributo. El valor de <xref:System.Windows.ResourceDictionary.Source%2A> debe ser un [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] que se resuelve en la ubicación del archivo de recursos que se combinarán. El destino de ese [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] debe ser otro [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo, con <xref:System.Windows.ResourceDictionary> como su elemento raíz.  
  
> [!NOTE]
>  Es válido definir recursos dentro de un <xref:System.Windows.ResourceDictionary> que se especifica como un diccionario combinado, ya sea como una alternativa a especificar <xref:System.Windows.ResourceDictionary.Source%2A>, o además de cualquier recurso que se incluye en el origen especificado. Sin embargo, esto no es un escenario común: el escenario principal para los diccionarios combinados es combinar recursos desde ubicaciones de archivo externas. Si desea especificar los recursos dentro del marcado de una página, se deberá definirlos en la ventana principal <xref:System.Windows.ResourceDictionary> y no en los diccionarios combinados.  
  
## <a name="merged-dictionary-behavior"></a>Comportamiento del diccionario combinado  
 Los recursos de un diccionario combinado ocupan una ubicación en el ámbito de búsqueda de recursos que está justo después del ámbito del diccionario de recursos principal en el que se combinan. Aunque una clave de recurso debe ser única dentro de un diccionario individual, una clave puede existir varias veces en un conjunto de diccionarios combinados. En este caso, el recurso que se devuelve procederá del último diccionario que se encuentra de forma secuencial en el <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> colección. Si el <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> colección se definió en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], a continuación, el orden de los diccionarios combinados de la colección es el orden de los elementos que se proporciona en el marcado. Si se define una clave en el diccionario principal y también en un diccionario combinado, el recurso que se devuelve procederá del diccionario principal. Estas reglas de ámbito se aplican igualmente para referencias de recursos estáticos y dinámicos.  
  
### <a name="merged-dictionaries-and-code"></a>Diccionarios combinados y código  
 Los diccionarios combinados se pueden agregar a un diccionario `Resources` mediante código. El valor predeterminado, que inicialmente vacío <xref:System.Windows.ResourceDictionary> que existe para cualquier `Resources` propiedad también tiene un valor predeterminado, que inicialmente vacío <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> propiedad de colección. Para agregar un diccionario combinado mediante código, puede obtener una referencia a la principal deseada <xref:System.Windows.ResourceDictionary>, obtener su <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> valor de propiedad y llame a `Add` en el tipo genérico `Collection` que se encuentra en <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A>. El objeto que se agrega debe ser un nuevo <xref:System.Windows.ResourceDictionary>. En el código, no establezca la <xref:System.Windows.ResourceDictionary.Source%2A> propiedad. En su lugar, debe obtener un <xref:System.Windows.ResourceDictionary> objeto creando o cargando uno. Una manera de cargar una existente <xref:System.Windows.ResourceDictionary> para llamar a <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> en una existente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] secuencia de archivo que tiene un <xref:System.Windows.ResourceDictionary> raíz, a continuación, convertir la <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> un valor devuelto para <xref:System.Windows.ResourceDictionary>.  
  
### <a name="merged-resource-dictionary-uris"></a>URI de diccionarios de recursos combinados  
 Existen varias técnicas para incluir un diccionario de recursos combinados, que se indican mediante el formato [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] que usará. En términos generales, estas técnicas pueden dividirse en dos categorías: recursos que se compilan como parte del proyecto y recursos que no se compilan como parte del proyecto.  
  
 Para los recursos que se compilan como parte del proyecto, puede usar una ruta de acceso relativa que haga referencia a la ubicación del recurso. La ruta de acceso relativa se evalúa durante la compilación. El recurso debe definirse como parte del proyecto como una acción de compilación de recursos. Si incluye un archivo .xaml de recursos en el proyecto como recurso, no tendrá que copiar el archivo de recursos en el directorio de salida, dado que el recurso ya está incluido en la aplicación compilada. También puede usar la acción de compilación de contenido, pero debe copiar los archivos en el directorio de salida e implementar los archivos de recursos en la misma relación de ruta de acceso que el ejecutable.  
  
> [!NOTE]
>  No use la acción de compilación de recurso incrustado. Se admite la acción de compilación propia para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] las aplicaciones, pero la resolución de <xref:System.Windows.ResourceDictionary.Source%2A> no incorpora <xref:System.Resources.ResourceManager>y, por tanto, no se puede separar el recurso individual de la secuencia. Todavía podría usar los recursos incrustados para otros fines siempre y cuando también usa <xref:System.Resources.ResourceManager> para tener acceso a los recursos.  
  
 Una técnica relacionada es usar un Pack URI en un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y hacer referencia a él como origen. Pack URI habilita las referencias a componentes de ensamblados de referencia y otras técnicas. Para obtener más información sobre Pack URI, consulte [Archivos de recursos, contenido y datos de aplicaciones de WPF](../app-development/wpf-application-resource-content-and-data-files.md).  
  
 Para los recursos que no se compilan como parte del proyecto, el URI se evalúa en tiempo de ejecución. Puede usar un transporte URI común, como file: o http:, para hacer referencia al archivo de recursos. La desventaja de usar el enfoque de recursos no compilados es que el acceso file: requiere pasos de implementación adicionales y el acceso http: implica la zona de seguridad de Internet.  
  
### <a name="reusing-merged-dictionaries"></a>Reutilizar diccionarios combinados  
 Puede reutilizar o compartir los diccionarios de recursos combinados entre aplicaciones, ya que se puede hacer referencia al diccionario de recursos para combinar mediante cualquier [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] válido. Cómo hacerlo exactamente dependerá de la estrategia de implementación de aplicaciones y de qué modelo de aplicación siga. La estrategia Pack URI mencionada anteriormente proporciona una forma de obtener normalmente un recurso combinado entre varios proyectos durante el desarrollo mediante el uso compartido de una referencia de ensamblado. En este escenario, el cliente distribuye los recursos y al menos una de las aplicaciones debe implementar el ensamblado de referencia. También es posible hacer referencia a recursos combinados mediante un URI distribuido que usa el protocolo http.  
  
 Escribir diccionarios combinados como archivos de aplicación locales o en almacenamiento compartido local es otro escenario posible de diccionario combinado o implementación de aplicación.  
  
### <a name="localization"></a>Localización  
 Si los recursos que deben localizarse están aislados en diccionarios que se combinan en diccionarios principales y se mantienen como [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] separados, estos archivos se pueden localizar por separado. Esta técnica es una alternativa ligera a la localización de los ensamblados de recursos satélite. Para obtener más información, consulte [Información general sobre la globalización y la localización de WPF](wpf-globalization-and-localization-overview.md).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.ResourceDictionary>
- [Recursos XAML](xaml-resources.md)
- [Recursos y código](resources-and-code.md)
- [Archivos de recursos, contenido y datos de aplicaciones de WPF](../app-development/wpf-application-resource-content-and-data-files.md)
