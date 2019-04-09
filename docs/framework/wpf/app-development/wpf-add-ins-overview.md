---
title: Información general sobre los complementos de WPF
ms.date: 03/30/2017
helpviewer_keywords:
- add-ins and XAML browser applications [WPF]
- add-ins overview [WPF]
- add-ins [WPF], performance
- add-ins [WPF], benefits
- .NET Framework add-in model [WPF]
- add-ins [WPF], user interface
- add-ins and the user interface [WPF]
- add-ins [WPF], architecture
- add-ins [WPF], limitations
ms.assetid: 00b4c776-29a8-4dba-b603-280a0cdc2ade
ms.openlocfilehash: 36cfcaca5ae49c87916f6d7c769c878c4321247f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091621"
---
# <a name="wpf-add-ins-overview"></a>Información general sobre los complementos de WPF
<a name="Introduction"></a> .NET Framework incluye un modelo de complemento que los desarrolladores pueden usar para crear aplicaciones que admiten la extensibilidad de complemento. Dicho modelo permite la creación de complementos que se integran con las aplicaciones y amplían su funcionalidad. En algunos escenarios, las aplicaciones también necesitan mostrar interfaces de usuario que se proporcionan los complementos. En este tema se muestra cómo WPF amplía el modelo de complemento de .NET Framework para habilitar estos escenarios, la arquitectura subyacente, sus ventajas y sus limitaciones.  

<a name="Requirements"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Es necesario estar familiarizado con el modelo de complemento de .NET Framework. Para más información, consulte [Complementos y extensibilidad](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).  
  
<a name="AddInsOverview"></a>   
## <a name="add-ins-overview"></a>Información general sobre los complementos  
 Para evitar las complejidades de la recompilación y reimplementación de aplicaciones para incorporar la nueva funcionalidad, estas implementan mecanismos de extensibilidad que permiten a los desarrolladores (tanto propios como de terceros) crear otras aplicaciones que se integran con ellas. La manera más común de admitir este tipo de extensibilidad es mediante el uso de complementos (también conocido como "complementos" y "módulos"). Estos son algunos ejemplos de aplicaciones reales que exponen la extensibilidad con complementos:  
  
-   Complementos de Internet Explorer.  
  
-   Módulos del Reproductor de Windows Media.  
  
-   Complementos de Visual Studio.  
  
 Por ejemplo, el modelo del complemento del Reproductor de Windows Media permite a los desarrolladores de otras empresas implementar "módulos" que extienden el Reproductor de Windows Media de varias formas, entre las que se incluye incluida la creación de descodificadores y codificadores para los formatos multimedia que el Reproductor de Windows Media no admite de forma nativa (por ejemplo, DVD o MP3), efectos de audio y máscaras. Cada modelo del complemento se crea para exponer la funcionalidad que es única para una aplicación, aunque hay varias entidades y comportamientos que son comunes a todos los modelos de complementos.  
  
 Las tres entidades principales de las soluciones de extensibilidad de complemento habituales son los *contratos*, los *complementos* y las *aplicaciones host*. Los contratos definen la forma en que los complementos se integran con las aplicaciones host de dos maneras:  
  
-   Los complementos se integran con la funcionalidad que implementan las aplicaciones host.  
  
-   Las aplicaciones host exponen la funcionalidad para que los complementos se integren con ella.  
  
 Para que se usen los complementos, es preciso que las aplicaciones host los encuentren y los carguen en tiempo de ejecución. En consecuencia, las aplicaciones que admiten complementos tienen las siguientes responsabilidades adicionales:  
  
-   **Detección**: Buscar complementos que se adhieran a los contratos admitidos por las aplicaciones host.  
  
-   **Activación**: Cargar, ejecutar y establecer comunicación con complementos.  
  
-   **Aislamiento**: Uso de dominios de aplicación o procesos para establecer los límites de aislamiento que protejan las aplicaciones de seguridad potencial y problemas de ejecución de complementos.  
  
-   **Comunicación**: Los complementos y aplicaciones host comunicarse entre sí a través de límites de aislamiento llamando a métodos y pasando datos.  
  
-   **Administración de la duración**: Cargar y descargar dominios de aplicación y los procesos de una manera limpia y predecible (consulte [dominios de aplicación](../../app-domains/application-domains.md)).  
  
-   **Control de versiones**: Lo que garantiza que las aplicaciones de host y los complementos puedan comunicarse cuando se crean las nuevas versiones de cualquiera.  
  
 Por último, el desarrollo de un sólido modelo de complemento es una empresa que no es trivial. Por este motivo, .NET Framework proporciona una infraestructura para la creación de modelos de complementos.  
  
> [!NOTE]
>  Para más información acerca de los complementos, consulte [Complementos y extensibilidad](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).  
  
<a name="NETFrameworkAddInModelOverview"></a>   
## <a name="net-framework-add-in-model-overview"></a>Introducción al modelo de complemento de .NET Framework  
 El modelo de complemento de .NET Framework, que se encuentra en la <xref:System.AddIn> espacio de nombres contiene un conjunto de tipos que están diseñadas para simplificar el desarrollo de extensibilidad. La unidad fundamental del modelo de complementos de .NET Framework es la *contrato*, que define cómo una aplicación host y un complemento comunicarse entre sí. Un contrato se expone a una aplicación host mediante una *vista* específica de la aplicación host del contrato. Del mismo modo, se expone una *vista* específica del complemento al complemento. Se usa un *adaptador* para que una aplicación host y un complemento se comuniquen entre sus respectivas vistas del contrato. Los contratos, vistas y adaptadores se conocen como segmentos y un conjunto de segmentos relacionados constituye una *canalización*. Las canalizaciones son la base en el que el modelo de complemento de .NET Framework admite la detección, la activación, aislamiento de seguridad, aislamiento de ejecución (mediante procesos y dominios de aplicación), comunicación, administración de la duración y control de versiones.  
  
 La suma de todo ello permite a los desarrolladores compilar complementos que se integran con la funcionalidad de una aplicación host. Sin embargo, algunos escenarios requieren las aplicaciones host muestren las interfaces de usuario proporcionadas por complementos. Dado que cada tecnología de presentación de .NET Framework tiene su propio modelo de implementación de interfaces de usuario, el modelo de complemento de .NET Framework no admite ninguna tecnología de presentación determinado. En su lugar, WPF amplía el modelo de complemento de .NET Framework con compatibilidad de UI para complementos.  
  
<a name="WPFAddInModel"></a>   
## <a name="wpf-add-ins"></a>Complementos WPF  
 WPF, junto con el modelo de complemento de .NET Framework, le permite abordar una amplia variedad de escenarios que requieren las aplicaciones host muestren las interfaces de usuario de complementos. En concreto, estos escenarios se tratan por WPF con los dos modelos de programación siguientes:  
  
1.  **El complemento devuelve una interfaz de usuario**. Un complemento devuelve una interfaz de usuario a la aplicación host mediante una llamada de método, tal como se define el contrato. Este escenario se utiliza en los casos siguientes:  
  
    -   La apariencia de una interfaz de usuario devuelto por un complemento es dependiente de datos o condiciones que existen en tiempo de ejecución, como dinámicamente los informes generan.  
  
    -   La interfaz de usuario para los servicios proporcionados por un complemento difiere de la interfaz de usuario de las aplicaciones de host que puede usar el complemento.  
  
    -   El complemento principalmente realiza un servicio para la aplicación host y notifica el estado a la aplicación host con una interfaz de usuario.  
  
2.  **El complemento es una interfaz de usuario**. Un complemento es una interfaz de usuario, como se define en el contrato. Este escenario se utiliza en los casos siguientes:  
  
    -   Los complementos solo muestran los servicios que se muestran, como un anuncio.  
  
    -   La interfaz de usuario para los servicios proporcionados por un complemento es común a todas las aplicaciones host que pueden usar ese complemento, como una calculadora o un selector de colores.  
  
 Estos escenarios requieren que se pueden pasar objetos de interfaz de usuario entre la aplicación host y los dominios de aplicación del complemento. Desde el modelo de complementos se basa en la comunicación remota entre dominios de aplicación de .NET Framework, los objetos que se pasan entre ellos deben ser utilizables de forma remota.  
  
 Un objeto que se puede usar de forma remota es una instancia de una clase que realiza una o varias de las siguientes acciones:  
  
-   Deriva el <xref:System.MarshalByRefObject> clase.  
  
-   Implementa la interfaz <xref:System.Runtime.Serialization.ISerializable>.  
  
-   Tiene la <xref:System.SerializableAttribute> atributo aplicado.  
  
> [!NOTE]
>  Para obtener más información acerca de la creación de objetos de .NET Framework utilizable de forma remota, consulte [utilizable de forma remota los objetos que hace](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/wcf3swha(v=vs.100)).  
  
 Los tipos de UI de WPF no son utilizables de forma remota. Para solucionar el problema, WPF amplía el modelo de complemento de .NET Framework para habilitar la UI de WPF crea los complementos que se muestran desde las aplicaciones host. Esta compatibilidad se proporciona por WPF en dos tipos: el <xref:System.AddIn.Contract.INativeHandleContract> interfaz y dos métodos estáticos implementados por el <xref:System.AddIn.Pipeline.FrameworkElementAdapters> clase: <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> y <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>. A un nivel alto, estos tipos y métodos se utilizan como se indica a continuación:  
  
1.  WPF requiere que las interfaces de usuario proporcionadas por complementos sean clases que derivan directa o indirectamente de <xref:System.Windows.FrameworkElement>, como formas, controles, controles de usuario, paneles de diseño y las páginas.  
  
2.  Siempre que el contrato declare que se pasará una interfaz de usuario entre el complemento y la aplicación host, debe declararse como un <xref:System.AddIn.Contract.INativeHandleContract> (no un <xref:System.Windows.FrameworkElement>); <xref:System.AddIn.Contract.INativeHandleContract> es una representación utilizable de forma remota de la IU del complemento que se puede pasar entre los límites de aislamiento.  
  
3.  Antes de que se pasa desde dominio de aplicación del complemento, un <xref:System.Windows.FrameworkElement> se empaqueta como un <xref:System.AddIn.Contract.INativeHandleContract> mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  
  
4.  Después de que se pasa al dominio de aplicación de la aplicación host, el <xref:System.AddIn.Contract.INativeHandleContract> se debe volver a empaquetar como un <xref:System.Windows.FrameworkElement> mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.  
  
 Cómo <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, y <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> se usan depende del escenario específico. En las siguientes secciones se proporciona información acerca de cada modelo de programación.  
  
<a name="ReturnUIFromAddInContract"></a>   
## <a name="add-in-returns-a-user-interface"></a>El complemento devuelve una interfaz de usuario  
 Para que un complemento devolver una interfaz de usuario a una aplicación host, se requiere lo siguiente:  
  
1.  La aplicación host y la canalización deben crearse, como se describe en .NET Framework [complementos y extensibilidad](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)) documentación.  
  
2.  El contrato debe implementar <xref:System.AddIn.Contract.IContract> y, para devolver una interfaz de usuario, el contrato debe declarar un método con un valor devuelto de tipo <xref:System.AddIn.Contract.INativeHandleContract>.  
  
3.  La interfaz de usuario que se pasa entre el complemento y la aplicación host debe derivar directa o indirectamente de <xref:System.Windows.FrameworkElement>.  
  
4.  La interfaz de usuario devuelto por el complemento se debe convertir de un <xref:System.Windows.FrameworkElement> a un <xref:System.AddIn.Contract.INativeHandleContract> antes de cruzar el límite de aislamiento.  
  
5.  La interfaz de usuario devuelto debe convertirse de un <xref:System.AddIn.Contract.INativeHandleContract> a un <xref:System.Windows.FrameworkElement> después de cruzar el límite de aislamiento.  
  
6.  La aplicación host muestra el valor devuelto <xref:System.Windows.FrameworkElement>.  
  
 Para obtener un ejemplo que muestra cómo implementar un complemento que devuelva una interfaz de usuario, consulte [crear un complemento que devuelva una interfaz de usuario](how-to-create-an-add-in-that-returns-a-ui.md).  
  
<a name="AddInIsAUI"></a>   
## <a name="add-in-is-a-user-interface"></a>El complemento es una interfaz de usuario  
 Cuando un complemento es una interfaz de usuario, se requiere lo siguiente:  
  
1.  La aplicación host y la canalización deben crearse, como se describe en .NET Framework [complementos y extensibilidad](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)) documentación.  
  
2.  Debe implementar la interfaz de contrato para el complemento <xref:System.AddIn.Contract.INativeHandleContract>.  
  
3.  El complemento que se pasa a la aplicación host debe derivar directa o indirectamente de <xref:System.Windows.FrameworkElement>.  
  
4.  El complemento se debe convertir de un <xref:System.Windows.FrameworkElement> a un <xref:System.AddIn.Contract.INativeHandleContract> antes de cruzar el límite de aislamiento.  
  
5.  El complemento se debe convertir de un <xref:System.AddIn.Contract.INativeHandleContract> a un <xref:System.Windows.FrameworkElement> después de cruzar el límite de aislamiento.  
  
6.  La aplicación host muestra el valor devuelto <xref:System.Windows.FrameworkElement>.  
  
 Para obtener un ejemplo que muestra cómo implementar un complemento es una interfaz de usuario, consulte [crear un complemento, que es una interfaz de usuario](how-to-create-an-add-in-that-is-a-ui.md).  
  
<a name="ReturningMultipleUIsFromAnAddIn"></a>   
## <a name="returning-multiple-uis-from-an-add-in"></a>Devolución de varias interfaces de usuario desde un complemento  
 Complementos a menudo proporcionan varias interfaces de usuario para las aplicaciones host muestren. Por ejemplo, considere un complemento que es una interfaz de usuario que también proporciona información de estado a la aplicación host, también como una interfaz de usuario. Un complemento como este se puede implementar mediante una combinación de técnicas de los modelos de [El complemento devuelve una interfaz de usuario](#ReturnUIFromAddInContract) y [El complemento es una interfaz de usuario](#AddInIsAUI).  
  
<a name="AddInsAndXBAPs"></a>   
## <a name="add-ins-and-xaml-browser-applications"></a>Complementos y aplicaciones del explorador XAML  
 Hasta ahora, en los ejemplos, la aplicación host ha sido una aplicación independiente instalada. Pero [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] también pueden hospedar complementos, aunque con los siguientes requisitos adicionales de compilación e implementación:  
  
-   El manifiesto de aplicación de [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] se debe configurar especialmente para descargar la canalización (carpetas y ensamblados) y el ensamblado del complemento a la caché de la aplicación [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] en el equipo cliente, en la misma carpeta que la [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
-   Para detectar y cargar complementos, el código de la [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] debe usar la caché de la aplicación [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] para la [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] como ubicación de la canalización y del complemento.  
  
-   La [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] debe cargar el complemento en un contexto de seguridad especial si el complemento hace referencia a archivos dinámicos que se encuentran en el sitio de origen; cuando los hospedan [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], los complementos solo pueden hacer referencia a los archivos dinámico que se encuentran en el sitio de origen de la aplicación host.  
  
 Estas tareas se describen con detalle en las subsecciones siguientes.  
  
### <a name="configuring-the-pipeline-and-add-in-for-clickonce-deployment"></a>Configuración de la canalización y el complemento para la implementación de ClickOnce  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] se descargan a y ejecutar desde una carpeta segura de la [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] memoria caché de implementación. Para que una [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] hospede un complemento, la canalización y el ensamblado del complemento también se debe descargar en la carpeta segura. Para lograrlo, es preciso que configure el manifiesto de aplicación para incluir tanto la canalización como el ensamblado del complemento en la descarga. Esto se hace más fácilmente en [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], aunque el ensamblado de la canalización y del ensamblado debe estar la carpeta raíz del proyecto de [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] del host en orden para que [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] detecte los ensamblados de canalización.  
  
 Por consiguiente, el primer paso es crear el ensamblado de la canalización y del complemento para la raíz del proyecto [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] estableciendo la salida de la compilación de cada proyecto de ensamblado de canalización y ensamblado de complemento. La siguiente tabla muestra las rutas de la salida de la compilación de los proyectos de ensamblado de canalización el proyecto de ensamblado de complemento que se encuentran en la misma carpeta de solución y raíz que el proyecto de [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] del host.  
  
 Tabla 1: Crear rutas de acceso de salida para los ensamblados de canalización que se hospedan en una aplicación XBAP  
  
|Proyecto de ensamblado de canalización|Ruta de acceso de salida de la compilación|  
|-------------------------------|-----------------------|  
|Contrato|`..\HostXBAP\Contracts\`|  
|Vista de complemento|`..\HostXBAP\AddInViews\`|  
|Adaptador del lado del complemento|`..\HostXBAP\AddInSideAdapters\`|  
|Adaptador del lado del host|`..\HostXBAP\HostSideAdapters\`|  
|Complemento|`..\HostXBAP\AddIns\WPFAddIn1`|  
  
 El siguiente paso es especificar los ensamblados de canalización y el ensamblado del complemento como archivos de contenido de las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] en [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] haciendo lo siguiente:  
  
1.  Incluir Incluso el ensamblado de la canalización y del complemento en el proyecto haciendo clic con el botón derecho en cada carpeta de la canalización en el Explorador de soluciones y elegir **Incluir en el proyecto**.  
  
2.  Establecer el **acción de compilación** de cada ensamblado de canalización y ensamblado de complemento en **Contenido** desde la ventana **Propiedades**.  
  
 El paso final es configurar el manifiesto de aplicación para incluir los archivos del ensamblado de la canalización como el archivo del ensamblado del complemento en la descarga. Los archivos deben encontrarse en las carpetas de la raíz de la carpeta de la caché de [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] que ocupa la aplicación de [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. En [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], para lograr esta configuración es preciso realizar las siguientes acciones:  
  
1.  Haga clic con el botón derecho en el proyecto de [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], haga clic en **Propiedades**, **Publicar** y, después, haga clic en el botón **Archivos de aplicación**.  
  
2.  En el cuadro de diálogo **Archivos de aplicación**, establezca el **estado de la publicación** de la DLL de cada canalización y complemento en **Incluir (automático)** y establezca el **grupo de descarga** de la DLL de cada canalización y complemento en **(Requerido)**.  
  
### <a name="using-the-pipeline-and-add-in-from-the-application-base"></a>Uso de la canalización y del complemento de la base de aplicación  
 Cuando la canalización y el complemento están configurados para la implementación de [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)], se descargan en la misma carpeta de caché de [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] que la [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Para usar la canalización y el complemento de la [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], el código de la [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] debe obtenerlos de la base de la aplicación. Los distintos tipos y miembros del modelo de complemento de .NET Framework para el uso de canalizaciones y complementos proporcionan una compatibilidad especial para este escenario. En primer lugar, la ruta de acceso se identifica mediante el <xref:System.AddIn.Hosting.PipelineStoreLocation.ApplicationBase> valor de enumeración. Este valor se utiliza en las sobrecargas de los miembros del complemento pertinentes para usar canalizaciones que incluyan los siguientes:  
  
-   <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%2CSystem.String%5B%5D%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Rebuild%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Update%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
### <a name="accessing-the-hosts-site-of-origin"></a>Acceso a sitio de origen del Host  
 Para asegurarse de que un complemento puede hacer referencia a los archivos del sitio de origen, debe cargarse con un aislamiento de seguridad equivalente a la aplicación host. Este nivel de seguridad se identifica mediante el <xref:System.AddIn.Hosting.AddInSecurityLevel.Host?displayProperty=nameWithType> valor de enumeración y pasa a la <xref:System.AddIn.Hosting.AddInToken.Activate%2A> método cuando se activa un complemento.  
  
<a name="WPFAddInModelArchitecture"></a>   
## <a name="wpf-add-in-architecture"></a>Arquitectura de complemento WPF  
 En el nivel más alto, como hemos visto, WPF habilita complementos de .NET Framework implementar las interfaces de usuario (que se derivan directa o indirectamente de <xref:System.Windows.FrameworkElement>) mediante <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> y <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>. El resultado es que la aplicación host se devuelve un <xref:System.Windows.FrameworkElement> que se muestra en la interfaz de usuario en la aplicación host.  
  
 Para la interfaz de usuario-en escenarios simples, se trata como nivel de detalle que necesita el desarrollador. Para escenarios más complejos, especialmente aquellas que intenten usar servicios adicionales de WPF como diseño, recursos y enlace de datos, se requiere un conocimiento más detallado de cómo WPF amplía el modelo de complemento de .NET Framework con compatibilidad de UI para comprender sus ventajas y las limitaciones.  
  
 Fundamentalmente, WPF no pasa una interfaz de usuario desde un complemento a una aplicación host; en su lugar, WPF pasa el identificador de ventana de Win32 para la interfaz de usuario mediante el uso de la interoperabilidad con WPF. Por lo tanto, cuando se pasa una interfaz de usuario desde un complemento a una aplicación host, ocurre lo siguiente:  
  
-   En el lado del complemento, WPF adquiere un identificador de ventana de la interfaz de usuario que se mostrará la aplicación host. El identificador de ventana está encapsulado por una clase interna de WPF que se deriva de <xref:System.Windows.Interop.HwndSource> e implementa <xref:System.AddIn.Contract.INativeHandleContract>. Devuelve una instancia de esta clase <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> y se calculan las referencias de dominio de aplicación del complemento al dominio de aplicación de la aplicación host.  
  
-   En el lado de la aplicación host, WPF, vuelve a empaquetar la <xref:System.Windows.Interop.HwndSource> como una clase interna de WPF que se derive de <xref:System.Windows.Interop.HwndHost> y consume <xref:System.AddIn.Contract.INativeHandleContract>. Devuelve una instancia de esta clase <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> a la aplicación host.  
  
 <xref:System.Windows.Interop.HwndHost> existe para mostrar interfaces de usuario, identificadas por los identificadores de ventana, de las interfaces de usuario WPF. Para más información, consulte [Interoperabilidad de WPF y Win32](../advanced/wpf-and-win32-interoperation.md).  
  
 En resumen, <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, y <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> existen para permitir que el identificador de ventana para una UI de WPF se pase de un complemento a una aplicación host, donde se encapsula mediante un <xref:System.Windows.Interop.HwndHost> y muestra la interfaz de usuario de la aplicación host.  
  
> [!NOTE]
>  Dado que la aplicación host obtiene un <xref:System.Windows.Interop.HwndHost>, la aplicación host no puede convertir el objeto devuelto por <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> para el tipo se implementa como mediante el complemento (por ejemplo, un <xref:System.Windows.Controls.UserControl>).  
  
 Por su naturaleza, <xref:System.Windows.Interop.HwndHost> tiene ciertas limitaciones que afectan a cómo las aplicaciones host pueden usarlos. Sin embargo, WPF amplía <xref:System.Windows.Interop.HwndHost> con varias funcionalidades para escenarios de inicio. A continuación se describen estas ventajas y limitaciones.  
  
<a name="WPFAddInModelBenefits"></a>   
## <a name="wpf-add-in-benefits"></a>Ventajas del complemento de WPF  
 Dado que las interfaces de usuario WPF se muestran desde las aplicaciones host mediante una clase interna que deriva de <xref:System.Windows.Interop.HwndHost>, esas interfaces de usuario están restringidas por las capacidades de <xref:System.Windows.Interop.HwndHost> con respecto a los servicios de la UI de WPF como diseño, representación, enlace de datos, estilos, plantillas y recursos. Sin embargo, aumenta su interno WPF <xref:System.Windows.Interop.HwndHost> subclase con capacidades adicionales que incluyen lo siguiente:  
  
-   Tabulación entre la interfaz de usuario de la aplicación host e interfaz de usuario de un complemento. Tenga en cuenta que el modelo de programación "complemento es una interfaz de usuario" requiere que el adaptador de complemento en el lado invalidar <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> para habilitar la tabulación, si el complemento es de plena confianza o de confianza parcial.  
  
-   Teniendo en cuenta los requisitos de accesibilidad para las interfaces de usuario que se muestran desde las interfaces de usuario de aplicación host.  
  
-   Habilitación de las aplicaciones de WPF se ejecutan de forma segura en diversos escenarios de dominio de aplicación.  
  
-   Impedir el acceso no válido para la interfaz de usuario del complemento los identificadores de ventana cuando los complementos se ejecutan con aislamiento de seguridad (es decir, un recinto de seguridad de confianza parcial). Una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> garantiza esta seguridad:  
  
    -   Para el modelo de programación "complemento devuelve una interfaz de usuario", la única manera de pasar el identificador de ventana para un complemento de la interfaz de usuario a través del límite de aislamiento es llamar a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  
  
    -   Para el modelo de programación "complemento es una interfaz de usuario" reemplazar <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> en el adaptador del complemento y llamar al método <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> (como se muestra en los ejemplos anteriores), es necesario, tal como está llamando a agregar en el lado del adaptador `QueryContract` implementación desde el adaptador del host.  
  
-   Se proporciona protección para la ejecución de varios dominios de aplicaciones. Dadas las limitaciones de los dominios de aplicación, las excepciones no controladas que se producen en los dominios de aplicación del complemento provocan que toda la aplicación se bloquee, aunque exista el límite de aislamiento. Sin embargo, WPF y el modelo de complemento de .NET Framework proporcionan una manera sencilla de solucionar este problema y mejorar la estabilidad de la aplicación. Un complemento de WPF que muestra una interfaz de usuario crea un <xref:System.Windows.Threading.Dispatcher> para el subproceso que el dominio de aplicación se ejecuta, si la aplicación host es una aplicación de WPF. Puede detectar excepciones no controladas de todos los que se producen en el dominio de aplicación controlando el <xref:System.Windows.Threading.Dispatcher.UnhandledException> eventos del complemento WPF <xref:System.Windows.Threading.Dispatcher>. Puede obtener el <xref:System.Windows.Threading.Dispatcher> desde el <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A> propiedad.  
  
<a name="WPFAddInModelLimitations"></a>   
## <a name="wpf-add-in-limitations"></a>Limitaciones del complemento de WPF  
 Más allá de las ventajas que WPF se agrega a los comportamientos predeterminados proporcionados por <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost>y los identificadores de ventana, también hay limitaciones para las interfaces de usuario que se muestran desde las aplicaciones host:  
  
-   Interfaces de usuario muestra desde una aplicación host no respetan el comportamiento de recorte de la aplicación host.  
  
-   El concepto de *espacio aéreo* en los escenarios de interoperabilidad también se aplica a los complementos (consulte [Información general sobre áreas de la tecnología](../advanced/technology-regions-overview.md)).  
  
-   La interfaz de usuario de la aplicación host de servicios, como la herencia de los recursos, el enlace de datos y comandos, no están disponibles automáticamente para el complemento de interfaces de usuario. Para proporcionar estos servicios al complemento, es preciso actualizar la canalización.  
  
-   Un complemento de la interfaz de usuario no se puede girar, escalar, sesgar o verse afectada por una transformación (consulte [información general sobre transformaciones](../graphics-multimedia/transforms-overview.md)).  
  
-   Contenido dentro de las interfaces de usuario que se representa mediante el dibujo de las operaciones desde el <xref:System.Drawing> espacio de nombres puede incluir la combinación alfa. Sin embargo, un complemento de la interfaz de usuario y la aplicación host de la interfaz de usuario que lo contiene deben ser 100% opacas; en otras palabras, la `Opacity` propiedad en ambos debe establecerse en 1.  
  
-   Si el <xref:System.Windows.Window.AllowsTransparency%2A> propiedad de una ventana en la aplicación host que contiene un complemento de la interfaz de usuario se establece en `true`, el complemento no es visible. Esto es así incluso si el complemento de la interfaz de usuario es 100% opaco (es decir, el `Opacity` propiedad tiene un valor de 1).  
  
-   Un complemento de la interfaz de usuario debe aparecer encima de otros elementos WPF en la misma ventana de nivel superior.  
  
-   Ninguna parte de interfaz de usuario de un complemento se puede representar mediante un <xref:System.Windows.Media.VisualBrush>. En su lugar, el complemento puede tardar una instantánea de la interfaz de usuario generada para crear un mapa de bits que se puede pasar a la aplicación host mediante los métodos definidos por el contrato.  
  
-   No se puede reproducir archivos multimedia desde un <xref:System.Windows.Controls.MediaElement> en un complemento de la interfaz de usuario.  
  
-   Eventos del mouse generados para el complemento de la interfaz de usuario no recibe ni generados por la aplicación host y el `IsMouseOver` propiedad de interfaz de usuario de la aplicación host tiene un valor de `false`.  
  
-   Cuando el foco cambia entre los controles en un complemento de la interfaz de usuario, el `GotFocus` y `LostFocus` eventos no recibe ni generados por la aplicación host.  
  
-   La parte de una aplicación host que contiene un complemento de la interfaz de usuario aparece en blanco cuando se imprimen.  
  
-   Todos los distribuidores (consulte <xref:System.Windows.Threading.Dispatcher>) creados por el complemento de interfaz de usuario se debe apagar manualmente antes de que el complemento propietario se descargue si continúa la ejecución de la aplicación host. El contrato puede implementar métodos que permiten la aplicación host señalar el complemento antes de que el complemento se descarga, lo que permite que la interfaz de usuario complemento apagar sus distribuidores.  
  
-   Si un complemento de la interfaz de usuario es un <xref:System.Windows.Controls.InkCanvas> o contiene un <xref:System.Windows.Controls.InkCanvas>, no se puede descargar el complemento.  
  
<a name="PerformanceOptimization"></a>   
## <a name="performance-optimization"></a>Optimización del rendimiento  
 De forma predeterminada, cuando se utilizan varios dominios de aplicación, los distintos ensamblados de .NET Framework requeridos por cada aplicación todas cargados en el dominio de la aplicación. Como consecuencia, el tiempo requerido para crear nuevos dominios de aplicación e iniciar aplicaciones en ellas puede afectar al rendimiento. Sin embargo, .NET Framework proporciona una manera de reducir los tiempos de inicio indicando a las aplicaciones pueden compartir ensamblados entre dominios de aplicación si ya están cargados. Para ello, uso el <xref:System.LoaderOptimizationAttribute> atributo, que debe aplicarse al método de punto de entrada (`Main`). En este caso, solo debe usar el código para implementar la definición de aplicación (consulte [Información general sobre la administración de aplicaciones](application-management-overview.md)).  
  
## <a name="see-also"></a>Vea también

- <xref:System.LoaderOptimizationAttribute>
- [Complementos y extensibilidad](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Dominios de aplicación](../../app-domains/application-domains.md)
- [Información general de servicios remotos de .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kwdt6w2k(v=vs.100))
- [Hacer que los objetos sean remotos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/wcf3swha(v=vs.100))
- [Temas "Cómo..."](how-to-topics.md)
