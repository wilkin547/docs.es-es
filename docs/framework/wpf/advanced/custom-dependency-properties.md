---
title: "Propiedades de dependencia personalizadas | Microsoft Docs"
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
  - "propiedades de dependencia personalizadas"
  - "propiedades de dependencia, personalizadas"
  - "implementar, contenedores"
  - "metadatos, para propiedades"
  - "propiedades, metadatos"
  - "propiedades, registrar"
  - "registrar propiedades"
  - "contenedores, implementar"
ms.assetid: e6bfcfac-b10d-4f58-9f77-a864c2a2938f
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Propiedades de dependencia personalizadas
En este tema se describen las razones por las que los desarrolladores de aplicaciones y los autores de componentes de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] pueden desear crear una [propiedad de dependencia](GTMT) personalizada, y se describen los pasos de implementación así como algunas opciones de implementación que pueden mejorar el rendimiento, la facilidad de uso o la versatilidad de la propiedad.  
  
   
  
<a name="prerequisites"></a>   
## Requisitos previos  
 En este tema se da por sentado que entiende las propiedades de dependencia desde la perspectiva de un consumidor de las propiedades de dependencia existentes en las clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], y que ha leído el tema [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  Para seguir los ejemplos de este tema, también debe entender [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y debe saber escribir aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="whatis"></a>   
## ¿Qué es una propiedad de dependencia?  
 Puede habilitar lo que de otro modo sería una propiedad de [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] para que admita estilos, enlaces de datos, herencia, animaciones y valores predeterminados implementándola como una [propiedad de dependencia](GTMT).  Las propiedades de dependencia son propiedades que se registran con el sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] llamando al método <xref:System.Windows.DependencyProperty.Register%2A> \(o <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A>\) y que están respaldadas por un campo de identificador <xref:System.Windows.DependencyProperty>.  Las propiedades de dependencia sólo pueden utilizarlas los tipos <xref:System.Windows.DependencyObject>, pero como <xref:System.Windows.DependencyObject> se encuentra bastante arriba en la jerarquía de clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], la mayoría de las clases disponibles en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pueden admitir propiedades de dependencia.  Para obtener más información acerca de las propiedades de dependencia y algunos de los términos y convenciones que se utilizan para describirlas en este [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)], vea [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
<a name="example_dp"></a>   
## Ejemplos de propiedades de dependencia  
 Como ejemplos de propiedades de dependencia que se implementan en clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pueden mencionarse la propiedad <xref:System.Windows.Controls.Control.Background%2A>, la propiedad <xref:System.Windows.FrameworkElement.Width%2A> y la propiedad <xref:System.Windows.Controls.TextBox.Text%2A>, entre muchas otras.  Cada propiedad de dependencia expuesta por una clase tiene expuesto un campo estático público correspondiente de tipo <xref:System.Windows.DependencyProperty> en esa misma clase. Este es el identificador de la propiedad de dependencia.  Al identificador se le asigna un nombre utilizando una convención: el nombre de la [propiedad de dependencia](GTMT) con la cadena `Property` anexada.  Por ejemplo, el campo de identificador <xref:System.Windows.DependencyProperty> correspondiente a la propiedad <xref:System.Windows.Controls.Control.Background%2A> es <xref:System.Windows.Controls.Control.BackgroundProperty>.  El identificador almacena la información sobre la [propiedad de dependencia](GTMT) en el momento de su registro y el identificador se utiliza después para otras operaciones relacionadas con la [propiedad de dependencia](GTMT), como llamar a <xref:System.Windows.DependencyObject.SetValue%2A>.  
  
 Tal y como se indica en [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md), todas las propiedades de dependencia de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] \(salvo la mayoría de las [propiedades adjuntas](GTMT)\) también son propiedades de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] debido a la implementación de "contenedores".  Por lo tanto, puede obtener o establecer las propiedades de dependencia desde el código llamando a los descriptores de acceso de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], que definen los contenedores de la misma manera que utilizaría otras propiedades de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  Como consumidor de propiedades de dependencia establecidas, lo normal es que no utilice los métodos <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A> de <xref:System.Windows.DependencyObject>, que constituyen el punto de conexión con el sistema de propiedades subyacente.  En lugar de ello, lo habitual es que la implementación existente de las propiedades de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] ya haya llamado a <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A> dentro de las implementaciones de contenedor `get` y `set` de la propiedad, utilizando apropiadamente el campo de identificador.  Si está implementando una propiedad de dependencia personalizada propia, estará definiendo el contenedor de forma similar.  
  
<a name="backing_with_dp"></a>   
## ¿Cuándo debe implementarse una propiedad de dependencia?  
 Al implementar una propiedad en una clase, siempre y cuando la clase se derive de <xref:System.Windows.DependencyObject>, tiene la opción de respaldar su propiedad con un identificador <xref:System.Windows.DependencyProperty> y, de este modo, convertirla en una propiedad de dependencia.  No siempre será necesario o adecuado convertir una propiedad en una propiedad de dependencia, sino que dependerá de las necesidades de su escenario.  En ocasiones, será adecuada la técnica típica de respaldar una propiedad con un campo privado.  Sin embargo, debe implementar la propiedad como una [propiedad de dependencia](GTMT) siempre que desee que la propiedad admita una o varias de las siguientes funciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   Desea que su propiedad pueda establecerse en un estilo.  Para obtener más información, consulte [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
-   Desea que su propiedad admita el enlace de datos.  Para obtener más información acerca de las propiedades de dependencia con enlace de datos, vea [Enlazar las propiedades de dos controles](../../../../docs/framework/wpf/data/how-to-bind-the-properties-of-two-controls.md).  
  
-   Desea que su propiedad pueda establecerse con una referencia de recurso dinámico.  Para obtener más información, consulte [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Desea heredar automáticamente el valor de una propiedad de un elemento primario del árbol de elementos.  En este caso, efectúe el registro con el método <xref:System.Windows.DependencyProperty.RegisterAttached%2A>, incluso aunque también cree un contenedor de propiedades para el acceso de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  Para obtener más información, vea [Herencia de valores de propiedad](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
-   Desea que su propiedad pueda animarse.  Para obtener más información, consulte [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Desea que el sistema de propiedades notifique el momento en el que cambie el valor anterior de la propiedad mediante acciones realizadas por el sistema de propiedades, el entorno o el usuario, o mediante la lectura y el uso de estilos.  El uso de metadatos de propiedad permite que su propiedad especifique un método de devolución de llamada que se invocará cada vez que el sistema de propiedades determine que el valor de propiedad ha cambiado definitivamente.  Un concepto relacionado esto último es la conversión del valor de propiedad.  Para obtener más información, consulte [Devoluciones de llamada y validación de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md).  
  
-   Desea utilizar convenciones de metadatos establecidas que también se utilizan en los procesos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], como notificar si el cambio de valor de propiedad debe exigir que el sistema de diseño recomponga la representación visual de un elemento.  O bien, desea poder utilizar invalidaciones para los metadatos de forma que las clases derivadas puedan modificar las características basadas en metadatos, como el valor predeterminado.  
  
-   Desea que las propiedades de un control personalizado sean compatibles con características de [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)], como la edición en la ventana **Propiedades**.  Para obtener más información, consulte [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Al examinar estos escenarios, también debe tener en cuenta si puede obtener su escenario invalidando los metadatos de una [propiedad de dependencia](GTMT) existente, en lugar de implementar una propiedad completamente nueva.  La invalidación de los metadatos será factible o no en función de su escenario y de la similitud de dicho escenario con la implementación de las clases y propiedades de dependencia de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Para obtener más información acerca de cómo invalidar los metadatos de las propiedades existentes, vea [Metadatos de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
<a name="checklist"></a>   
## Lista de comprobación para definir una propiedad de dependencia  
 La definición de una propiedad de dependencia consiste en cuatro conceptos distintos.  Estos conceptos no son necesariamente los pasos de un procedimiento estricto, ya que algunos de ellos acaban combinándose en una sola línea de código en la implementación:  
  
-   \(Opcional\) Cree metadatos de propiedad para la propiedad de dependencia.  
  
-   Registre el nombre de la propiedad con el sistema de propiedades, especificando un tipo de propietario y el tipo de valor de propiedad.  Especifique también los metadatos de la propiedad, si se utilizan.  
  
-   Defina un identificador <xref:System.Windows.DependencyProperty> como un campo `public``static``readonly` en el tipo de propietario.  
  
-   Defina una propiedad de "contenedor" de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] cuyo nombre coincida con el nombre de la propiedad de dependencia.  Implemente los descriptores de acceso `get` y `set` de la propiedad de "contenedor" de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] para conectarla con la propiedad de dependencia que la respalda.  
  
<a name="registering"></a>   
### Registrar la propiedad con el sistema de propiedades  
 Para que su propiedad sea una [propiedad de dependencia](GTMT), deberá registrarla en una tabla que mantiene el sistema de propiedades y asignarle un identificador único que se utilice como calificador para las operaciones posteriores del sistema de propiedades.  Estas operaciones podrían ser operaciones internas o su propio código llamando a las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] del sistema de propiedades.  Para registrar la propiedad, llame al método <xref:System.Windows.DependencyProperty.Register%2A> dentro del cuerpo de su clase \(dentro de la clase, pero fuera de las definiciones de miembros\).  La llamada al método <xref:System.Windows.DependencyProperty.Register%2A> también proporciona el campo de identificador como valor devuelto.  La razón por la que la llamada a <xref:System.Windows.DependencyProperty.Register%2A> se realiza fuera de las demás definiciones de miembros es porque este valor devuelto se utiliza para asignar y crear un campo `public` `static` `readonly` de tipo <xref:System.Windows.DependencyProperty> como parte de la clase.  Este campo se convierte en el identificador para la propiedad de dependencia.  
  
 [!code-csharp[WPFAquariumSln#RegisterAG](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerag)]
 [!code-vb[WPFAquariumSln#RegisterAG](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerag)]  
  
<a name="nameconventions"></a>   
### Convenciones de nomenclatura de las propiedades de dependencia  
 Existen convenciones de nomenclatura establecidas para las propiedades de dependencia que debe cumplir siempre salvo en circunstancias excepcionales.  
  
 La propiedad de dependencia propiamente dicha tendrá un nombre básico, como "AquariumGraphic" en este ejemplo, que se proporciona como primer parámetro de <xref:System.Windows.DependencyProperty.Register%2A>.  Este nombre debe ser único para cada tipo de registro.  Se considera que las propiedades de dependencia heredadas a través de los tipos base ya forman parte del tipo de registro; los nombres de las propiedades heredadas no pueden volver a registrarse.  No obstante, existe una técnica para agregar una clase como propietario de una propiedad de dependencia, aunque dicha propiedad de dependencia no sea heredada; para obtener información detallada, vea [Metadatos de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
 Al crear el campo de identificador, asígnele el nombre de la propiedad tal y como lo registró, más el sufijo `Property`.  Este campo es el identificador de la propiedad de dependencia y se utilizará después como entrada para las llamadas a <xref:System.Windows.DependencyObject.SetValue%2A> y <xref:System.Windows.DependencyObject.GetValue%2A> que se realizarán en los contenedores, por parte de cualquier otro acceso de código a la propiedad efectuado por el código propio, por parte de cualquier acceso de código externo permitido, por parte del sistema de propiedades y, posiblemente, por parte de los procesadores de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
> [!NOTE]
>  La implementación típica consiste en definir la propiedad de dependencia en el cuerpo de la clase, pero también es posible definir una propiedad de dependencia en el constructor estático de la clase.  Este enfoque podría tener sentido es necesaria más de una línea de código para inicializar la propiedad de dependencia.  
  
<a name="wrapper1"></a>   
### Implementar el "contenedor"  
 Su implementación del contenedor debería llamar a <xref:System.Windows.DependencyObject.GetValue%2A> en la implementación de `get` y a <xref:System.Windows.DependencyObject.SetValue%2A> en la implementación de `set` \(el campo y la llamada de registro original también se muestran aquí para mayor claridad\).  
  
 Salvo en circunstancias excepcionales, sus implementaciones de contenedores sólo deberían realizar las acciones <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A>, respectivamente.  El motivo de ello se explica en el tema [Carga de XAML y propiedades de dependencia](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md).  
  
 Todas las propiedades de dependencia públicas existentes que se incluyen en las clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizan este modelo de implementación de contenedor simple; la mayor parte de la complejidad del funcionamiento de las propiedades de dependencia es inherentemente un comportamiento del sistema de propiedades o se implementa a través de otros conceptos, como la conversión o las devoluciones de llamada de cambio de propiedad a través de los metadatos de las propiedades.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
 De nuevo, por convención, el nombre de la propiedad de contenedor debe coincidir con el nombre elegido y usado como primer parámetro de la llamada a <xref:System.Windows.DependencyProperty.Register%2A> que registró la propiedad.  Si su propiedad no cumple esta convención, no necesariamente se deshabilitan todos los usos posibles, pero encontrará varios problemas importantes:  
  
-   No funcionarán determinados aspectos de los estilos y las plantillas.  
  
-   La mayoría de las herramientas y los diseñadores deben basarse en las convenciones de nomenclatura para serializar correctamente el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o para proporcionar ayuda sobre cada propiedad en el entorno de diseñador.  
  
-   La implementación actual del cargador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] omite los contenedores por completo y se basa en la convención de nomenclatura a la hora de procesar los valores de los atributos.  Para obtener más información, consulte [Carga de XAML y propiedades de dependencia](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md).  
  
<a name="metadata"></a>   
### Metadatos de propiedad para una nueva propiedad de dependencia  
 Al registrar una propiedad de dependencia mediante el sistema de propiedades, se crea un objeto de metadatos en el que se almacenan las características de la propiedad.  Muchas de estas características presentan valores predeterminados que se establecen si la propiedad se registra con las firmas simples de <xref:System.Windows.DependencyProperty.Register%2A>.  Otras firmas de <xref:System.Windows.DependencyProperty.Register%2A> le permiten especificar los metadatos que desea al registrar la propiedad.  Los metadatos más comunes para las propiedades de dependencia consisten en asignarles un valor predeterminado que se aplica a las nuevas instancias que utilizan la propiedad.  
  
 Si está creando una propiedad de dependencia que existe en una clase derivada de <xref:System.Windows.FrameworkElement>, puede utilizar la clase de metadatos <xref:System.Windows.FrameworkPropertyMetadata> más especializada en lugar de la clase <xref:System.Windows.PropertyMetadata> base.  El constructor de la clase <xref:System.Windows.FrameworkPropertyMetadata> presenta varias firmas en las que puede especificar conjuntamente varias características de los metadatos.  Si sólo desea especificar el valor predeterminado, utilice la firma que toma un único parámetro de tipo <xref:System.Object>.  Pase dicho parámetro de objeto como un valor predeterminado específico del tipo para su propiedad \(el valor predeterminado proporcionado debe ser el tipo que proporcionó como parámetro `propertyType` en la llamada a <xref:System.Windows.DependencyProperty.Register%2A>\).  
  
 En el caso de <xref:System.Windows.FrameworkPropertyMetadata>, también puede especificar marcadores de opciones de metadatos para su propiedad.  Estos marcadores se convierten en propiedades discretas en los metadatos de la propiedad después del registro y se utilizan para comunicar determinadas instrucciones condicionales a otros procesos, como el motor de diseño.  
  
#### Establecer marcadores de metadatos adecuados  
  
-   Si su propiedad \(o los cambios realizados en su valor\) afecta a la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] y, en especial, afecta al modo en que el sistema de diseño debe cambiar de tamaño o representar su elemento en una página, establezca uno o varios de los marcadores siguientes: <xref:System.Windows.FrameworkPropertyMetadataOptions>, <xref:System.Windows.FrameworkPropertyMetadataOptions>, <xref:System.Windows.FrameworkPropertyMetadataOptions>.  
  
    -   <xref:System.Windows.FrameworkPropertyMetadataOptions> indica que un cambio realizado en esta propiedad exige un cambio en la representación de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] en el que el objeto contenedor puede necesitar más o menos espacio dentro del elemento primario.  Por ejemplo, una propiedad "Width" debe tener establecido este marcador.  
  
    -   <xref:System.Windows.FrameworkPropertyMetadataOptions> indica que un cambio realizado en esta propiedad exige un cambio en la representación de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que normalmente no requiere un cambio en el espacio dedicado, sino que indica que ha cambiado la posición dentro del espacio.  Por ejemplo, una propiedad "Alignment" debe tener establecido este marcador.  
  
    -   <xref:System.Windows.FrameworkPropertyMetadataOptions> indica que se ha producido algún otro cambio que no afectará al diseño ni a las medidas, pero que requiere actualizar la representación.  Un ejemplo sería una propiedad que cambia un color de un elemento existente, como "Background".  
  
    -   Estos marcadores suelen utilizarse como un protocolo en los metadatos para sus propias implementaciones de invalidación del sistema de propiedades o devoluciones de llamada de diseño.  Por ejemplo, puede tener una devolución de llamada <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> que llame a <xref:System.Windows.UIElement.InvalidateArrange%2A> si alguna de las propiedades de la instancia notifica un cambio de valor y tiene la propiedad <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> establecida en `true` en sus metadatos.  
  
-   Algunas propiedades pueden afectar a las características de representación del elemento primario contenedor de forma mucho más drástica que los cambios de tamaño necesarios mencionados anteriormente.  Un ejemplo es la propiedad <xref:System.Windows.Documents.Paragraph.MinOrphanLines%2A> que se utiliza en el modelo de documentos dinámicos, cuyos cambios pueden afectar a la representación global del documento dinámico que contiene el párrafo.  Utilice <xref:System.Windows.FrameworkPropertyMetadataOptions> o <xref:System.Windows.FrameworkPropertyMetadataOptions> para identificar casos similares en sus propias propiedades.  
  
-   De forma predeterminada, las propiedades de dependencia admiten el enlace de datos.  Puede deshabilitarlo intencionadamente en casos en los que no haya ningún escenario realista para el enlace de datos o en los que el rendimiento del enlace de datos para un objeto de gran tamaño suponga un problema.  
  
-   De forma predeterminada, el <xref:System.Windows.Data.Binding.Mode%2A> de enlace de datos para las propiedades de dependencia toma como valor predeterminado <xref:System.Windows.Data.BindingMode>.  Siempre puede cambiar el enlace para que sea <xref:System.Windows.Data.BindingMode> por cada instancia de enlace; para obtener información detallada, vea [Especificar la dirección del enlace](../../../../docs/framework/wpf/data/how-to-specify-the-direction-of-the-binding.md).  Pero como autor de la propiedad de dependencia, puede hacer la que propiedad utilice el modo de enlace <xref:System.Windows.Data.BindingMode> de forma predeterminada.  Un ejemplo de una propiedad de dependencia existente es <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A?displayProperty=fullName>; el escenario para esta propiedad es que la lógica de establecimiento de <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> y la composición de <xref:System.Windows.Controls.MenuItem> interactúen con el estilo del tema predeterminado.  La lógica de la propiedad <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> utiliza el enlace de datos de forma nativa para mantener el estado de la propiedad de acuerdo con otras propiedades de estado y llamadas a métodos.  Otra propiedad de ejemplo que enlaza <xref:System.Windows.Data.BindingMode> de forma predeterminada es <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=fullName>.  
  
-   También puede habilitar la herencia de propiedades en una propiedad de dependencia personalizada estableciendo el marcador <xref:System.Windows.FrameworkPropertyMetadataOptions>.  La herencia de propiedades resulta de gran utilidad en escenarios donde los elementos primarios y secundarios tienen una propiedad en común, y tiene sentido que el valor de propiedad para los elementos secundarios esté establecido en el mismo valor que para los elementos primarios.  Un ejemplo de propiedad heredable es <xref:System.Windows.FrameworkElement.DataContext%2A>, que se utiliza para que las operaciones de enlace habiliten el escenario de detalles principales que resulta tan importante para la presentación de datos.  Haciendo que <xref:System.Windows.FrameworkElement.DataContext%2A> pueda heredarse, cualquier elemento secundario también heredará ese contexto de datos.  Debido a la herencia de valores de propiedad, puede especificar un contexto de datos en la raíz de la página o aplicación y no necesita volver a especificarlo para los enlaces de todos los elementos secundarios posibles.  <xref:System.Windows.FrameworkElement.DataContext%2A> también es un buen ejemplo para ilustrar que la herencia reemplaza el valor predeterminado, pero siempre puede establecerse localmente en cualquier elemento secundario determinado; para obtener información detallada, vea [Usar el patrón principal\-detalle con datos jerárquicos](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).  La herencia del valor de propiedad supone un posible costo de rendimiento y, por lo tanto, debe utilizarse con moderación; para obtener información detallada, vea [Herencia de valores de propiedad](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
-   Establezca el marcador <xref:System.Windows.FrameworkPropertyMetadataOptions> para indicar si los servicios d el diario de navegación deben detectar o utilizar su propiedad.  Un ejemplo es la propiedad <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>; todos los elementos seleccionados en un control de selección deben mantenerse cuando se navega por el historial del diario.  
  
<a name="RODP"></a>   
## Propiedades de dependencia de sólo lectura  
 Puede definir una propiedad de dependencia que sea de sólo lectura.  No obstante, los escenarios para los que debe definirse una propiedad de sólo lectura son algo distintos, así como el procedimiento utilizado para registrarlos con el sistema de propiedades y exponer el identificador.  Para obtener más información, consulte [Propiedades de dependencia de sólo lectura](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md).  
  
<a name="CTDP"></a>   
## Propiedades de dependencia de tipo de colección  
 Las propiedades de dependencia de tipo colección plantean algunos problemas de implementación adicionales que hay tener en cuenta.  Para obtener información detallada, vea [Propiedades de dependencia de tipo de colección](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md).  
  
<a name="SecurityC"></a>   
## Consideraciones de seguridad de las propiedades de dependencia  
 Las propiedades de dependencia deben declararse como propiedades públicas.  Los campos de identificador de las propiedades de dependencia deben declararse como campos estáticos públicos.  Aunque intente declarar otros niveles de acceso \(como protegido\), siempre se puede obtener acceso a una propiedad de dependencia a través del identificador en combinación con las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] del sistema de propiedades.  Es posible incluso obtener acceso a un campo de identificador protegido debido a las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] de determinación de valores o de notificación de metadatos que forman parte del sistema de propiedades, como <xref:System.Windows.LocalValueEnumerator>.  Para obtener más información, consulte [Seguridad de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-security.md).  
  
<a name="DPCtor"></a>   
## Propiedades de dependencia y constructores de clases  
 Existe un principio general en programación de código administrado \(que suelen aplicar las herramientas de análisis del código como FxCop\) según el cual los constructores de clases no deben llamar a métodos virtuales.  Esto se debe a que es posible llamar a constructores como inicialización base de un constructor de clases derivadas, y podría entrarse en el método virtual a través del constructor en un estado de inicialización incompleto de la instancia del objeto que se está construyendo.  Al derivar de cualquier clase que ya se deriva de <xref:System.Windows.DependencyObject>, debe ser consciente de que el propio sistema de propiedades llama y expone internamente los métodos virtuales.  Estos métodos virtuales forman parte de los servicios del sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Al invalidar los métodos se permite que las clases derivadas participen en la determinación de valores.  Para evitar posibles problemas con la inicialización en tiempo de ejecución, no debe establecer los valores de propiedad de dependencia dentro de los constructores de clases, a menos que siga un modelo de constructor muy concreto.  Para obtener información detallada, vea [Modelos de constructores seguros para objetos DependencyObject](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md).  
  
## Vea también  
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Metadatos de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)   
 [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md)   
 [Propiedades de dependencia de tipo de colección](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md)   
 [Seguridad de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-security.md)   
 [Carga de XAML y propiedades de dependencia](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md)   
 [Modelos de constructores seguros para objetos DependencyObject](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md)