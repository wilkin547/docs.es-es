---
title: Información general sobre globalización y localización
ms.date: 03/30/2017
helpviewer_keywords:
- globalization [WPF], about globalization
- localization [WPF], about localization
ms.assetid: 56e5a5c8-6c96-4d19-b8e1-a5be1dc564af
ms.openlocfilehash: 665daa14b543a357b17747a7d9d34dac2224711d
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124564"
---
# <a name="wpf-globalization-and-localization-overview"></a>Información general sobre la globalización y la localización de WPF

Al limitar la disponibilidad de un producto a un solo idioma, limitará la base de clientes potencial a una fracción de la población 7,5 mil millones de nuestro mundo. Si quiere que las aplicaciones alcancen una audiencia global, la localización rentable del producto es una de las formas mejores y más económicas de llegar a más clientes.

Esta información general presenta la globalización y la localización en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. La globalización es el diseño y desarrollo de aplicaciones que funcionan en diversas ubicaciones. Por ejemplo, la globalización permite el uso de interfaces de usuario localizadas y datos regionales para usuarios de diferentes referencias culturales. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona características de diseño globalizadas, incluidos el diseño automático, los ensamblados satélite y los atributos y los comentarios localizados.

La localización es la traducción de los recursos de una aplicación en versiones localizadas para las referencias culturales específicas que admite la aplicación. Cuando se localiza en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], se usan las API del espacio de nombres <xref:System.Windows.Markup.Localizer>. Estas API potencian la herramienta de línea de comandos de ejemplo de la [herramienta LocBaml](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml) . Para obtener información sobre cómo compilar y usar LocBaml, vea [localizar una aplicación](how-to-localize-an-application.md).

## <a name="best-practices-for-globalization-and-localization-in-wpf"></a>Procedimientos recomendados para la globalización y localización en WPF

Puede aprovechar al máximo la funcionalidad de globalización y localización que se integra en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] siguiendo las sugerencias relacionadas con el diseño de la interfaz de usuario y la localización que proporciona esta sección.

### <a name="best-practices-for-wpf-ui-design"></a>Procedimientos recomendados para el diseño de interfaces de usuario de WPF

Al diseñar un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]basado en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], considere la posibilidad de implementar estas prácticas recomendadas:

- Escriba el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; Evite la creación de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] en el código. Al crear el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], lo expone a través de las API de localización integradas.

- Evite usar posiciones absolutas y tamaños fijos para diseñar el contenido; en su lugar, utilice el ajuste de tamaño relativo o automático.

  - Use <xref:System.Windows.Window.SizeToContent%2A> y mantenga el ancho y el alto establecidos en `Auto`.

  - Evite el uso de <xref:System.Windows.Controls.Canvas> para diseñar [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]s.

  - Use <xref:System.Windows.Controls.Grid> y su característica de uso compartido de tamaño.

- Proporcione espacio adicional en los márgenes, porque el texto localizado suele requerir más espacio. El espacio adicional permite que sobresalga algún carácter.

- Habilite <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> en <xref:System.Windows.Controls.TextBlock> para evitar el recorte.

- Defina el atributo `xml:lang` . Este atributo describe la referencia cultural de un elemento específico y sus elementos secundarios. El valor de esta propiedad cambia el comportamiento de varias características de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Por ejemplo, cambia el comportamiento de los guiones, la revisión ortográfica, la sustitución de números, la forma de la escritura compleja y la reserva de fuentes. Vea [globalización de WPF](globalization-for-wpf.md) para obtener más información sobre cómo establecer el [control de XML: lang en XAML](../../../desktop-wpf/xaml-services/xml-language-handling.md).

- Cree una fuente compuesta personalizada para obtener un mejor control de las fuentes que se usan para distintos idiomas. De forma predeterminada, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa la fuente GlobalUserInterface. composite en el directorio Windows\fonts.

- Cuando cree aplicaciones de navegación que se puedan localizar en una referencia cultural que presente texto en un formato de derecha a izquierda, establezca explícitamente el <xref:System.Windows.FlowDirection> de cada página para asegurarse de que la página no hereda <xref:System.Windows.FlowDirection> de la <xref:System.Windows.Navigation.NavigationWindow>.

- Al crear aplicaciones de navegación independientes que se hospedan fuera de un explorador, establezca el <xref:System.Windows.Application.StartupUri%2A> de la aplicación inicial en un <xref:System.Windows.Navigation.NavigationWindow> en lugar de en una página (por ejemplo, `<Application StartupUri="NavigationWindow.xaml">`). Este diseño permite cambiar el <xref:System.Windows.FlowDirection> de la ventana y la barra de navegación. Para obtener más información y un ejemplo, vea ejemplo de la [Página principal de globalización](https://github.com/microsoft/WPF-Samples/tree/master/Globalization%20and%20Localization/GlobalizationHomepage).

### <a name="best-practices-for-wpf-localization"></a>Procedimientos recomendados para la localización de WPF

Al localizar aplicaciones basadas en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], considere la posibilidad de implementar estas prácticas recomendadas:

- Use los comentarios de localización para proporcionar contexto adicional a los localizadores.

- Utilice los atributos de localización para controlar la localización en lugar de omitir selectivamente <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> propiedades en los elementos. Vea [atributos y comentarios de localización](localization-attributes-and-comments.md) para obtener más información.

- Use `msbuild -t:updateuid` y `-t:checkuid` para agregar y comprobar las propiedades de <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Use <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> propiedades para realizar el seguimiento de los cambios entre el desarrollo y la localización. <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> propiedades le ayudan a localizar los nuevos cambios de desarrollo. Si agrega manualmente <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> propiedades a un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], la tarea suele ser tediosa y menos precisa.

  - No edite ni cambie <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> propiedades después de comenzar la localización.

  - No use propiedades de <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> duplicadas (recuerde esta sugerencia al usar el comando de copiar y pegar).

  - Establezca la ubicación `UltimateResourceFallback` en AssemblyInfo.\* para especificar el idioma adecuado para la reserva (por ejemplo, `[assembly: NeutralResourcesLanguage("en-US",   UltimateResourceFallbackLocation.Satellite)]`).

    Si decide incluir el idioma de origen en el ensamblado principal omitiendo la `<UICulture>` etiqueta en el archivo de proyecto, establezca la ubicación de `UltimateResourceFallback` como el ensamblado principal en lugar del satélite (por ejemplo, `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.MainAssembly)]`).

## <a name="localize-a-wpf-application"></a>Localizar una aplicación WPF

Al localizar una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], tiene varias opciones. Por ejemplo, puede enlazar los recursos localizables de la aplicación a un archivo XML, almacenar texto localizable en tablas resx o hacer que el localizador use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivos. En esta sección se describe un flujo de trabajo de localización que usa el formato BAML de XAML, que ofrece varias ventajas:

- Puede localizarlo después de compilar.

- Puede actualizar a una versión más reciente del formulario BAML de XAML con localizaciones de una versión anterior del formulario BAML de XAML para que pueda localizar al mismo tiempo que desarrolla.

- Puede validar los elementos de origen y la semántica originales en tiempo de compilación porque la forma BAML de XAML es la forma compilada de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

### <a name="localization-build-process"></a>Proceso de compilación de la localización

Al desarrollar una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], el proceso de compilación para la localización es el siguiente:

- El desarrollador crea y globaliza la aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. En el archivo de proyecto, el desarrollador establece `<UICulture>en-US</UICulture>` de modo que, cuando se compila la aplicación, se genera un ensamblado principal independiente del idioma. Este ensamblado tiene un archivo satélite .resources.dll que contiene todos los recursos localizables. Opcionalmente, puede mantener el idioma de origen en el ensamblado principal porque nuestras API de localización admiten la extracción del ensamblado principal.

- Cuando el archivo se compila en la compilación, el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se convierte al formato BAML de XAML. Los archivos de `MyDialog.resources.dll` culturalmente neutros `MyDialog.exe` y culturalmente dependiente (Inglés) se publican en el cliente en inglés.

### <a name="localization-workflow"></a>Flujo de trabajo de localización

El proceso de localización comienza después de compilar el archivo de `MyDialog.resources.dll` no localizado. Los elementos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] y las propiedades del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] original se extraen del formulario BAML de XAML en pares de clave-valor mediante las API de <xref:System.Windows.Markup.Localizer>. Los localizadores usan los pares clave-valor para localizar la aplicación. Puede generar un nuevo archivo .resource.dll a partir de los nuevos valores, una vez completada la localización.

Las claves de los pares clave-valor son `x:Uid` valores que el desarrollador coloca en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]original. Estos valores `x:Uid` permiten a la API realizar un seguimiento de los cambios que se producen entre el desarrollador y el localizador durante la localización. Por ejemplo, si el desarrollador cambia el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] después de que el localizador empiece a localizarse, puede combinar el cambio de desarrollo con el trabajo de localización ya completado para que se pierda el trabajo de traducción mínimo.

En el gráfico siguiente se muestra un flujo de trabajo de localización típico basado en el formato BAML de XAML. En este diagrama se supone que el desarrollador escribe la aplicación en inglés. El desarrollador crea y globaliza la aplicación WPF. En el archivo de proyecto, el desarrollador establece `<UICulture>en-US</UICulture>` de modo que, al compilar, se genere un ensamblado principal independiente del lenguaje con un archivo. Resources. dll satélite que contenga todos los recursos localizables. De manera alternativa, puede mantenerse el idioma de origen en el ensamblado principal porque las API de localización de WPF admiten la extracción desde el ensamblado principal. Después del proceso de compilación, el XAML se genera en BAML. El archivo MyDialog.exe.resources.dll culturalmente neutral se distribuye al cliente angloparlante.

![Diagrama que muestra el flujo de trabajo de localización.](./media/wpf-globalization-and-localization-overview/localization-workflow.png)

![Diagrama que muestra el flujo de trabajo no localizado.](./media/wpf-globalization-and-localization-overview/unlocalized-workflow.png)

## <a name="examples-of-wpf-localization"></a>Ejemplos de localización de WPF

Esta sección contiene ejemplos de aplicaciones localizadas que le ayudarán a entender cómo compilar y localizar aplicaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

### <a name="run-dialog-box-example"></a>Ejemplo de cuadro de diálogo Ejecutar

En los gráficos siguientes se muestra el resultado del ejemplo de cuadro de diálogo **Ejecutar** .

**Inglés:**

![Captura de pantalla que muestra un cuadro de diálogo de ejecución en inglés.](./media/wpf-globalization-and-localization-overview/run-dialog-box-english.png)

**Alemán:**

![Captura de pantalla que muestra un cuadro de diálogo de ejecución en alemán.](./media/wpf-globalization-and-localization-overview/run-dialog-box-german.png)

**Diseñar un cuadro de diálogo Ejecutar global**

En este ejemplo se genera un cuadro de diálogo de **ejecución** mediante [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Este cuadro de diálogo es equivalente al cuadro de diálogo **Ejecutar** que está disponible en el menú Inicio de Microsoft Windows.

Algunos puntos importantes para la creación de cuadros de diálogo globales son los siguientes:

**Diseño automático**

*En Window1.xaml:*

`<Window SizeToContent="WidthAndHeight">`

La propiedad Window anterior cambia automáticamente el tamaño de la ventana en función del tamaño del contenido. Esta propiedad evita que la ventana recorte el contenido que aumenta de tamaño después de la localización; también quita el espacio innecesario cuando el contenido disminuye de tamaño después de la localización.

`<Grid x:Uid="Grid_1">`

<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> propiedades son necesarias para que las API de localización de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funcionen correctamente.

Los usan las API de localización de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para realizar el seguimiento de los cambios entre el desarrollo y la localización de la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> propiedades le permiten combinar una versión más reciente del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con una localización anterior de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Para agregar una propiedad <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>, ejecute `msbuild -t:updateuid RunDialog.csproj` en un shell de comandos. Este es el método recomendado para agregar propiedades <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> porque la adición manual suele ser lenta y menos precisa. Para comprobar que <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> propiedades se han establecido correctamente, ejecute `msbuild -t:checkuid RunDialog.csproj`.

El [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se estructura mediante el control <xref:System.Windows.Controls.Grid>, que es un control útil para aprovechar el diseño automático en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Observe que el cuadro de diálogo se divide en tres filas y cinco columnas. No una de las definiciones de fila y columna tiene un tamaño fijo; por lo tanto, los elementos de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que se colocan en cada celda pueden adaptarse a los aumentos y disminuyen de tamaño durante la localización.

[!code-xaml[GlobalizationRunDialog#GridColumnDef](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef)]

Las dos primeras columnas en las que se colocan la etiqueta **Open:** y <xref:System.Windows.Controls.ComboBox> utilizan el 10 por ciento del ancho total [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].

[!code-xaml[GlobalizationRunDialog#GridColumnDef2](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef2)]

Tenga en cuenta que en el ejemplo se usa la característica de ajuste de tamaño compartido de <xref:System.Windows.Controls.Grid>. Las tres últimas columnas se aprovechan de esto colocando en el mismo <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A>. Como cabe esperar del nombre de la propiedad, esto permite que las columnas compartan el mismo tamaño. Por tanto, cuando la "examinar..." se localiza a la cadena más larga "Durchsuchen...", todos los botones aumentan de ancho en lugar de tener un pequeño botón "Aceptar" y un "Durchsuchen..." de gran tamaño. botón.

**XML: lang**

`xml:lang="en-US"`

Observe el [control XML: lang en XAML](../../../desktop-wpf/xaml-services/xml-language-handling.md) colocado en el elemento raíz del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Esta propiedad describe la referencia cultural de un elemento determinado y de sus elementos secundarios. Este valor se usa en varias características de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y debe cambiarse de forma adecuada durante la localización. Este valor cambia qué diccionario de idioma se usa para separar las palabras con guiones y para la revisión ortográfica. También afecta a la presentación de dígitos y a cómo selecciona el sistema de reserva de fuentes qué fuente usar. Finalmente, la propiedad afecta a la manera en que se muestran los números y la manera en que se aplica formato a los textos escritos de escritura compleja. El valor predeterminado es "en-US".

**Crear un ensamblado de recursos satélite**

*En .csproj:*

Edite el archivo de `.csproj` y agregue la siguiente etiqueta a un `<PropertyGroup>`incondicional:

`<UICulture>en-US</UICulture>`

Observe la adición de un valor de `UICulture`. Cuando se establece en un valor de <xref:System.Globalization.CultureInfo> válido como en-US, al compilar el proyecto se generará un ensamblado satélite con todos los recursos localizables en él.

`<Resource Include="RunIcon.JPG">`

`<Localizable>False</Localizable>`

`</Resource>`

No es necesario localizar el `RunIcon.JPG` porque debe aparecer igual para todas las referencias culturales. `Localizable` se establece en `false` para que permanezca en el ensamblado principal independiente del idioma en lugar del ensamblado satélite. El valor predeterminado de todos los recursos de noncompilable es `Localizable` establecido en `true`.

**Localizar el cuadro de diálogo Ejecutar**

**Analizar**

Después de compilar la aplicación, el primer paso para localizarla es analizar los recursos localizables del ensamblado satélite. Para los fines de este tema, use la herramienta LocBaml de ejemplo que encontrará en el [ejemplo de la herramienta LocBaml](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml). Tenga en cuenta que LocBaml es solamente una herramienta de ejemplo, cuyo propósito es ayudarle a iniciarse en la compilación de una herramienta de localización adecuada para el proceso de localización. Con LocBaml, ejecute lo siguiente para analizar: **LocBaml/Parse runDialog. Resources. dll/out:** para generar un archivo "runDialog. Resources. dll. csv".

**Localizar**

Use su editor favorito de archivos .CSV compatible con Unicode para modificar este archivo. Filtre todas las entradas que tengan la categoría de localización "None". Debería ver las entradas siguientes:

|Clave de recurso|Categoría de localización|Value|
|-|-|-|
|Button_1:System.Windows.Controls.Button.$Content|Botón|Aceptar|
|Button_2:System.Windows.Controls.Button.$Content|Botón|Cancelar|
|Button_3:System.Windows.Controls.Button.$Content|Botón|Examinar...|
|ComboBox_1:System.Windows.Controls.ComboBox.$Content|ComboBox||
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Texto|Escriba el nombre del programa, carpeta, documento o recurso de Internet que desea abrir con Windows.|
|TextBlock_2:System.Windows.Controls.TextBlock.$Content|Texto|Abierta:|
|Window_1:System.Windows.Window.Title|Título|Ejecute|

Localizar la aplicación a alemán requerirá las traducciones siguientes:

|Clave de recurso|Categoría de localización|Value|
|-|-|-|
|Button_1:System.Windows.Controls.Button.$Content|Botón|Aceptar|
|Button_2:System.Windows.Controls.Button.$Content|Botón|Abbrechen|
|Button_3:System.Windows.Controls.Button.$Content|Botón|Durchsuchen…|
|ComboBox_1:System.Windows.Controls.ComboBox.$Content|ComboBox||
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Texto|Geben Sie den Namen eines Programms, Ordners, Dokuments oder einer Internetresource an.|
|TextBlock_2:System.Windows.Controls.TextBlock.$Content|Texto|Abrir:|
|Window_1:System.Windows.Window.Title|Título|Ejecute|

**Generate**

El último paso de localización implica la creación del nuevo ensamblado satélite localizado. Esto se puede hacer con el siguiente comando de LocBaml:

**LocBaml. exe/Generate RunDialog. Resources. dll/trans: RunDialog. Resources. dll. CSV/out:. /CUL: de-DE**

En las ventanas alemanas, si este archivo resources. dll se coloca en una carpeta de-DE situada junto al ensamblado principal, este recurso se cargará automáticamente en lugar de en la carpeta en-US. Si no tiene una versión alemana de Windows para probarlo, establezca la referencia cultural en la referencia cultural de Windows que esté usando (por ejemplo, `en-US`) y reemplace el archivo DLL de recursos original.

**Carga de recursos satélite**

|MyDialog.exe|en-US\MyDialog.resources.dll|de-DE\MyDialog.resources.dll|
|------------------|------------------------------------|------------------------------------|
|Código|BAML en inglés original|BAML localizado|
|Recursos culturalmente neutrales|Otros recursos en inglés|Otros recursos localizados al alemán|

.NET Framework elige automáticamente el ensamblado de recursos satélite que se va a cargar en función del `Thread.CurrentThread.CurrentUICulture`de la aplicación. El valor predeterminado es la referencia cultural de su sistema operativo Windows. Por lo tanto, si usa ventanas alemanas, el de-DE\MyDialog.resources.dll se carga, si usa ventanas en inglés, el en-US\MyDialog.resources.dll se carga. Puede establecer el recurso de reserva final de la aplicación especificando el NeutralResourcesLanguage en el AssemblyInfo del proyecto.\*. Por ejemplo, si especifica:

`[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.Satellite)]`

se usará en-US\MyDialog.resources.dll con la versión alemana de Windows si no están disponibles de-DE\MyDialog.resources.dll ni de\MyDialog.resources.dll.

### <a name="microsoft-saudi-arabia-homepage"></a>Página principal de Microsoft Arabia Saudí

En los gráficos siguientes se muestra una página principal en inglés y en árabe. Para obtener el ejemplo completo que genera estos gráficos, vea ejemplo de la [Página principal de globalización](https://github.com/microsoft/WPF-Samples/tree/master/Globalization%20and%20Localization/GlobalizationHomepage).

**Inglés:**

![Captura de pantalla que muestra una página principal en inglés.](./media/wpf-globalization-and-localization-overview/english-home-page-sample.jpg)

**Árabe:**

![Captura de pantalla que muestra una página principal de árabe.](./media/wpf-globalization-and-localization-overview/arabic-home-page-sample.jpg)

### <a name="designing-a-global-microsoft-home-page"></a>Diseño de una página principal de Microsoft global

En este ejemplo de sitio web de Microsoft Arabia Saudí se muestran las características de globalización que se proporcionan para los idiomas de derecha a izquierda. Los idiomas como el hebreo y el árabe tienen un orden de lectura de derecha a izquierda, por lo que el diseño de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se debe diseñar con frecuencia de forma bastante diferente que en los idiomas de izquierda a derecha, como el inglés. Localizar de un idioma de izquierda a derecha a uno de derecha a izquierda, o viceversa, puede ser todo un reto. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se ha diseñado de modo que tales localizaciones resulten mucho más fáciles.

**FlowDirection**

*Homepage.xaml:*

[!code-xaml[GlobalizationHomepage#Homepage](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#homepage)]

Observe la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> en <xref:System.Windows.Controls.Page>. Al cambiar esta propiedad a <xref:System.Windows.FlowDirection.RightToLeft> se cambiará el <xref:System.Windows.FrameworkElement.FlowDirection%2A> de la <xref:System.Windows.Controls.Page> y sus elementos secundarios para que el diseño de este [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se invierta en de derecha a izquierda, como cabría esperar un usuario árabe. Puede invalidar el comportamiento de la herencia especificando una <xref:System.Windows.FrameworkElement.FlowDirection%2A> explícita en cualquier elemento. La propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> está disponible en cualquier elemento relacionado con <xref:System.Windows.FrameworkElement> o documento y tiene un valor implícito de <xref:System.Windows.FlowDirection.LeftToRight>.

Observe que incluso los pinceles de degradado de fondo se voltean correctamente cuando se cambia el <xref:System.Windows.FrameworkElement.FlowDirection%2A> raíz:

**FlowDirection="LeftToRight"**

![Captura de pantalla que muestra el flujo de degradado de izquierda a derecha.](./media/wpf-globalization-and-localization-overview/gradient-flow-left-right.png)

**FlowDirection="RightToLeft"**

![Captura de pantalla que muestra el flujo de degradado de derecha a izquierda.](./media/wpf-globalization-and-localization-overview/gradient-flow-right-left.png)

**Evitar usar dimensiones fijas para paneles y controles**

Eche un vistazo a homepage. XAML, tenga en cuenta que, aparte del ancho y el alto fijos especificados para todo el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] en la parte superior <xref:System.Windows.Controls.DockPanel>, no hay otras dimensiones fijas. Evite usar dimensiones fijas para impedir que se recorte el texto localizado que sea más largo que el texto de origen. Los paneles y controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ajustarán automáticamente su tamaño en función de su contenido. La mayoría de los controles también tienen dimensiones mínima y máxima que se pueden establecer para obtener más control (por ejemplo, MinWidth = "20"). Con <xref:System.Windows.Controls.Grid>, también puede establecer anchos y altos relativos mediante el uso de "\*" (por ejemplo, `Width="0.25*"`) o usar su característica de uso compartido de tamaño de celda.

**Comentarios de localización**

En muchos casos, el contenido puede ser ambiguo y difícil de traducir. El desarrollador o el diseñador tiene la capacidad de proporcionar contexto y comentarios adicionales a los localizadores mediante comentarios de localización. Por ejemplo, la localización. los comentarios siguientes aclaran el uso del carácter&#124;' '.

[!code-xaml[GlobalizationHomepage#LocalizationComment](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcomment)]

Este comentario se asocia con el contenido de TextBlock_1 y, en el caso de la herramienta LocBaml, (vea [localizar una aplicación](how-to-localize-an-application.md)), se puede ver en la sexta columna de la fila de TextBlock_1 en el archivo. csv de salida:

|Clave de recurso|Category|Legible|Modificable|Comentario|Value|
|-|-|-|-|-|-|
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Texto|TRUE|TRUE|Este carácter se usa como una regla decorativa.|&#124;|

Se pueden colocar comentarios en el contenido o en las propiedades de cualquier elemento usando la sintaxis siguiente:

[!code-xaml[GlobalizationHomepage#LocalizationCommentsProp](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcommentsprop)]

**Atributos de localización**

A menudo, el desarrollador o el administrador de la localización necesita controlar lo que pueden leer y modificar los localizadores. Por ejemplo, quizá no quiera que el localizador traduzca el nombre de su compañía o la redacción legal. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona atributos que permiten establecer la legibilidad, la modificabilidad y la categoría del contenido o la propiedad de un elemento que la herramienta de localización puede usar para bloquear, ocultar u ordenar elementos. Para más información, consulte <xref:System.Windows.Localization.Attributes%2A>. Para este ejemplo, la herramienta LocBaml genera solamente los valores de estos atributos. Todos los controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tienen valores predeterminados para estos atributos, pero es posible invalidarlos. Por ejemplo, en el ejemplo siguiente se reemplazan los atributos de localización predeterminados para `TextBlock_1` y se establece que el contenido sea legible pero no modificable para los localizadores.

[!code-xaml[LocalizationComAtt#LocalizationAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributes)]

Además de los atributos de legibilidad y modificabilidad, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una enumeración de categorías comunes de la interfaz de usuario (<xref:System.Windows.LocalizationCategory>) que se pueden usar para proporcionar más contexto a los localizadores. Las [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] categorías predeterminadas para los controles de plataforma se pueden invalidar en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] también:

[!code-xaml[LocalizationComAtt#LocalizationAttributesOverridden](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributesoverridden)]

Los atributos de localización predeterminados que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona también se pueden invalidar a través del código, por lo que puede establecer correctamente los valores predeterminados correctos para los controles personalizados. Por ejemplo:

```csharp
[Localizability(Readability = Readability.Readable, Modifiability=Modifiability.Unmodifiable, LocalizationCategory.None)]
public class CorporateLogo : TextBlock
{
    // ...
}
```

Los atributos por instancia establecidos en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] tendrán prioridad sobre los valores establecidos en el código de los controles personalizados. Para obtener más información sobre los atributos y los comentarios, vea [atributos y comentarios de localización](localization-attributes-and-comments.md).

**Reserva de fuente y fuentes compuestas**

Si especifica una fuente que no admite un intervalo de punto de tipos determinado, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se reservará automáticamente a una que lo hace mediante el uso de la interfaz de usuario global. CompositeFont que se encuentra en el directorio Windows\fonts. Las fuentes compuestas funcionan de la misma forma que cualquier otra fuente y se pueden usar explícitamente estableciendo el `FontFamily` de un elemento (por ejemplo, `FontFamily="Global User Interface"`). Puede especificar sus propias preferencias de reserva de fuentes creando fuentes compuestas propias y especificando qué fuente quiere usar para los intervalos de punto de codificación e idiomas concretos.

Para obtener más información sobre las fuentes compuestas, vea <xref:System.Windows.Media.FontFamily>.

**Localizar la página principal de Microsoft**

Puede seguir los mismos pasos que en el ejemplo del cuadro de diálogo Ejecutar para localizar esta aplicación. El archivo. csv localizado para árabe está disponible en el [ejemplo de página principal de globalización](https://github.com/microsoft/WPF-Samples/tree/master/Globalization%20and%20Localization/GlobalizationHomepage).
