---
title: "Diccionarios de recursos combinados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "diccionarios de recursos combinados"
  - "diccionarios de recursos combinados"
ms.assetid: d159531f-05d4-49fd-b951-c332de51e5bc
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Diccionarios de recursos combinados
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]recursos admiten una característica de diccionario de recursos combinados. Esta característica proporciona una manera de definir la parte de recursos de un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación fuera de la compilación [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] aplicación. A continuación, se pueden compartir recursos entre aplicaciones y son también más cómodamente aislada para la localización.  
  
## <a name="introducing-a-merged-resource-dictionary"></a>Presentación de un diccionario de recursos combinados  
 En el marcado, se usan la sintaxis siguiente para introducir un diccionario de recursos combinado en una página:  
  
 [!code-xml[ResourceMergeDictionary#MergedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourceMergeDictionary/CS/default.xaml#mergedxaml)]  
  
 Tenga en cuenta que el <xref:System.Windows.ResourceDictionary> el elemento no tiene un [x: Key (directiva)](../../../../docs/framework/xaml-services/x-key-directive.md), que generalmente se necesita para todos los elementos de una colección de recursos. Pero otro <xref:System.Windows.ResourceDictionary> se hace referencia desde el <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> colección es un caso especial, reservado para este escenario de diccionario de recursos combinados. El <xref:System.Windows.ResourceDictionary> que presenta un combinadas diccionario de recursos no puede tener un [x: Key (directiva)](../../../../docs/framework/xaml-services/x-key-directive.md). Normalmente, cada una <xref:System.Windows.ResourceDictionary> dentro de la <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> colección especifica un <xref:System.Windows.ResourceDictionary.Source%2A> atributo. El valor de <xref:System.Windows.ResourceDictionary.Source%2A> debería ser un [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] que se resuelve en la ubicación del archivo de recursos que se va a combinar. El destino de ese [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] debe ser otro [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo, con <xref:System.Windows.ResourceDictionary> como su elemento raíz.  
  
> [!NOTE]
>  Es válido definir recursos dentro de un <xref:System.Windows.ResourceDictionary> que se especifica como un diccionario combinado, ya sea como alternativa a especificar <xref:System.Windows.ResourceDictionary.Source%2A>, o además de recursos que se incluyen en el origen especificado. Sin embargo, esto no es un escenario común; el escenario principal para los diccionarios combinados es combinar recursos procedentes de ubicaciones de archivo externo. Si desea especificar recursos en el marcado de una página, se deberá definirlos en la ventana principal <xref:System.Windows.ResourceDictionary> y no en los diccionarios combinados.  
  
## <a name="merged-dictionary-behavior"></a>Comportamiento del diccionario combinado  
 Recursos de un diccionario combinado ocupan una ubicación en el ámbito de búsqueda de recursos que está justo después del ámbito del diccionario de recursos principal que se combinan. Aunque una clave de recurso debe ser única dentro de los diccionarios individuales, una clave puede existir varias veces en un conjunto de diccionarios combinados. En este caso, el recurso que se devuelve procederá del último diccionario situado secuencialmente en la <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> colección. Si el <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> colección definida en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], entonces el orden de los diccionarios combinados de la colección es el orden de los elementos tal y como se indica en el marcado. Si se define una clave en el diccionario principal y también en un diccionario que se ha combinado, el recurso que se devuelve procederá del diccionario principal. Estas reglas de ámbito aplican igualmente para referencias de recursos estáticos y recursos dinámicos referencias.  
  
### <a name="merged-dictionaries-and-code"></a>Diccionarios combinados y código  
 Diccionarios combinados se pueden agregar a un `Resources` diccionario mediante código. El valor predeterminado, que inicialmente vacío <xref:System.Windows.ResourceDictionary> que existe para cualquier `Resources` propiedad también tiene un valor predeterminado, que inicialmente vacío <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> propiedad de colección. Para agregar un diccionario combinado mediante código, puede obtener una referencia a la principal deseada <xref:System.Windows.ResourceDictionary>, obtener su <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> valor de propiedad y llame a `Add` en el tipo genérico `Collection` que se encuentra en <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A>. El objeto que se agrega debe ser un nuevo <xref:System.Windows.ResourceDictionary>. En el código, no establezca la <xref:System.Windows.ResourceDictionary.Source%2A> propiedad. En su lugar, debe obtener un <xref:System.Windows.ResourceDictionary> objeto creando uno o cargar uno. Una manera de cargar existente <xref:System.Windows.ResourceDictionary> para llamar a <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=fullName> en un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] secuencia de archivo que tiene un <xref:System.Windows.ResourceDictionary> raíz, a continuación, convertir el <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=fullName> valor devuelto para <xref:System.Windows.ResourceDictionary>.  
  
### <a name="merged-resource-dictionary-uris"></a>URI de diccionarios de recursos combinados  
 Existen varias técnicas para incluir un diccionario de recursos combinado, que se indican mediante el [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] formato que va a utilizar. En términos generales, estas técnicas pueden dividirse en dos categorías: los recursos que se compilan como parte del proyecto y recursos que no se compilan como parte del proyecto.  
  
 Para obtener recursos que se compilan como parte del proyecto, puede utilizar una ruta de acceso relativa que hace referencia a la ubicación del recurso. La ruta de acceso relativa se evalúa durante la compilación. El recurso debe definirse como parte del proyecto como una acción de compilación de recursos. Si incluye un archivo .xaml de recursos en el proyecto como recurso, no debe copiar el archivo de recursos en el directorio de resultados, el recurso ya está incluido en la aplicación compilada. También puede utilizar la acción de compilación de contenido, pero debe implementar también los archivos de recursos en la misma relación de ruta de acceso al archivo ejecutable y, a continuación, copie los archivos en el directorio de salida.  
  
> [!NOTE]
>  No utilice la acción de compilación de recurso incrustado. La propia acción de compilación se admite para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones, pero la resolución de <xref:System.Windows.ResourceDictionary.Source%2A> no incorpora <xref:System.Resources.ResourceManager>y, por tanto, no puede separar el recurso individual de la secuencia. Aún se podrían usar los recursos incrustados en las demás aplicaciones que también utiliza <xref:System.Resources.ResourceManager> para tener acceso a los recursos.  
  
 Una técnica relacionada es utilizar un Pack URI a un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de archivos y hacer referencia a él como origen. URI de paquete permite referencias a componentes de ensamblados de referencia y otras técnicas. Para obtener más información sobre los Pack URI, vea [recurso de aplicación de WPF, contenido y archivos de datos](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).  
  
 Para obtener recursos que no se compilan como parte del proyecto, el URI se evalúa en tiempo de ejecución. Puede utilizar un transporte URI común como archivo: o http: para hacer referencia al archivo de recursos. La desventaja de utilizar el enfoque de recursos no compilados es ese archivo: acceso requiere pasos de implementación adicionales y http: access implica la zona de seguridad de Internet.  
  
### <a name="reusing-merged-dictionaries"></a>Reutilizar diccionarios combinados  
 Puede reutilizar o compartir los diccionarios de recursos combinados entre aplicaciones, porque se puede hacer referencia en el diccionario de recursos para combinar a través de cualquier válido [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]. Exactamente cómo hacerlo dependerá de la estrategia de implementación de aplicaciones y modelo de aplicación siga. La estrategia de URI de paquete mencionados anteriormente proporciona una forma de origen normalmente un recurso combinado en varios proyectos durante el desarrollo mediante el uso compartido de una referencia de ensamblado. En este escenario, los recursos aún se distribuyen por el cliente y al menos una de las aplicaciones debe implementar el ensamblado de referencia. También es posible hacer referencia a recursos combinados a través de un URI distribuido que utiliza el protocolo http.  
  
 Escribir diccionarios combinados como archivos de aplicación local o en el almacenamiento compartido local es otro diccionario combinado posibles / escenario de implementación de la aplicación.  
  
### <a name="localization"></a>Localización  
 Si los recursos que deben localizarse están aislados en diccionarios que se combinan en los diccionarios primarios y mantienen separados [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], estos archivos se pueden localizar por separado. Esta técnica es una alternativa ligera a la localización de los ensamblados de recursos satélite. Para obtener más información, consulte [información general de localización y globalización de WPF](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.ResourceDictionary>   
 [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Recursos y código](../../../../docs/framework/wpf/advanced/resources-and-code.md)   
 [Recurso de aplicación de WPF, contenido y archivos de datos](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)