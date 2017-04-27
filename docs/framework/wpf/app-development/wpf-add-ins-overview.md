---
title: "Informaci&#243;n general sobre los complementos de WPF | Microsoft Docs"
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
  - "modelo de complementos de .NET Framework [WPF]"
  - "complementos [WPF], arquitectura"
  - "complementos [WPF], ventajas"
  - "complementos [WPF], limitaciones"
  - "complementos [WPF], rendimiento"
  - "complementos [WPF], interfaz de usuario"
  - "complementos y la interfaz de usuario [WPF]"
  - "complementos y aplicaciones de explorador XAML [WPF]"
  - "información general sobre complementos [WPF]"
ms.assetid: 00b4c776-29a8-4dba-b603-280a0cdc2ade
caps.latest.revision: 36
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 35
---
# Informaci&#243;n general sobre los complementos de WPF
<a name="Introduction"></a> [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] incluye un modelo de complementos que los desarrolladores pueden utilizar para crear aplicaciones que admitan la extensibilidad de los complementos.  Este modelo de complementos permite la creación de complementos que se integran con la funcionalidad de la aplicación y la extienden.  En algunos escenarios, las aplicaciones también necesitan mostrar las [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] proporcionadas por los complementos.  En este tema se muestra cómo [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aumenta el modelo de complementos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para permitir estos escenarios, la arquitectura subyacente, sus ventajas y sus limitaciones.  
  
   
  
<a name="Requirements"></a>   
## Requisitos previos  
 Es necesario conocer el modelo de complementos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  Para obtener más información, vea [Complementos y extensibilidad](../../../../ml/index.xml).  
  
<a name="AddInsOverview"></a>   
## Información general sobre los complementos  
 Para evitar las complejidades que implican las acciones de compilar e implementar de nuevo una aplicación para que incorpore nuevas funcionalidades, las aplicaciones implementan mecanismos de extensibilidad que permiten a los desarrolladores \(tanto propios como de otros fabricantes\) crear otras aplicaciones que se integren con ellas.  La manera más común de admitir este tipo de extensibilidad es mediante el uso de complementos.  Algunos ejemplos de aplicaciones reales que exponen la extensibilidad con complementos son los siguientes:  
  
-   Complementos de Internet Explorer.  
  
-   Complementos del Reproductor de Windows Media.  
  
-   Complementos de Visual Studio.  
  
 Por ejemplo, el modelo de complementos del Reproductor de Windows Media permite a los desarrolladores de otros fabricantes implementar complementos que extienden el Reproductor de Windows Media de diversas maneras, entre las que están la creación de descodificadores y codificadores para los formatos multimedia que el Reproductor de Windows Media no admite de forma nativa \(por ejemplo, DVD y MP3\), efectos de audio y máscaras.  Cada modelo de complementos se ha compilado de modo que exponga la funcionalidad que es única de una aplicación, aunque hay varias entidades y comportamientos que son comunes a todos los modelos de complementos.  
  
 Las tres entidades principales de las típicas soluciones de extensibilidad mediante complementos son los *contratos*, los *complementos* y las *aplicaciones host*.  Los contratos definen cómo se integran los complementos con las aplicaciones host de dos maneras:  
  
-   Los complementos se integran con la funcionalidad que implementan las aplicaciones host.  
  
-   Las aplicaciones host exponen la funcionalidad para los complementos con los que se integran.  
  
 Para poder utilizar complementos, las aplicaciones host deben encontrarlos y cargarlos en tiempo de ejecución.  Por consiguiente, las aplicaciones que admiten complementos tienen las siguientes responsabilidades adicionales:  
  
-   **Detección**: búsqueda de complementos que se adhieran a los contratos admitidos por las aplicaciones host.  
  
-   **Activación**: carga, ejecución y establecimiento de la comunicación con los complementos.  
  
-   **Aislamiento**: uso de dominios de aplicación o procesos para establecer límites de aislamiento que protejan las aplicaciones frente a posibles problemas de seguridad y ejecución con los complementos.  
  
-   **Comunicación**: los complementos y las aplicaciones host deben poder comunicarse entre sí más allá de los límites de aislamiento llamando a métodos y pasando datos.  
  
-   **Administración de la duración**: carga y descarga de los dominios de aplicación y procesos de una manera limpia y predecible \(vea [Dominios de aplicación](../../../../docs/framework/app-domains/application-domains.md)\).  
  
-   **Control de versiones**: garantía de que las aplicaciones host y los complementos puedan continuar comunicándose cuando se creen nuevas versiones de cualquiera de ellos.  
  
 En última instancia, el desarrollo de un modelo de complementos robusto no es una tarea trivial.  Por esta razón, [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporciona una infraestructura para compilar modelos de complementos.  
  
> [!NOTE]
>  Para obtener información más detallada sobre los complementos, vea [Complementos y extensibilidad](../../../../ml/index.xml).  
  
<a name="NETFrameworkAddInModelOverview"></a>   
## Información general sobre el modelo de complementos de .NET Framework  
 El modelo de complementos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], que se encuentra en el espacio de nombres <xref:System.AddIn>, contiene un conjunto de tipos que permiten simplificar el desarrollo de la extensibilidad mediante complementos.  La unidad fundamental del modelo de complementos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] es el *contrato*, que define cómo se comunican entre sí una aplicación host y un complemento.  Un contrato se expone a una aplicación host utilizando una *vista* del contrato que es específica de la aplicación host.  De manera similar, se expone al complemento una *vista* del contrato que es específica del complemento.  Se utiliza un *adaptador* para que una aplicación host y un complemento puedan comunicarse entre sus respectivas vistas del contrato.  Los contratos, las vistas y los adaptadores se conocen como segmentos y un conjunto de segmentos relacionados constituye una *canalización*.  Las canalizaciones son la base para que el modelo de complementos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] admita la detección, la activación, el aislamiento de seguridad, el aislamiento de ejecución \(utilizando tanto dominios de aplicación como procesos\), la comunicación, la administración de la duración y el control de versiones.  
  
 La suma de estas compatibilidades permite a los desarrolladores generar complementos que se integran con la funcionalidad de una aplicación host.  Sin embargo, algunos escenarios requieren que las aplicaciones host muestren las [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] proporcionadas por los complementos.  Dado que cada tecnología de presentación de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] tiene su propio modelo para implementar las [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], el modelo de complementos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] no es compatible con ninguna tecnología de presentación en particular.  En su lugar, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extiende el modelo de complementos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] con la compatibilidad de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para los complementos.  
  
<a name="WPFAddInModel"></a>   
## Complementos de WPF  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], junto con el modelo de complementos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], permite manejar una amplia variedad de escenarios que requieren que las aplicaciones host muestren las [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] de los complementos.  En concreto, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] maneja estos escenarios con estos dos modelos de programación:  
  
1.  **El complemento devuelve una interfaz de usuario**.  Un complemento devuelve una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a la aplicación host mediante una llamada de método, que se define en el contrato.  Este escenario se utiliza en los casos siguientes:  
  
    -   La apariencia de una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] devuelta por un complemento depende de los datos o condiciones que solamente existen en tiempo de ejecución, como informes generados dinámicamente.  
  
    -   La [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para los servicios proporcionados por un complemento difiere de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de las aplicaciones host que pueden usar el complemento.  
  
    -   El complemento realiza principalmente un servicio para la aplicación host e informa de su estado a la aplicación host mediante una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
2.  **El complemento es una interfaz de usuario**.  Un complemento es una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], tal como lo define el contrato.  Este escenario se utiliza en los casos siguientes:  
  
    -   Un complemento no proporciona más servicios que el de mostrarse, como un anuncio.  
  
    -   La [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para los servicios proporcionados por un complemento es común a todas las aplicaciones host que pueden utilizar ese complemento, como una calculadora o un selector de color.  
  
 Estos escenarios requieren que se puedan pasar los objetos de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] entre la aplicación host y los dominios de aplicación del complemento.  Puesto que el modelo de complementos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] se basa en la comunicación remota para establecer la comunicación entre los dominios de aplicación, los objetos que se pasen entre ellos deberán poder usarse de forma remota.  
  
 Un objeto utilizable de forma remota es una instancia de una clase que cumple una o varias de las siguientes condiciones:  
  
-   Deriva de la clase <xref:System.MarshalByRefObject>.  
  
-   Implementa la interfaz <xref:System.Runtime.Serialization.ISerializable>.  
  
-   Tiene aplicado el atributo <xref:System.SerializableAttribute>.  
  
> [!NOTE]
>  Para obtener más información sobre la creación de objetos utilizables de forma remota de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], vea [Making Objects Remotable](http://msdn.microsoft.com/es-es/01197253-3f13-43b7-894d-9683e431192a).  
  
 Los tipos de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] no se pueden usar de forma remota.  Para resolver el problema, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extiende el modelo de complementos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para permitir que la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] creada por complementos se muestre desde las aplicaciones host.  Esta compatibilidad la proporciona [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] mediante dos tipos: la interfaz <xref:System.AddIn.Contract.INativeHandleContract> y dos métodos estáticos que se implementan mediante la clase <xref:System.AddIn.Pipeline.FrameworkElementAdapters>: <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> y <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  A alto nivel, estos tipos y métodos se utilizan de la manera siguiente:  
  
1.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] requiere que las [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] proporcionadas por complementos sean clases que se deriven, directa o indirectamente, de <xref:System.Windows.FrameworkElement>, como formas, controles, controles de usuario, paneles de diseño y páginas.  
  
2.  Siempre que el contrato declare que se pasará una interfaz de usuario entre el complemento y la aplicación host, ésta debe declararse como una interfaz <xref:System.AddIn.Contract.INativeHandleContract> \(en lugar de un objeto <xref:System.Windows.FrameworkElement>\);<xref:System.AddIn.Contract.INativeHandleContract> es una representación utilizable de forma remota de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del complemento que se puede pasar más allá de los límites de aislamiento.  
  
3.  Antes de que pase desde el dominio de aplicación del complemento, un objeto <xref:System.Windows.FrameworkElement> se empaqueta como una interfaz <xref:System.AddIn.Contract.INativeHandleContract> llamando a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  
  
4.  Después de pasar al dominio de aplicación de la aplicación host, la interfaz <xref:System.AddIn.Contract.INativeHandleContract> debe volver a empaquetarse como un objeto <xref:System.Windows.FrameworkElement> llamando a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.  
  
 Cómo se utilicen <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> y <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> depende del escenario en cuestión.  En las secciones siguientes se proporciona información detallada para cada modelo de programación.  
  
<a name="ReturnUIFromAddInContract"></a>   
## El complemento devuelve una interfaz de usuario  
 Para que un complemento devuelva una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a una aplicación host, se requiere lo siguiente:  
  
1.  La aplicación host, el complemento y la canalización deben crearse de acuerdo con la documentación de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] [Complementos y extensibilidad](../../../../ml/index.xml).  
  
2.  El contrato debe implementar <xref:System.AddIn.Contract.IContract> y, para devolver una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], el contrato debe declarar un método que devuelva un valor de tipo <xref:System.AddIn.Contract.INativeHandleContract>.  
  
3.  La [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que se pasa entre el complemento y la aplicación host debe derivarse, directa o indirectamente, de <xref:System.Windows.FrameworkElement>.  
  
4.  La [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que el complemento devuelve debe convertirse de un objeto <xref:System.Windows.FrameworkElement> en una interfaz <xref:System.AddIn.Contract.INativeHandleContract> antes de cruzar el límite de aislamiento.  
  
5.  La [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que se devuelve debe convertirse de una interfaz <xref:System.AddIn.Contract.INativeHandleContract> en un objeto <xref:System.Windows.FrameworkElement> después de cruzar el límite de aislamiento.  
  
6.  La aplicación host muestra el objeto <xref:System.Windows.FrameworkElement> devuelto.  
  
 Para obtener un ejemplo que muestra cómo implementar un complemento que devuelve una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], vea [Crear un complemento que devuelva una interfaz de usuario](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md).  
  
<a name="AddInIsAUI"></a>   
## El complemento es una interfaz de usuario  
 Cuando un complemento es una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], se requiere lo siguiente:  
  
1.  La aplicación host, el complemento y la canalización deben crearse de acuerdo con la documentación de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] [Complementos y extensibilidad](../../../../ml/index.xml).  
  
2.  La interfaz de contrato para el complemento debe implementar <xref:System.AddIn.Contract.INativeHandleContract>.  
  
3.  El complemento que se pasa a la aplicación host debe derivar, directa o indirectamente, de <xref:System.Windows.FrameworkElement>.  
  
4.  El complemento se debe convertir de un objeto <xref:System.Windows.FrameworkElement> en una interfaz <xref:System.AddIn.Contract.INativeHandleContract> antes de cruzar el límite de aislamiento.  
  
5.  El complemento se debe convertir de una interfaz <xref:System.AddIn.Contract.INativeHandleContract> en un objeto <xref:System.Windows.FrameworkElement> después de cruzar el límite de aislamiento.  
  
6.  La aplicación host muestra el objeto <xref:System.Windows.FrameworkElement> devuelto.  
  
 Para obtener un ejemplo en el que se muestra cómo implementar un complemento que es una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], vea [Crear un complemento que sea una interfaz de usuario](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-is-a-ui.md).  
  
<a name="ReturningMultipleUIsFromAnAddIn"></a>   
## Devolver varias interfaces de usuario de un complemento  
 Los complementos proporcionan a menudo varias [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] para mostrar aplicaciones host.  Por ejemplo, considere un complemento que sea una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que además proporciona información de estado a la aplicación host, también como una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  Un complemento de este tipo se puede implementar mediante una combinación de técnicas de los modelos [El complemento devuelve una interfaz de usuario](#ReturnUIFromAddInContract) y [El complemento es una interfaz de usuario](#AddInIsAUI).  
  
<a name="AddInsAndXBAPs"></a>   
## Complementos y aplicaciones de explorador XAML  
 Hasta ahora, en los ejemplos, la aplicación host era una aplicación independiente instalada.  Sin embargo, las [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] también pueden hospedar complementos, aunque con los siguientes requisitos adicionales de compilación e implementación:  
  
-   El manifiesto de aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] se debe configurar especialmente para descargar la canalización \(carpetas y ensamblados\) y el ensamblado de complemento en la memoria caché de aplicación de [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] del equipo cliente, en la misma carpeta que la aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
-   El código de la aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] para detectar y cargar los complementos debe usar la memoria caché de aplicación de [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] para la aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] como ubicación de la canalización y del complemento.  
  
-   La aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] debe cargar el complemento en un contexto de seguridad especial si el complemento hace referencia a archivos separados que están ubicados en el sitio de origen; cuando se hospedan en [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], los complementos solamente pueden hacer referencia a archivos separados que se encuentran en el sitio de origen de la aplicación host.  
  
 Estas tareas se describen detalladamente en las siguientes subsecciones.  
  
### Configurar la canalización y el complemento para la implementación de ClickOnce  
 Las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] se descargan y se ejecutan en una carpeta segura en la memoria caché de implementación de [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)].  Para que una aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] pueda hospedar un complemento, la canalización y el ensamblado de complemento también se deben descargar en la carpeta segura.  Para ello, se debe configurar el manifiesto de aplicación de modo que incluya tanto la canalización como el ensamblado de complemento para la descarga.  Esto se hace fácilmente en [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], aunque la canalización y el ensamblado de complemento deben estar en la carpeta raíz del proyecto de la aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] host para que [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] detecte los ensamblados de canalización.  
  
 Por consiguiente, el primer paso es compilar la canalización y el ensamblado de complemento en la raíz del proyecto de la aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] estableciendo la salida de la compilación de cada ensamblado de canalización y proyecto de ensamblado de complemento.  En la tabla siguiente, se muestran las rutas de acceso de la salida de la compilación para los proyectos de ensamblado de canalización y el proyecto de ensamblado de complemento que están en la misma solución y en la misma carpeta raíz que el proyecto de la aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] host.  
  
 Tabla 1: rutas de acceso de los resultados de compilación para los ensamblados de canalización hospedados por una XBAP  
  
|Proyecto de ensamblado de canalización|Ruta de acceso de salida de la compilación|  
|--------------------------------------------|------------------------------------------------|  
|Contrato|`..  \HostXBAP\Contracts\`|  
|Vista de complemento|`..  \HostXBAP\AddInViews\`|  
|Adaptador de conversión|`..  \HostXBAP\AddInSideAdapters\`|  
|Adaptador del host|`..  \HostXBAP\HostSideAdapters\`|  
|Complemento|`..  \HostXBAP\AddIns\WPFAddIn1`|  
  
 El paso siguiente es especificar los ensamblados de canalización y el ensamblado de complemento como archivos de contenido de las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] en [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]; para ello, siga este procedimiento:  
  
1.  Incluya el ensamblado de canalización y el ensamblado de complemento en el proyecto haciendo clic con el botón secundario del mouse en cada carpeta de canalización del Explorador de soluciones y, a continuación, elija **Incluir en el proyecto**.  
  
2.  Establezca el valor de **Acción de compilación** de cada ensamblado de canalización y ensamblado de complemento en **Contenido** en la ventana **Propiedades**.  
  
 El paso final es configurar el manifiesto de aplicación de modo que incluya los archivos de ensamblado de canalización y el archivo de ensamblado de complemento para la descarga.  Los archivos deben ubicarse en carpetas en la raíz de la carpeta de la memoria caché de [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] que la aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] ocupa.  La configuración se puede realizar en [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] siguiendo este procedimiento:  
  
1.  Haga clic con el botón secundario del mouse en el proyecto [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], haga clic en **Propiedades**, haga clic en **Publicar** y, a continuación, haga clic en el botón **Archivos de aplicación**.  
  
2.  En el cuadro de diálogo **Archivos de aplicación**, establezca el valor de **Estado de la publicación** de cada DLL de canalización y de complemento en **Incluir \(automático\)** y establezca el valor de **Grupo de descarga** para cada DLL de canalización y de complemento en **\(Requerido\)**.  
  
### Utilizar la canalización y el complemento de la base de la aplicación  
 Cuando la canalización y el complemento se configuran para la implementación de [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)], se descargan en la misma carpeta de la memoria caché de [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] que la aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  Para utilizar la canalización y el complemento de la aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], el código de la aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] debe obtenerlos de la base de la aplicación.  Los diversos tipos y miembros del modelo de complementos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para el uso de canalizaciones y complementos proporcionan una compatibilidad especial para este escenario.  En primer lugar, se identifica la ruta de acceso mediante el valor de enumeración <xref:System.AddIn.Hosting.PipelineStoreLocation>.  Este valor se utiliza con sobrecargas de los miembros pertinentes del complemento para el uso de canalizaciones que incluyan lo siguiente:  
  
-   <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=fullName>  
  
-   [AddInStore.FindAddIns\(Type, PipelineStoreLocation, String\<xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%2CSystem.String%5B%5D%29?displayProperty=fullName>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Rebuild%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=fullName>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Update%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=fullName>  
  
### Obtener acceso al sitio de origen del host  
 Para asegurarse de que un complemento pueda hacer referencia a los archivos del sitio de origen, el complemento debe cargarse con aislamiento de seguridad equivalente a la aplicación host.  Este nivel de seguridad se identifica mediante el valor de enumeración <xref:System.AddIn.Hosting.AddInSecurityLevel?displayProperty=fullName> y se pasa al método <xref:System.AddIn.Hosting.AddInToken.Activate%2A> cuando se activa un complemento.  
  
<a name="WPFAddInModelArchitecture"></a>   
## Arquitectura de complementos de WPF  
 En el nivel más alto, tal y como hemos visto, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] permite a los complementos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] implementar [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] \(que se derivan, directa o indirectamente, de <xref:System.Windows.FrameworkElement>\) mediante los métodos <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> y <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.  El resultado es que a la aplicación host se le devuelve un objeto <xref:System.Windows.FrameworkElement> que se muestra en la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de la aplicación host.  
  
 Para los escenarios simples de complementos de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], esta es toda la información que necesita el desarrollador.  Para los escenarios más complejos, en particular aquéllos en los que se intenten utilizar servicios adicionales de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] como el diseño, los recursos y el enlace de datos, se requieren conocimientos más detallados de cómo [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extiende el modelo de complementos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] con compatibilidad de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para entender sus ventajas y limitaciones.  
  
 Fundamentalmente, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] no pasa una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de un complemento a una aplicación host; [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] pasa el identificador de ventana Win32 para la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] utilizando la interoperabilidad de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Como tal, cuando se pasa una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de un complemento a una aplicación host, ocurre lo siguiente:  
  
-   En el lado del complemento, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] adquiere un identificador de ventana para la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que la aplicación host mostrará.  El identificador de ventana está encapsulado por una clase interna de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] que se deriva de <xref:System.Windows.Interop.HwndSource> e implementa <xref:System.AddIn.Contract.INativeHandleContract>.  <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> devuelve una instancia de esta clase y se calculan sus referencias desde el dominio de aplicación del complemento al dominio de aplicación de la aplicación host.  
  
-   En el lado de la aplicación host, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] reempaqueta <xref:System.Windows.Interop.HwndSource> como una clase interna de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] que se deriva de <xref:System.Windows.Interop.HwndHost> y consume <xref:System.AddIn.Contract.INativeHandleContract>.  <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> devuelve una instancia de esta clase a la aplicación host.  
  
 <xref:System.Windows.Interop.HwndHost> existe para mostrar las [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], identificadas por identificadores de ventana, desde las [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Para obtener más información, vea [Interoperabilidad de WPF y Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).  
  
 En resumen, <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> y <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> existen para permitir que el identificador de ventana de una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] pase de un complemento a una aplicación host, donde es encapsulado por <xref:System.Windows.Interop.HwndHost> y muestra la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de la aplicación.  
  
> [!NOTE]
>  Dado que la aplicación host obtiene una clase <xref:System.Windows.Interop.HwndHost>, no puede convertir el objeto devuelto por <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> en el tipo implementado por el complemento \(por ejemplo, un control <xref:System.Windows.Controls.UserControl>\).  
  
 Debido a su naturaleza, la clase <xref:System.Windows.Interop.HwndHost> tiene ciertas limitaciones que afectan al modo en que las aplicaciones host la usan.  Sin embargo, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extiende <xref:System.Windows.Interop.HwndHost> con varias funciones para los escenarios de complementos.  Estas ventajas y limitaciones se describen a continuación.  
  
<a name="WPFAddInModelBenefits"></a>   
## Ventajas de los complementos de WPF  
 Dado que las [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] de los complementos de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se muestran en las aplicaciones host utilizando una clase interna que deriva de <xref:System.Windows.Interop.HwndHost>, esas [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] están restringidas por las funciones de <xref:System.Windows.Interop.HwndHost> respecto a los servicios de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], como el diseño, la presentación, el enlace de datos, los estilos, las plantillas y los recursos.  Sin embargo, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aumenta su subclase <xref:System.Windows.Interop.HwndHost> interna con funciones adicionales que incluyen las siguientes:  
  
-   Tabulación entre la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de una aplicación host y la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de un complemento.  Observe que el modelo de programación "El complemento es una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]" requiere que el adaptador de conversión invalide <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> para permitir la tabulación, independientemente de si el complemento es de plena confianza o de confianza parcial.  
  
-   Cumplimiento de los requisitos de accesibilidad para las [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] de los complementos que se muestran desde las [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] de la aplicación host.  
  
-   Posibilidad de que las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se ejecuten de forma segura en varios escenarios de dominio de aplicación.  
  
-   Prevención del acceso ilegal a los identificadores de ventana de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de los complementos cuando éstos se ejecutan con aislamiento de seguridad \(es decir, un recinto de seguridad de confianza parcial\).  Al llamar a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, se garantiza esta seguridad:  
  
    -   Para el modelo de programación "El complemento devuelve una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]", la única manera de pasar el identificador de ventana para una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de complemento más allá del límite de aislamiento es llamar a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  
  
    -   Para el modelo de programación "El complemento es una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]", es preciso invalidar <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> en el adaptador de conversión y llamar a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> \(tal como se muestra en los ejemplos anteriores\), así como llamar a la implementación de `QueryContract` del adaptador de conversión desde el adaptador del host.  
  
-   Provisión de protección de ejecución en varios dominios de aplicación.  Debido a las limitaciones con los dominios de aplicación, las excepciones no controladas que se producen en los dominios de aplicación del complemento hacen que se bloquee la aplicación completa, aunque exista el límite de aislamiento.  Sin embargo, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] y el modelo de complementos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporcionan una manera simple de evitar este problema y mejorar la estabilidad de la aplicación.  Un complemento de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] que muestre una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] crea un objeto <xref:System.Windows.Threading.Dispatcher> para el subproceso en el que se ejecuta el dominio de aplicación si la aplicación host es una aplicación de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Para detectar todas las excepciones no controladas que se produzcan en el dominio de aplicación, controle el evento <xref:System.Windows.Threading.Dispatcher.UnhandledException> del objeto <xref:System.Windows.Threading.Dispatcher> del complemento de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Puede obtener el objeto <xref:System.Windows.Threading.Dispatcher> mediante la propiedad <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A>.  
  
<a name="WPFAddInModelLimitations"></a>   
## Limitaciones de los complementos de WPF  
 Más allá de las ventajas que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] agrega a los comportamientos predeterminados que <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> y los identificadores de ventana proporcionan, también hay limitaciones para las [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] de complementos que se muestran desde aplicaciones host:  
  
-   Las [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] de complementos que se muestran desde una aplicación host no respetan el comportamiento de recorte de la aplicación host.  
  
-   El concepto de *espacio aéreo* en los escenarios de interoperabilidad también se aplica a los complementos \(vea [Información general sobre áreas de la tecnología](../../../../docs/framework/wpf/advanced/technology-regions-overview.md)\).  
  
-   Los servicios de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de una aplicación host, como la herencia de recursos, el enlace de datos y los comandos, no están disponibles automáticamente para las [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] de los complementos.  Para proporcionar estos servicios al complemento, es preciso actualizar la canalización.  
  
-   Una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de complemento no se puede girar, escalar, sesgar ni transformar de ninguna otra manera \(vea [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)\).  
  
-   El contenido de las [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] de complementos que se presenta mediante operaciones de dibujo desde el espacio de nombres <xref:System.Drawing> puede incluir mezclas alfa.  Sin embargo, tanto la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del complemento como la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de la aplicación host que la contiene deben ser 100% opacas; en otras palabras, la propiedad `Opacity` de ambas interfaces debe estar establecida en 1.  
  
-   Si la propiedad <xref:System.Windows.Window.AllowsTransparency%2A> de una ventana en la aplicación host que contiene una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de complemento está establecida en `true`, el complemento será invisible.  Esto es cierto aunque la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del complemento sea 100% opaca \(es decir, aunque la propiedad `Opacity` tenga el valor 1\).  
  
-   Una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de complemento debe aparecer encima de los demás elementos de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] en la misma ventana de nivel superior.  
  
-   Ninguna parte de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de un complemento puede representarse mediante <xref:System.Windows.Media.VisualBrush>.  En su lugar, el complemento puede tomar una instantánea de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] generada para crear un mapa de bits que se puede pasar a la aplicación host mediante los métodos definidos por el contrato.  
  
-   No es posible reproducir archivos multimedia desde un control <xref:System.Windows.Controls.MediaElement> en una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de complemento.  
  
-   Los eventos del mouse generados para la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del complemento no los recibe ni los provoca la aplicación host, y la propiedad `IsMouseOver` de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de la aplicación host tiene el valor `false`.  
  
-   Cuando el foco se desplaza entre los controles de una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de complemento, la aplicación host no recibe ni provoca los eventos `GotFocus` y `LostFocus`.  
  
-   La parte de una aplicación host que contiene una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de complemento aparece en blanco al imprimirse.  
  
-   Todos los distribuidores \(vea <xref:System.Windows.Threading.Dispatcher>\) creados por la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del complemento se deben cerrar manualmente antes de descargar el complemento propietario si la aplicación host continúa ejecutándose.  El contrato puede implementar métodos que permiten a la aplicación host señalar el complemento antes de que éste se descargue, permitiendo que la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del complemento cierre sus distribuidores.  
  
-   Si una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de complemento es un control <xref:System.Windows.Controls.InkCanvas> o contiene un control <xref:System.Windows.Controls.InkCanvas>, no es posible descargar el complemento.  
  
<a name="PerformanceOptimization"></a>   
## Optimización del rendimiento  
 De forma predeterminada, cuando se utilizan varios dominios de aplicación, los diversos ensamblados de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] requeridos por cada aplicación se cargan en el dominio de esa aplicación.  Como resultado, el tiempo requerido para crear nuevos dominios de aplicación e iniciar aplicaciones en ellos puede afectar al rendimiento.  Sin embargo, [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporciona un método para reducir los tiempos de inicio indicando a las aplicaciones que compartan los ensamblados en los diversos dominios de aplicación si ya están cargados.  Para ello, utilice el atributo <xref:System.LoaderOptimizationAttribute>, que debe aplicarse al método de punto de entrada \(`Main`\).  En este caso, sólo debe utilizar código para implementar la definición de la aplicación \(vea [Información general sobre la administración de aplicaciones](../../../../docs/framework/wpf/app-development/application-management-overview.md)\).  
  
## Vea también  
 <xref:System.LoaderOptimizationAttribute>   
 [Complementos y extensibilidad](../../../../ml/index.xml)   
 [Dominios de aplicación](../../../../docs/framework/app-domains/application-domains.md)   
 [.NET Framework Remoting Overview](http://msdn.microsoft.com/es-es/eccb1d31-0a22-417a-97fd-f4f1f3aa4462)   
 [Making Objects Remotable](http://msdn.microsoft.com/es-es/01197253-3f13-43b7-894d-9683e431192a)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/app-development/how-to-topics.md)