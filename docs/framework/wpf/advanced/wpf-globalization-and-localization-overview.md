---
title: "Informaci&#243;n general sobre la localizaci&#243;n y globalizaci&#243;n de WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "globalización, acerca de la globalización"
  - "localización, acerca de la localización"
ms.assetid: 56e5a5c8-6c96-4d19-b8e1-a5be1dc564af
caps.latest.revision: 39
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 34
---
# Informaci&#243;n general sobre la localizaci&#243;n y globalizaci&#243;n de WPF
Cuando se limita la disponibilidad de un producto a un solo idioma, se limita la base de clientes potenciales a una fracción de los 6.500 millones de habitantes de nuestro mundo.  Si desea que las aplicaciones alcancen una audiencia global, la localización rentable del producto es una de las formas mejores y más económicas de llegar a más clientes.  
  
 Esta información general presenta la globalización y la localización en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  La globalización es el diseño y desarrollo de aplicaciones que funcionen en diversas ubicaciones.  Por ejemplo, la globalización permite el uso de interfaces de usuario adaptadas y datos regionales a usuarios de diferentes referencias culturales.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ofrece características de diseño globalizadas, entre las que se encuentran el diseño automático, los ensamblados satélite, y los atributos y comentarios adaptados.  
  
 La localización es la traducción de los recursos de una aplicación en versiones locales para las referencias culturales específicas que admite la aplicación.  Cuando cree versiones localizadas en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], utilizará las API del espacio de nombres <xref:System.Windows.Markup.Localizer>. Estas API son la base de la herramienta de línea de comandos [LocBaml Tool Sample](http://go.microsoft.com/fwlink/?LinkID=160016).  Para obtener información sobre cómo compilar y utilizar LocBaml, vea [Localizar una aplicación](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).  
  
   
  
## Procedimientos recomendados para la globalización y localización en WPF  
 Puede aprovechar al máximo la funcionalidad de globalización y localización integrada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] siguiendo las sugerencias relacionadas con el diseño y localización de interfaces de usuario que proporciona esta sección.  
  
### Procedimientos recomendados para el diseño de interfaces de usuario de WPF  
 Cuando diseñe una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] basada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] considere implementar estos procedimientos recomendados:  
  
-   Escriba la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]; evite crear la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] en código.  Cuando cree la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] utilizando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], expóngala a través de API de localización integradas.  
  
-   Evite utilizar posiciones absolutas y tamaños fijos para el diseño de contenido; en su lugar, utilice el ajuste de tamaño relativo o automático.  
  
    -   Utilice <xref:System.Windows.Window.SizeToContent%2A>; mantenga los altos y anchos establecidos en `Auto`.  
  
    -   Evite utilizar <xref:System.Windows.Controls.Canvas> para diseñar la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]s.  
  
    -   Utilice <xref:System.Windows.Controls.Grid> y su característica del uso compartido del tamaño.  
  
-   Proporcione espacio adicional en los márgenes, porque el texto traducido suele requerir más espacio.  El espacio adicional permite que sobresalga algún carácter.  
  
-   Habilite <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> en <xref:System.Windows.Controls.TextBlock> para evitar el recorte.  
  
-   Establezca el atributo **xml:lang**.  Este atributo describe la referencia cultural de un elemento concreto y sus elementos secundarios.  El valor de esta propiedad cambia el comportamiento de varias características de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Por ejemplo, cambia el comportamiento de los guiones, la revisión ortográfica, la sustitución de números, la forma de la escritura compleja y la reserva de fuentes.  Vea [Globalización de WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md) para obtener más información sobre la configuración del [Control de xml:lang en XAML](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md).  
  
-   Cree una fuente compuesta personalizada para controlar mejor las fuentes que se utilizan para los diferentes idiomas.  De forma predeterminada, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]utiliza la fuente de GlobalUserInterface.composite del directorio Windows\\Fonts.  
  
-   Cuando cree aplicaciones de navegación que puedan localizarse en una referencia cultural que presente el texto en formato de derecha a izquierda, establezca explícitamente la propiedad <xref:System.Windows.FlowDirection> de cada una de las páginas para asegurarse de que no hereda <xref:System.Windows.FlowDirection> de <xref:System.Windows.Navigation.NavigationWindow>.  
  
-   Cuando cree aplicaciones de navegación independientes que se hospeden fuera de un explorador, establezca la propiedad <xref:System.Windows.Application.StartupUri%2A> de la aplicación inicial en un objeto <xref:System.Windows.Navigation.NavigationWindow> en lugar de en una página \(por ejemplo, `<Application StartupUri="NavigationWindow.xaml">`\).  Este diseño permite cambiar la propiedad <xref:System.Windows.FlowDirection> de la ventana y la barra de navegación.  Para obtener más información y un ejemplo, vea [Globalization Homepage Sample](http://go.microsoft.com/fwlink/?LinkID=159990).  
  
### Procedimientos recomendados para la localización de WPF  
 Cuando adapte aplicaciones basadas en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], considere implementar estos procedimientos recomendados:  
  
-   Utilice comentarios de localización para proporcionar contexto adicional a los localizadores.  
  
-   Utilice atributos de localización para controlar la localización, en lugar de omitir selectivamente propiedades de <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> en los elementos.  Vea [Atributos y comentarios sobre localización](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md) para obtener más información.  
  
-   Utilice **msbuild \/t:updateuid** y **\/t:checkuid** para agregar y comprobar las propiedades de <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Use las propiedades <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> para realizar un seguimiento de los cambios entre el desarrollo y la localización. Las propiedades <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> le ayudan a adaptar los nuevos cambios de desarrollo.  Si agrega manualmente propiedades de <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> a la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], la tarea será habitualmente tediosa y poco precisa.  
  
    -   No modifique ni cambie las propiedades de <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> después de iniciar la localización.  
  
    -   No utilice propiedades de <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> duplicadas \(recuerde esta sugerencia al utilizar el comando copiar y pegar\).  
  
    -   Establezca la ubicación de `UltimateResourceFallback` en AssemblyInfo.\* para especificar el idioma adecuado para la reserva \(por ejemplo, `[assembly: NeutralResourcesLanguage("en-US",   UltimateResourceFallbackLocation.Satellite)]`\).  
  
         Si decide incluir su idioma de origen en el ensamblado principal omitiendo la etiqueta `<UICulture>` en el archivo de proyecto, establezca la ubicación de `UltimateResourceFallback` como el ensamblado principal en lugar del satélite \(por ejemplo, `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.MainAssembly)]`\).  
  
<a name="workflow_to_localize"></a>   
## Adaptar una aplicación WPF  
 Cuando adapte una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], tiene varias opciones.  Por ejemplo, puede enlazar los recursos adaptables de la aplicación a un archivo [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], almacenar el texto adaptable en tablas resx o hacer que el localizador utilice archivos [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  En esta sección se describe un flujo de trabajo de localización que utiliza el formato BAML de XAML, lo que ofrece varias ventajas:  
  
-   Puede adaptar después de compilar.  
  
-   Puede actualizar a una versión más reciente del formato BAML de XAML con localizaciones de una versión anterior del formato BAML de XAML, de modo que pueda localizar al mismo tiempo que desarrolla.  
  
-   Puede validar los elementos y semánticas de origen originales en tiempo de compilación, porque el formato BAML de XAML es el formato compilado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
### Proceso de compilación de la localización  
 Cuando desarrolle una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], el proceso de compilación para la localización será el siguiente:  
  
-   El programador crea y globaliza la aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  En el archivo de proyecto, el desarrollador establece `<UICulture>en-US</UICulture>` de modo que, cuando se compile la aplicación, se genere un ensamblado principal independiente del idioma. Este ensamblado tiene un archivo satélite .resources.dll que contiene todos los recursos localizables. Opcionalmente, puede mantener el idioma de origen en el ensamblado principal, porque nuestras [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] de localización permiten la extracción desde el ensamblado principal.  
  
-   Cuando se compila el archivo, el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se convierte al formato BAML de XAML.  Los archivos `MyDialog.exe` culturalmente neutro y `MyDialog.resources.dll` culturalmente dependiente \(inglés\) se publican para el cliente angloparlante.  
  
### Flujo de trabajo de localización  
 El proceso de la localización comienza una vez compilado el archivo `MyDialog.resources.dll` sin adaptar.  Los elementos y propiedades de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] original se extraen del formato BAML de XAML en forma de pares clave\-valor utilizando las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] bajo <xref:System.Windows.Markup.Localizer>.  Los localizadores utilizan los pares clave\-valor para adaptar la aplicación.  Puede generar un nuevo archivo .resource .dll a partir de los nuevos valores, una vez completada la localización.  
  
 Las claves de los pares clave\-valor son valores `x:Uid` que coloca el desarrollador en el código [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] original.  Estos valores `x:Uid` permiten que la [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] realice un seguimiento de los cambios y combine aquellos que se producen entre el desarrollador y el localizador durante la localización.  Por ejemplo, si el programador cambia la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] después de que el localizador empiece a adaptar, puede combinar el cambio de desarrollo con el trabajo de la localización ya completado, de modo que el trabajo de traducción que se pierda sea mínimo.  
  
 En el gráfico siguiente se muestra un flujo de trabajo de localización típico basado en el formato BAML de XAML.  En este diagrama se asume que el programador escribe la aplicación en inglés.  El programador crea y globaliza la aplicación WPF.  En el archivo de proyecto, el desarrollador establece `<UICulture>en-US</UICulture>` para que, en la compilación, se genere un ensamblado principal independiente del idioma, con archivos satélite .resources.dll que contienen todos los recursos adaptables.  Como alternativa, puede mantenerse el idioma de origen en el ensamblado principal, porque las API de localización de WPF admiten la extracción desde el ensamblado principal.  Después del proceso de compilación, el XAML se genera en BAML.  El archivo MyDialog.exe.resources.dll culturalmente neutral se distribuye al cliente angloparlante.  
  
 ![Flujo de trabajo de localización](../../../../docs/framework/wpf/advanced/media/localizationworkflow.png "LocalizationWorkflow")  
  
 ![Flujo de trabajo sin localizar](../../../../docs/framework/wpf/advanced/media/localizationworkflow2.png "LocalizationWorkflow2")  
  
<a name="examples_of_localization"></a>   
## Ejemplos de localización de WPF  
 Esta sección contiene ejemplos de aplicaciones adaptadas para ayudarle a entender cómo compilar y adaptar aplicaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
#### Ejemplo de cuadro de diálogo Ejecutar  
 Los gráficos siguientes muestran el resultado del ejemplo del cuadro de diálogo **Ejecutar**.  
  
 **Inglés:**  
  
 ![Cuadro de diálogo Run](../../../../docs/framework/wpf/advanced/media/rundialogenglish.png "RunDialogEnglish")  
  
 **Alemán:**  
  
 ![Cuadro de diálogo German Run](../../../../docs/framework/wpf/advanced/media/rundialoggerman.png "RunDialogGerman")  
  
 **Diseñar un cuadro de diálogo Ejecutar global**  
  
 En este ejemplo se genera un cuadro de diálogo **Ejecutar** utilizando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Este cuadro de diálogo es equivalente al cuadro de diálogo **Ejecutar** que está disponible en el menú Inicio de [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)].  
  
 Algunos puntos importantes para la creación de cuadros de diálogo globales son los siguientes:  
  
 **Automatic Layout**  
  
 *En Window1.xaml:*  
  
 `<Window SizeToContent="WidthAndHeight">`  
  
 La propiedad Window anterior cambia automáticamente el tamaño de la ventana en función del tamaño del contenido.  Esta propiedad evita que la ventana recorte el contenido que aumente de tamaño después de la localización; también quita el espacio innecesario cuando el contenido disminuye de tamaño después de la localización.  
  
 `<Grid x:Uid="Grid_1">`  
  
 Se necesitan propiedades <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> para que las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] de localización de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funcionen correctamente.  
  
 La [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] de localización de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] las usa para realizar un seguimiento de los cambios entre el desarrollo y la localización de la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  Las propiedades <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> le permiten combinar una versión más reciente de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con una localización anterior de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  Para agregar una propiedad <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>, ejecute **msbuild \/t:updateuid RunDialog.csproj** en un shell de comandos.  Éste es el método recomendado para agregar propiedades de <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>, porque agregarlas manualmente suele exigir mucho tiempo y es menos preciso.  Para comprobar que las propiedades de <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> están correctamente establecidas, ejecute **msbuild \/t:checkuid RunDialog.csproj**.  
  
 La [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se estructura utilizando el control <xref:System.Windows.Controls.Grid>, que es un control útil para aprovechar el diseño automático de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Observe que el cuadro de diálogo se divide en tres filas y cinco columnas.  Ninguna de las definiciones de columna y fila tiene un tamaño fijo; por lo tanto, los elementos de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que se colocan en cada celda pueden adaptarse a aumentos y reducciones de tamaño durante la localización.  
  
 [!code-xml[GlobalizationRunDialog#GridColumnDef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef)]  
  
 Las primeras dos columnas donde se colocan la etiqueta **Abrir:** y el control <xref:System.Windows.Controls.ComboBox> utilizan el 10 por ciento del ancho total de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 [!code-xml[GlobalizationRunDialog#GridColumnDef2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef2)]  
  
 Tenga en cuenta que el ejemplo utiliza la característica de tamaño compartido de <xref:System.Windows.Controls.Grid>.  Las últimas tres columnas la aprovechan colocándose en el mismo <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A>.  Como cabe esperar del nombre de la propiedad, esto permite que las columnas compartan el mismo tamaño.  Así, cuando se adapta "Browse..." a la cadena "Durchsuchen...", más larga, todos los botones crecen en ancho en lugar de obtenerse un botón "OK" pequeño y un botón "Durchsuchen" desproporcionadamente grande.  
  
 **Xml:lang**  
  
 `Xml:lang="en-US"`  
  
 Observe el [Control de xml:lang en XAML](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md) colocado en el elemento raíz de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  Esta propiedad describe la referencia cultural de un elemento determinado y de sus elementos secundarios.  Este valor lo utilizan varias características de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y debe cambiarse en consecuencia durante la localización.  Este valor cambia qué diccionario de idioma se utiliza para separar las palabras con guiones y para la revisión ortográfica.  También afecta a la presentación de dígitos y a cómo selecciona el sistema de reserva de fuentes qué fuente utilizar.  Finalmente, la propiedad afecta a la manera en que se muestran los números y la manera en que se da forma a los textos escritos de escritura compleja.  El valor predeterminado es "en\-US".  
  
 **Building a Satellite Resource Assembly**  
  
 *En .csproj:*  
  
 `<UICulture>en-US</UICulture>`  
  
 Observe la adición de un valor `UICulture`.  Cuando se establece en un valor <xref:System.Globalization.CultureInfo> válido tal como en\-US, al compilar el proyecto se genera un ensamblado satélite que contiene todos los recursos adaptables.  
  
 `<Resource Include="RunIcon.JPG">`  
  
 `<Localizable>False</Localizable>`  
  
 `</Resource>`  
  
 No es necesario adaptar `RunIcon.JPG`, porque debe aparecer igual para todas las referencias culturales.  `Localizable` se establece en `false`, para que permanezca en el ensamblado principal neutral respecto al idioma en lugar de en el ensamblado satélite.  El valor predeterminado de todos los recursos no compilables es `Localizable` establecido en `true`.  
  
 **Adaptar el cuadro de diálogo Ejecutar**  
  
 **Parse**  
  
 Después de compilar la aplicación, el primer paso para adaptarla es analizar los recursos adaptables del ensamblado satélite.  Para los propósitos de este tema, utilice la herramienta de ejemplo LocBaml, que encontrará en [LocBaml Tool Sample](http://go.microsoft.com/fwlink/?LinkID=160016).  Tenga en cuenta que LocBaml es solamente una herramienta de ejemplo, cuyo propósito es ayudarle a iniciarse en la compilación de una herramienta de localización adecuada para el proceso de localización.  Con LocBaml, ejecute lo siguiente para analizar: **LocBaml \/parse RunDialog.resources.dll \/out:** y generar un archivo "RunDialog.resources.dll.CSV".  
  
 **Localize**  
  
 Utilice su editor favorito de archivos .CSV compatible con Unicode para modificar este archivo.  Filtre para ocultar todas las entradas que tengan la categoría de localización "None".  Debería ver las entradas siguientes:  
  
||||  
|-|-|-|  
|Resource key|Localization Category|Valor|  
|Button\_1:System.Windows.Controls.Button.$Content|Button|OK|  
|Button\_2:System.Windows.Controls.Button.$Content|Button|Cancelar|  
|Button\_3:System.Windows.Controls.Button.$Content|Button|Browse...|  
|ComboBox\_1:System.Windows.Controls.ComboBox.$Content|ComboBox||  
|TextBlock\_1:System.Windows.Controls.TextBlock.$Content|Text|Type the name of a program, folder, document, or Internet resource, and Windows will open it for you.|  
|TextBlock\_2:System.Windows.Controls.TextBlock.$Content|Text|Open:|  
|Window\_1:System.Windows.Window.Title|Título|Run|  
  
 Adaptar la aplicación a alemán requerirá las traducciones siguientes:  
  
||||  
|-|-|-|  
|Resource key|Localization Category|Valor|  
|Button\_1:System.Windows.Controls.Button.$Content|Button|OK|  
|Button\_2:System.Windows.Controls.Button.$Content|Button|Abbrechen|  
|Button\_3:System.Windows.Controls.Button.$Content|Button|Durchsuchen…|  
|ComboBox\_1:System.Windows.Controls.ComboBox.$Content|ComboBox||  
|TextBlock\_1:System.Windows.Controls.TextBlock.$Content|Text|Geben Sie den Namen eines Programms, Ordners, Dokuments oder einer Internetresource an.|  
|TextBlock\_2:System.Windows.Controls.TextBlock.$Content|Text|Öffnen:|  
|Window\_1:System.Windows.Window.Title|Título|Run|  
  
 **Generate**  
  
 El último paso de localización implica la creación del nuevo ensamblado satélite adaptado.  Esto se puede hacer con el siguiente comando de LocBaml:  
  
 **LocBaml.exe \/generate RunDialog.resources.dll \/trans:RunDialog.resources.dll.CSV \/out: .  \/cul:de\-DE**  
  
 En la versión alemana de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], si se coloca resources.dll se coloca en una carpeta de\-DE junto al ensamblado principal, este recurso se cargará automáticamente en lugar del de la carpeta en\-US.  Si no tiene una versión alemana de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] para probarlo, establezca la referencia cultural en la referencia cultural de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] que esté utilizando \(por ejemplo,  en\-US\) y reemplace el archivo resources.dll original.  
  
 **Satellite Resource Loading**  
  
|MyDialog.exe|en\-US\\MyDialog.resources.dll|de\-DE\\MyDialog.resources.dll|  
|------------------|------------------------------------|------------------------------------|  
|Código|BAML en inglés original|BAML adaptado|  
|Recursos culturalmente neutrales|Otros recursos en inglés|Otros recursos adaptados al alemán|  
  
 .NET Framework elige automáticamente el ensamblado de recursos satélite que debe cargar en función de la propiedad `Thread.CurrentThread.CurrentUICulture` de la aplicación.  Esto tiene como valor predeterminado la referencia cultural de su SO [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  Por lo tanto, si está usando la versión alemana de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], se cargará de\-DE\\MyDialog.resources.dll, si está utilizando la versión en inglés de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], se cargará en US\\MyDialog.resources.dll.  Puede establecer el recurso de reserva último para la aplicación especificando NeutralResourcesLanguage en AssemblyInfo.\* del proyecto.  Por ejemplo, si especifica:  
  
 `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.Satellite)]`  
  
 se utilizará en\-US\\MyDialog.resources.dll con la versión alemana de Windows si no están disponibles de\-DE\\MyDialog.resources.dll ni de\\MyDialog.resources.dll.  
  
### Página principal de Microsoft Arabia Saudí  
 Los gráficos siguientes muestran una página principal en inglés y en árabe.  Para ver el ejemplo completo que genera estos gráficos, vea [Globalization Homepage Sample](http://go.microsoft.com/fwlink/?LinkID=159990).  
  
 **Inglés:**  
  
 ![Página en inglés](../../../../docs/framework/wpf/advanced/media/englishhomepage.png "EnglishHomepage")  
  
 **Árabe:**  
  
 ![Página árabe](../../../../docs/framework/wpf/advanced/media/arabichomepage.png "ArabicHomepage")  
  
### Diseñar una página principal de Microsoft global  
 Este ejemplo de sitio web de Microsoft Arabia Saudí muestra las características de globalización que se proporcionan para los idiomas RightToLeft.  Los idiomas como el hebreo y el árabe se leen de derecha a izquierda, así que el diseño de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] suele ser muy diferente del que sería en idiomas de izquierda a derecha como el inglés.  Adaptar de un idioma de izquierda a derecha a uno de derecha a izquierda, o viceversa, puede ser todo un reto.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se ha diseñado de modo que tales adaptaciones resulten mucho más fáciles.  
  
 **FlowDirection**  
  
 *Homepage.xaml:*  
  
 [!code-xml[GlobalizationHomepage#Homepage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#homepage)]  
  
 Observe la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> en el control <xref:System.Windows.Controls.Page>.  Al cambiar esta propiedad a <xref:System.Windows.FlowDirection>, se cambiará la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> del control <xref:System.Windows.Controls.Page> y de sus elementos secundarios, de modo que el diseño de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se invierte para que se lea de derecha a izquierda, como esperaría un usuario árabe.  Se puede invalidar el comportamiento de herencia especificando un valor explícito para la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> de cualquier elemento.  La propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> está disponible en cualquier objeto <xref:System.Windows.FrameworkElement> o elemento relacionado con documentos y tiene un valor implícito de <xref:System.Windows.FlowDirection>.  
  
 Observe que incluso los pinceles de degradado de fondo se invierten correctamente al cambiar la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> raíz:  
  
 **FlowDirection\="LeftToRight"**  
  
 ![Flujo de izquierda a derecha](../../../../docs/framework/wpf/advanced/media/lefttoright.png "LeftToRight")  
  
 **FlowDirection\="RightToLeft"**  
  
 ![Flujo de derecha a izquierda](../../../../docs/framework/wpf/advanced/media/righttoleft.png "RightToLeft")  
  
 **Evite utilizar dimensiones fijas para paneles y controles**  
  
 Eche una mirada a Homepage.xaml; observe que, aparte del ancho y el alto fijos especificados para toda la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] completa en el control <xref:System.Windows.Controls.DockPanel> superior, no hay ninguna otra dimensión fija.  Evite utilizar dimensiones fijas, para impedir que se recorte el texto adaptado que sea más largo que el texto de origen.  Los paneles y controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ajustarán automáticamente su tamaño en función de su contenido.  La mayoría de los controles tienen también dimensiones máximas y mínimas que puede establecer para mejorar el control \(por ejemplo,  MinWidth\= "20"\).  Con <xref:System.Windows.Controls.Grid>, puede establecer también anchos y altos relativos utilizando '\*' \(por ejemplo,  Width\= "0,25\*"\) o utilizar la característica de uso compartido del tamaño de celda.  
  
 **Comentarios de localización**  
  
 En muchos casos, el contenido puede ser ambiguo y difícil de traducir.  El programador o el diseñador tiene la capacidad de proporcionar contexto y comentarios adicionales a los localizadores mediante comentarios de localización.  El ejemplo de Localization.Comments que aparece a continuación clarifica el uso del carácter " &#124; ".  
  
 [!code-xml[GlobalizationHomepage#LocalizationComment](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcomment)]  
  
 Este comentario se asocia con el contenido de TextBlock\_1 y, en el caso de la herramienta LocBaml, \(vea [Localizar una aplicación](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)\) se puede ver en la sexta columna de la fila de TextBlock\_1 en el archivo .csv resultante:  
  
|||||||  
|-|-|-|-|-|-|  
|Resource key|Categoría|Readable|Modifiable|Comment|Valor|  
|TextBlock\_1:System.Windows.Controls.TextBlock.$Content|Text|TRUE|TRUE|Este carácter se utiliza como una regla decorativa.|&#124;|  
  
 Se puede colocar comentarios en el contenido o en las propiedades de cualquier elemento utilizando la sintaxis siguiente:  
  
 [!code-xml[GlobalizationHomepage#LocalizationCommentsProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcommentsprop)]  
  
 **Atributos de localización**  
  
 A menudo, el programador o el administrador de la localización necesita controlar lo que pueden leer y modificar los localizadores.  Por ejemplo, quizá no desee que el localizador traduzca el nombre de su compañía o la redacción legal.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona atributos que permiten establecer la legibilidad, modificabilidad y categoría del contenido o las propiedades de un elemento; la herramienta de localización puede utilizar estos atributos para bloquear, ocultar u ordenar elementos.  Para obtener más información, vea <xref:System.Windows.Localization.Attributes%2A>.  Para este ejemplo, la herramienta LocBaml genera solamente los valores de estos atributos.  Todos los controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tienen valores predeterminados para estos atributos, pero es posible invalidarlos.  Por ejemplo, en el ejemplo siguiente se invalidan los atributos de localización predeterminados para `TextBlock_1` y se establece que el contenido sea legible pero no modificable para los localizadores.  
  
 [!code-xml[LocalizationComAtt#LocalizationAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributes)]  
  
 Además de los atributos que facilitan la lectura y las modificaciones, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una enumeración de categorías comunes de la interfaz de usuario \(<xref:System.Windows.LocalizationCategory>\) que se pueden usar para dar más contexto a los localizadores.  Las categorías predeterminadas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para los controles de plataforma también se pueden invalidar en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:  
  
 [!code-xml[LocalizationComAtt#LocalizationAttributesOverridden](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributesoverridden)]  
  
 Los atributos de localización predeterminados que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona también se pueden invalidar mediante código, de modo que se puedan establecer correctamente los valores predeterminados de los controles personalizados.  Por ejemplo:  
  
 `[Localizability(Readability = Readability.Readable, Modifiability=Modifiability.Unmodifiable, LocalizationCategory.None)]`  
  
 `public class CorporateLogo: TextBlock`  
  
 `{`  
  
 `…`  
  
 `..`  
  
 `.`  
  
 `}`  
  
 Los atributos establecidos por instancia en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] tendrá precedencia sobre los valores establecidos en el código sobre los controles personalizados.  Para obtener más información sobre los atributos y los comentarios, vea [Atributos y comentarios sobre localización](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md).  
  
 **Reserva de fuente y fuentes compuestas**  
  
 Si especifica una fuente que no admita un intervalo de punto de codificación determinado, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] recurrirá automáticamente a una que lo haga utilizando Global User Interface.compositefont, que se encuentra en el directorio Windows\\Fonts.  Las fuentes compuestas funcionan como cualquier otra fuente y se pueden utilizar explícitamente estableciendo la propiedad FontFamily de un elemento \(por ejemplo,  FontFamily\= "Global User Interface"\).  Puede especificar sus propias preferencia de reserva de fuentes creando fuentes compuestas propias y especificando qué fuente desea utilizar para intervalos de punto de codificación e idiomas concretos.  
  
 Para obtener más información sobre fuentes compuestas, vea <xref:System.Windows.Media.FontFamily>.  
  
 **Adaptar la página principal de Microsoft**  
  
 Puede seguir los mismos pasos que en el ejemplo del cuadro de diálogo Ejecutar para adaptar esta aplicación.  El archivo .csv adaptado para árabe está a su disposición en [Globalization Homepage Sample](http://go.microsoft.com/fwlink/?LinkID=159990).