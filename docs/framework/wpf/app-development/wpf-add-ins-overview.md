---
title: "Información general sobre los complementos de WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "36"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ffd45957b41cdfd8488aedd865aa70ef5b2634b2
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="wpf-add-ins-overview"></a>Información general sobre los complementos de WPF
<a name="Introduction"></a>El[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] incluye un modelo de complementos que los desarrolladores pueden usar para crear aplicaciones que admiten la extensibilidad de los complementos. Dicho modelo permite la creación de complementos que se integran con las aplicaciones y amplían su funcionalidad. En algunos escenarios, las aplicaciones también necesitan mostrar [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] que proporcionan los complementos. En este tema se muestra la forma en que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aumenta el modelo del complemento de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para habilitar estos escenarios, la arquitectura subyacente, sus ventajas y sus limitaciones.  
  

  
<a name="Requirements"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Se requieren conocimientos del modelo del complemento de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Para más información, consulte [Complementos y extensibilidad](../../../../docs/framework/add-ins/index.md).  
  
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
  
-   **Detección**: buscar complementos que se adhieran a los contratos que admiten las aplicaciones host.  
  
-   **Activación**: cargar, ejecutar y establecer de comunicación con complementos.  
  
-   **Aislamiento**: usar dominios de aplicación o procesos para establecer límites de aislamiento que protejan las aplicaciones frente a posibles problemas de seguridad y de ejecución con los complementos.  
  
-   **Comunicación**: permitir a los complementos y aplicaciones host comunicarse entre sí en los límites de aislamiento llamando a métodos y pasando datos.  
  
-   **Administración de la duración**: cargar y descargar dominios de aplicación y procesos de una manera limpia y predecible (consulte [Dominios de aplicación](../../../../docs/framework/app-domains/application-domains.md)).  
  
-   **Control de versiones**: asegurarse de que las aplicaciones host y los complementos se pueden comunicar cuando se crean nuevas versiones de cualquiera de ellos.  
  
 Por último, el desarrollo de un sólido modelo de complemento es una empresa que no es trivial. Por este motivo, [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporciona una infraestructura para compilar modelos de complementos.  
  
> [!NOTE]
>  Para más información acerca de los complementos, consulte [Complementos y extensibilidad](../../../../docs/framework/add-ins/index.md).  
  
<a name="NETFrameworkAddInModelOverview"></a>   
## <a name="net-framework-add-in-model-overview"></a>Introducción al modelo de complemento de .NET Framework  
 El [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] complemento modelo, se encuentra en la <xref:System.AddIn> espacio de nombres contiene un conjunto de tipos que están diseñados para simplificar el desarrollo de complemento de extensibilidad. La unidad fundamental del modelo de complemento de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] es el *contrato*, que define cómo se comunican una aplicación host y un complemento entre sí. Un contrato se expone a una aplicación host mediante una *vista* específica de la aplicación host del contrato. Del mismo modo, se expone una *vista* específica del complemento al complemento. Se usa un *adaptador* para que una aplicación host y un complemento se comuniquen entre sus respectivas vistas del contrato. Los contratos, vistas y adaptadores se conocen como segmentos y un conjunto de segmentos relacionados constituye una *canalización*. Las canalizaciones son la base sobre la que el modelo de complemento de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] admite la detección, la activación, el aislamiento de el seguridad, aislamiento de ejecución (mediante procesos y dominios de aplicación), la comunicación, la administración de la duración y el control de versiones.  
  
 La suma de todo ello permite a los desarrolladores compilar complementos que se integran con la funcionalidad de una aplicación host. Sin embargo, algunos escenarios requieren que las aplicaciones host muestren [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] que proporcionan los complementos. Dado que cada una de las tecnologías de presentación de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] tiene su propio modelo de implementación [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], el modelo de complemento de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] no admite ninguna tecnología de presentación concreta. En su lugar, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] amplía el modelo de complemento de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] con la compatibilidad de los complementos con la i[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
<a name="WPFAddInModel"></a>   
## <a name="wpf-add-ins"></a>Complementos WPF  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], junto con el modelo de complemento de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], permite abordar una amplia variedad de escenarios que requieren que las aplicaciones host muestren las interfaces de usuario [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] de los complementos. En concreto, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aborda estos escenarios con los dos modelos de programación siguientes:  
  
1.  **El complemento devuelve una interfaz de usuario**. Un complemento devuelve una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a la aplicación host mediante la llamada a un método, como se define en el contrato. Este escenario se utiliza en los casos siguientes:  
  
    -   La apariencia de una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que devuelve un complemento depende de datos o condiciones que solo existen en tiempo de ejecución, como los informes generados dinámicamente.  
  
    -   La [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de los servicios que proporciona un complemento no es la misma que la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de las aplicaciones host que pueden usar el complemento.  
  
    -   El complemento realiza principalmente un servicio para la aplicación host y notifica el estado a esta con una interfaz de usuario [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
2.  **El complemento es una interfaz de usuario**. Un complemento es una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], como define el contrato. Este escenario se utiliza en los casos siguientes:  
  
    -   Los complementos solo muestran los servicios que se muestran, como un anuncio.  
  
    -   La [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de los servicios que proporciona un complemento es común a todas las aplicaciones host que pueden utilizar dicho complemento, como una calculadora o un selector de colores.  
  
 Estos escenarios requieren que [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se puedan pasar objetos de la interfaz de usuario entre la aplicación host y los dominios de aplicaciones del complemento. Dado que el modelo de complemento de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] se basa en la comunicación remota entre dominios de aplicación, los objetos que se pasan entre ellos deben poder utilizarse de forma remota.  
  
 Un objeto que se puede usar de forma remota es una instancia de una clase que realiza una o varias de las siguientes acciones:  
  
-   Se deriva de la <xref:System.MarshalByRefObject> clase.  
  
-   Implementa la interfaz <xref:System.Runtime.Serialization.ISerializable>.  
  
-   Tiene la <xref:System.SerializableAttribute> atributo aplicado.  
  
> [!NOTE]
>  Para más información acerca de la creación de objetos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] remotos, consulte [Hacer que los objetos sean remotos](http://msdn.microsoft.com/library/01197253-3f13-43b7-894d-9683e431192a).  
  
 Los tipo de interfaz de usuario de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] no se pueden usar de forma remota. Para solucionar el problema, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] amplía el modelo de complemento de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para habilitar la interfaz de usuario de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] creada por los complementos que se muestran desde las aplicaciones host. Se admiten por [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] por dos tipos: el <xref:System.AddIn.Contract.INativeHandleContract> interfaz y dos métodos estáticos que implementa el <xref:System.AddIn.Pipeline.FrameworkElementAdapters> clase: <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> y <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>. A un nivel alto, estos tipos y métodos se utilizan como se indica a continuación:  
  
1.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]requiere que [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] proporcionada por complementos son clases que derivan directa o indirectamente de <xref:System.Windows.FrameworkElement>, por ejemplo, formas, controles, controles de usuario, los paneles de diseño y páginas.  
  
2.  Siempre que el contrato declare que se pasará una interfaz de usuario entre el complemento y la aplicación host, se debe declarar como una <xref:System.AddIn.Contract.INativeHandleContract> (no un <xref:System.Windows.FrameworkElement>); <xref:System.AddIn.Contract.INativeHandleContract> es una representación utilizable de forma remota el complemento de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que se pueden pasar a través de los límites de aislamiento.  
  
3.  Antes de que se pasan desde dominio de aplicación del complemento, un <xref:System.Windows.FrameworkElement> se empaqueta como un <xref:System.AddIn.Contract.INativeHandleContract> mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  
  
4.  Después de que se pasa al dominio de aplicación de la aplicación host, el <xref:System.AddIn.Contract.INativeHandleContract> deben volver a empaquetar como un <xref:System.Windows.FrameworkElement> mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.  
  
 Cómo <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, y <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> se usan depende del escenario específico. En las siguientes secciones se proporciona información acerca de cada modelo de programación.  
  
<a name="ReturnUIFromAddInContract"></a>   
## <a name="add-in-returns-a-user-interface"></a>El complemento devuelve una interfaz de usuario  
 Para que un complemento devuelva una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a una aplicación host, se necesita lo siguiente:  
  
1.  La aplicación host, el complemento y la canalización deben crearse, como se describe en el documento [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)][Complementos y extensibilidad](../../../../docs/framework/add-ins/index.md).  
  
2.  El contrato debe implementar <xref:System.AddIn.Contract.IContract> y, para devolver un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], el contrato debe declarar un método con un valor devuelto de tipo <xref:System.AddIn.Contract.INativeHandleContract>.  
  
3.  El [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que se pasa entre el complemento y el host de aplicación debe directa o indirectamente derivarse <xref:System.Windows.FrameworkElement>.  
  
4.  El [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] devuelto por el complemento se debe convertir de un <xref:System.Windows.FrameworkElement> a una <xref:System.AddIn.Contract.INativeHandleContract> antes de cruzar el límite de aislamiento.  
  
5.  El [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que se devuelve se deben convertir de un <xref:System.AddIn.Contract.INativeHandleContract> a una <xref:System.Windows.FrameworkElement> después de cruzar el límite de aislamiento.  
  
6.  La aplicación host muestra el valor devuelto <xref:System.Windows.FrameworkElement>.  
  
 Para ver un ejemplo en el que se muestra cómo implementar un complemento que devuelve una interfaz de usuario [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], consulte [Cómo: Crear un complemento que devuelva una interfaz de usuario](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md).  
  
<a name="AddInIsAUI"></a>   
## <a name="add-in-is-a-user-interface"></a>El complemento es una interfaz de usuario  
 Cuando un complemento es una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], se requiere lo siguiente:  
  
1.  La aplicación host, el complemento y la canalización deben crearse, como se describe en el documento [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)][Complementos y extensibilidad](../../../../docs/framework/add-ins/index.md).  
  
2.  Debe implementar la interfaz de contrato para el complemento <xref:System.AddIn.Contract.INativeHandleContract>.  
  
3.  El complemento que se pasa a la aplicación host debe directa o indirectamente derivan de <xref:System.Windows.FrameworkElement>.  
  
4.  El complemento se debe convertir de un <xref:System.Windows.FrameworkElement> a una <xref:System.AddIn.Contract.INativeHandleContract> antes de cruzar el límite de aislamiento.  
  
5.  El complemento se debe convertir de un <xref:System.AddIn.Contract.INativeHandleContract> a una <xref:System.Windows.FrameworkElement> después de cruzar el límite de aislamiento.  
  
6.  La aplicación host muestra el valor devuelto <xref:System.Windows.FrameworkElement>.  
  
 Para ver un ejemplo en el que se muestra cómo implementar un complemento que es una interfaz de usuario [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], consulte [Cómo: Crear un complemento que sea una interfaz de usuario](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-is-a-ui.md).  
  
<a name="ReturningMultipleUIsFromAnAddIn"></a>   
## <a name="returning-multiple-uis-from-an-add-in"></a>Devolución de varias interfaces de usuario desde un complemento  
 Los complementos a menudo proporcionan varias [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] para que se muestren las aplicaciones host. Por ejemplo, considere un complemento que sea una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] y que también proporcione información de estado a la aplicación host, también como una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Un complemento como este se puede implementar mediante una combinación de técnicas de los modelos de [El complemento devuelve una interfaz de usuario](#ReturnUIFromAddInContract) y [El complemento es una interfaz de usuario](#AddInIsAUI).  
  
<a name="AddInsAndXBAPs"></a>   
## <a name="add-ins-and-xaml-browser-applications"></a>Complementos y aplicaciones del explorador XAML  
 Hasta ahora, en los ejemplos, la aplicación host ha sido una aplicación independiente instalada. Pero [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] también pueden hospedar complementos, aunque con los siguientes requisitos adicionales de compilación e implementación:  
  
-   El manifiesto de aplicación de [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] se debe configurar especialmente para descargar la canalización (carpetas y ensamblados) y el ensamblado del complemento a la caché de la aplicación [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] en el equipo cliente, en la misma carpeta que la [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
-   Para detectar y cargar complementos, el código de la [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] debe usar la caché de la aplicación [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] para la [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] como ubicación de la canalización y del complemento.  
  
-   La [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] debe cargar el complemento en un contexto de seguridad especial si el complemento hace referencia a archivos dinámicos que se encuentran en el sitio de origen; cuando los hospedan [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], los complementos solo pueden hacer referencia a los archivos dinámico que se encuentran en el sitio de origen de la aplicación host.  
  
 Estas tareas se describen con detalle en las subsecciones siguientes.  
  
### <a name="configuring-the-pipeline-and-add-in-for-clickonce-deployment"></a>Configuración de la canalización y el complemento para la implementación de ClickOnce  
 Las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] se descargan en una carpeta segura de la caché de implementación de [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] y se ejecutan desde ella. Para que una [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] hospede un complemento, la canalización y el ensamblado del complemento también se debe descargar en la carpeta segura. Para lograrlo, es preciso que configure el manifiesto de aplicación para incluir tanto la canalización como el ensamblado del complemento en la descarga. Esto se hace más fácilmente en [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], aunque el ensamblado de la canalización y del ensamblado debe estar la carpeta raíz del proyecto de [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] del host en orden para que [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] detecte los ensamblados de canalización.  
  
 Por consiguiente, el primer paso es crear el ensamblado de la canalización y del complemento para la raíz del proyecto [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] estableciendo la salida de la compilación de cada proyecto de ensamblado de canalización y ensamblado de complemento. La siguiente tabla muestra las rutas de la salida de la compilación de los proyectos de ensamblado de canalización el proyecto de ensamblado de complemento que se encuentran en la misma carpeta de solución y raíz que el proyecto de [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] del host.  
  
 Tabla 1: Crear rutas de la salida de la compilación para los ensamblados de canalización que hospeda una aplicación XBAP  
  
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
 Cuando la canalización y el complemento están configurados para la implementación de [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)], se descargan en la misma carpeta de caché de [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] que la [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Para usar la canalización y el complemento de la [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], el código de la [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] debe obtenerlos de la base de la aplicación. Los distintos tipos y miembros del modelo de complemento de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para el uso de canalizaciones y complementos proporcionan una compatibilidad especial con este escenario. En primer lugar, la ruta de acceso se identifica mediante el <xref:System.AddIn.Hosting.PipelineStoreLocation.ApplicationBase> valor de enumeración. Este valor se utiliza en las sobrecargas de los miembros del complemento pertinentes para usar canalizaciones que incluyan los siguientes:  
  
-   <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%2CSystem.String%5B%5D%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Rebuild%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Update%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
### <a name="accessing-the-hosts-site-of-origin"></a>Acceso a sitio de origen del Host  
 Para asegurarse de que un complemento puede hacer referencia a los archivos del sitio de origen, debe cargarse con un aislamiento de seguridad equivalente a la aplicación host. Este nivel de seguridad se identifica mediante el <xref:System.AddIn.Hosting.AddInSecurityLevel.Host?displayProperty=nameWithType> valor de enumeración y pasa a la <xref:System.AddIn.Hosting.AddInToken.Activate%2A> método cuando se activa un complemento.  
  
<a name="WPFAddInModelArchitecture"></a>   
## <a name="wpf-add-in-architecture"></a>Arquitectura de complemento WPF  
 En el nivel superior, como hemos visto, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] permite [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] complementos para implementar [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] (que se derivan directa o indirectamente de <xref:System.Windows.FrameworkElement>) con <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> y <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>. El resultado es que la aplicación host se devuelve un <xref:System.Windows.FrameworkElement> que se muestra de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] en la aplicación host.  
  
 En el caso de escenarios de complementos de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] simples, este es todo el detalle que necesita el desarrollador. Para escenarios más complejos, especialmente las que intente utilizar adicionales [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] servicios, como el diseño, los recursos y enlace de datos, más un conocimiento detallan de cómo [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] amplía la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modelo con [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] soporte técnico debe conocer sus ventajas y limitaciones.  
  
 Fundamentalmente, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] no pasa una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] interfaz de usuario desde un complemento a una aplicación host; en su lugar, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] pasa el identificador de ventana de Win32 para la interfaz [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de usuario mediante la interoperabilidad de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Por lo tanto, cuando una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de un complemento se pasa a una aplicación host, ocurre lo siguiente:  
  
-   En el lado del complemento, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] adquiere un identificador de ventana para la interfaz de usuario [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que mostrará la aplicación host. El identificador de ventana se encapsula una interno [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] clase que deriva de <xref:System.Windows.Interop.HwndSource> e implementa <xref:System.AddIn.Contract.INativeHandleContract>. Devuelve una instancia de esta clase <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> y se serializará desde dominio de aplicación del complemento al dominio de aplicación de la aplicación host.  
  
-   En el lado de la aplicación host, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] vuelve a empaquetar la <xref:System.Windows.Interop.HwndSource> como interno [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] clase que deriva de <xref:System.Windows.Interop.HwndHost> y consume <xref:System.AddIn.Contract.INativeHandleContract>. Devuelve una instancia de esta clase <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> a la aplicación host.  
  
 <xref:System.Windows.Interop.HwndHost>no existe para mostrar [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], identificadas por los identificadores de ventana, a partir de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]. Para más información, consulte [Interoperabilidad de WPF y Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).  
  
 En resumen, <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, y <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> existe para permitir que el identificador de ventana para un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que se pasan de un complemento a una aplicación host, que está encapsulado por un <xref:System.Windows.Interop.HwndHost> y muestra el host la aplicación [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
> [!NOTE]
>  Dado que la aplicación host obtiene una <xref:System.Windows.Interop.HwndHost>, la aplicación host no puede convertir el objeto devuelto por <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> para el tipo se implementa, el complemento (por ejemplo, un <xref:System.Windows.Controls.UserControl>).  
  
 Por su naturaleza, <xref:System.Windows.Interop.HwndHost> tiene ciertas limitaciones que afectan a cómo las aplicaciones host pueden usar. Sin embargo, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extiende <xref:System.Windows.Interop.HwndHost> con varias funciones para escenarios de complemento. A continuación se describen estas ventajas y limitaciones.  
  
<a name="WPFAddInModelBenefits"></a>   
## <a name="wpf-add-in-benefits"></a>Ventajas del complemento de WPF  
 Dado que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] complemento [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] se muestran desde aplicaciones de host mediante una clase interna que se deriva de <xref:System.Windows.Interop.HwndHost>, dichos [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] están restringidas por las capacidades de <xref:System.Windows.Interop.HwndHost> con respecto a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] servicios como diseño, representación, enlace de datos, estilos, plantillas y recursos. Sin embargo, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aumenta su interno <xref:System.Windows.Interop.HwndHost> subclase con capacidades adicionales que incluyen lo siguiente:  
  
-   Desplazamiento mediante tabulador entre la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de una aplicación host y la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de un complemento. Tenga en cuenta que el "complemento es un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]" modelo de programación requiere que el adaptador de complemento de conversión reemplazar <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> para habilitar la tabulación, si el complemento es de plena confianza o de confianza parcial.  
  
-   Cumplimiento de los requisitos de accesibilidad para las [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] del complemento de que se muestran en las [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] de la aplicación host.  
  
-   Habilitación de aplicaciones [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] que se ejecutan de forma segura en varios escenarios de dominio de aplicación.  
  
-   Se impide el acceso no válido a los identificadores de la ventana de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del complemento cuando los complementos se ejecutan con aislamiento de seguridad (es decir, un espacio aislado de seguridad de confianza parcial). Al llamar a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> garantiza esta seguridad:  
  
    -   Para el "complemento devuelve un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]" modelo de programación, la única manera de pasar el identificador de ventana para un complemento de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] en el aislamiento límite consiste en llamar a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  
  
    -   Para el "complemento es un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]" de programación del modelo, reemplazar <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> en el adaptador de complemento de conversión y llamar al método <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> (como se muestra en los ejemplos anteriores), es necesario, tal y como está llamando al complemento en el lado del adaptador `QueryContract` implementación desde el adaptador del host.  
  
-   Se proporciona protección para la ejecución de varios dominios de aplicaciones. Dadas las limitaciones de los dominios de aplicación, las excepciones no controladas que se producen en los dominios de aplicación del complemento provocan que toda la aplicación se bloquee, aunque exista el límite de aislamiento. Sin embargo, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] y el modelo del complemento de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporcionan una manera sencilla de evitar este problema y mejorar la estabilidad de la aplicación. A [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] complemento muestra un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] crea un <xref:System.Windows.Threading.Dispatcher> para el subproceso que el dominio de aplicación se ejecuta en, si la aplicación host es un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicación. Puede detectar excepciones no controladas de todos los que se producen en el dominio de aplicación controlando el <xref:System.Windows.Threading.Dispatcher.UnhandledException> eventos de la [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] del complemento <xref:System.Windows.Threading.Dispatcher>. Puede obtener el <xref:System.Windows.Threading.Dispatcher> desde el <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A> propiedad.  
  
<a name="WPFAddInModelLimitations"></a>   
## <a name="wpf-add-in-limitations"></a>Limitaciones del complemento de WPF  
 Más allá de las ventajas que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] agrega a los comportamientos predeterminados proporcionados por <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost>e identificadores de ventana, también existen limitaciones en el complemento [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] que se muestran en las aplicaciones de host:  
  
-   Complemento [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] muestra desde un host de aplicación no respeta comportamiento de recorte de la aplicación host.  
  
-   El concepto de *espacio aéreo* en los escenarios de interoperabilidad también se aplica a los complementos (consulte [Información general sobre áreas de la tecnología](../../../../docs/framework/wpf/advanced/technology-regions-overview.md)).  
  
-   Una aplicación host [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] servicios, como la herencia de los recursos, el enlace de datos y comandos, no están disponibles automáticamente para el complemento [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]. Para proporcionar estos servicios al complemento, es preciso actualizar la canalización.  
  
-   Una interfaz de usuario del complemento no se puede girar, escalar, sesgar ni verse afectada de ninguna otra forma por una transformación (consulte [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]Información general sobre [transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)).  
  
-   Contenido dentro de complemento [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] que se representa mediante el dibujo de las operaciones de la <xref:System.Drawing> espacio de nombres puede incluir combinación alfa. Sin embargo, tanto la interfaz de usuario del complemento como la de aplicación host [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que la contiene deben ser 100 % opacas; es decir, la `Opacity` propiedad [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de ambas se debe establecer en 1.  
  
-   Si el <xref:System.Windows.Window.AllowsTransparency%2A> propiedad de una ventana en la aplicación host que contiene un complemento de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se establece en `true`, el complemento es invisible. Esto es cierto incluso si el complemento [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] es 100% opaca (es decir, el `Opacity` propiedad tiene un valor de 1).  
  
-   Una interfaz de usuario del complemento [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aparece encima de los restantes elementos de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] en la misma ventana de nivel superior.  
  
-   Ninguna parte de un complemento [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se puede representar mediante un <xref:System.Windows.Media.VisualBrush>. En su lugar, el complemento puede tomar una instantánea de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] generada para crear un mapa de bits que se puede pasar a la aplicación host mediante los métodos que se definen en el contrato.  
  
-   No se puede reproducir archivos multimedia desde un <xref:System.Windows.Controls.MediaElement> en un complemento de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
-   Los eventos del mouse generados para la interfaz de usuario del complemento no los genera ni los recibe la aplicación host y la propiedad [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de la interfaz de usuario de la aplicación host [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] tiene un valor de `IsMouseOver``false`.  
  
-   Cuando el foco cambia entre los controles de una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del complemento, la aplicación host no recibe ni genera los eventos `GotFocus` y `LostFocus`.  
  
-   La parte de una aplicación host que contiene un complemento de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aparecerá en blanco cuando se imprima.  
  
-   Todos los distribuidores (vea <xref:System.Windows.Threading.Dispatcher>) creados por el complemento de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] debe cerrarse manualmente antes de que el complemento de propietario se descargan si continúa la ejecución de la aplicación host. El contrato puede implementar métodos que permiten la aplicación de host señalar el complemento antes de que el complemento se descarga, lo que permite que el complemento [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para cerrar sus distribuidores.  
  
-   Si un complemento de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] es un <xref:System.Windows.Controls.InkCanvas> o contiene un <xref:System.Windows.Controls.InkCanvas>, no se puede descargar el complemento.  
  
<a name="PerformanceOptimization"></a>   
## <a name="performance-optimization"></a>Optimización del rendimiento  
 De manera predeterminada, si se utilizan varios dominios de aplicación, los distintos ensamblados de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que requiere cada aplicación se cargan en el dominio de la aplicación. Como consecuencia, el tiempo requerido para crear nuevos dominios de aplicación e iniciar aplicaciones en ellas puede afectar al rendimiento. Sin embargo, [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporciona una manera de reducir los tiempos de inicio indicando a las aplicaciones que compartan ensamblados entre los dominios de aplicación si ya están cargados. Para ello, usando la <xref:System.LoaderOptimizationAttribute> atributo, que debe aplicarse al método de punto de entrada (`Main`). En este caso, solo debe usar el código para implementar la definición de aplicación (consulte [Información general sobre la administración de aplicaciones](../../../../docs/framework/wpf/app-development/application-management-overview.md)).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.LoaderOptimizationAttribute>  
 [Complementos y extensibilidad](../../../../docs/framework/add-ins/index.md)  
 [Dominios de aplicación](../../../../docs/framework/app-domains/application-domains.md)  
 [Información general sobre comunicación remota de .NET framework](http://msdn.microsoft.com/library/eccb1d31-0a22-417a-97fd-f4f1f3aa4462)  
 [Realizar objetos utilizables de forma remota](http://msdn.microsoft.com/library/01197253-3f13-43b7-894d-9683e431192a)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/app-development/how-to-topics.md)
