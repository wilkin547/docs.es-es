---
title: Introducción a los complementos
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
ms.openlocfilehash: 93904e308932ea41c736ca849ce0efb200502a7e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738941"
---
# <a name="wpf-add-ins-overview"></a>Información general sobre los complementos de WPF

<a name="Introduction"></a>El .NET Framework incluye un modelo de complemento que los desarrolladores pueden utilizar para crear aplicaciones que admitan la extensibilidad de complementos. Dicho modelo permite la creación de complementos que se integran con las aplicaciones y amplían su funcionalidad. En algunos escenarios, las aplicaciones también necesitan mostrar las interfaces de usuario que proporcionan los complementos. En este tema se muestra cómo WPF amplía el modelo de complemento de .NET Framework para habilitar estos escenarios, la arquitectura subyacente, sus ventajas y sus limitaciones.

<a name="Requirements"></a>

## <a name="prerequisites"></a>Prerequisites

Es necesario estar familiarizado con el modelo de complemento de .NET Framework. Para más información, consulte [Complementos y extensibilidad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).

<a name="AddInsOverview"></a>

## <a name="add-ins-overview"></a>Información general sobre los complementos

Para evitar las complejidades de la recompilación y reimplementación de aplicaciones para incorporar la nueva funcionalidad, estas implementan mecanismos de extensibilidad que permiten a los desarrolladores (tanto propios como de terceros) crear otras aplicaciones que se integran con ellas. La manera más común de admitir este tipo de extensibilidad es mediante el uso de complementos (también conocido como "complementos" y "módulos"). Estos son algunos ejemplos de aplicaciones reales que exponen la extensibilidad con complementos:

- Complementos de Internet Explorer.

- Módulos del Reproductor de Windows Media.

- Complementos de Visual Studio.

Por ejemplo, el modelo del complemento del Reproductor de Windows Media permite a los desarrolladores de otras empresas implementar "módulos" que extienden el Reproductor de Windows Media de varias formas, entre las que se incluye incluida la creación de descodificadores y codificadores para los formatos multimedia que el Reproductor de Windows Media no admite de forma nativa (por ejemplo, DVD o MP3), efectos de audio y máscaras. Cada modelo del complemento se crea para exponer la funcionalidad que es única para una aplicación, aunque hay varias entidades y comportamientos que son comunes a todos los modelos de complementos.

Las tres entidades principales de las soluciones de extensibilidad de complemento habituales son los *contratos*, los *complementos* y las *aplicaciones host*. Los contratos definen la forma en que los complementos se integran con las aplicaciones host de dos maneras:

- Los complementos se integran con la funcionalidad que implementan las aplicaciones host.

- Las aplicaciones host exponen la funcionalidad para que los complementos se integren con ella.

Para que se usen los complementos, es preciso que las aplicaciones host los encuentren y los carguen en tiempo de ejecución. En consecuencia, las aplicaciones que admiten complementos tienen las siguientes responsabilidades adicionales:

- **Detección**: buscar complementos que se adhieran a los contratos que admiten las aplicaciones host.

- **Activación**: cargar, ejecutar y establecer de comunicación con complementos.

- **Aislamiento**: usar dominios de aplicación o procesos para establecer límites de aislamiento que protejan las aplicaciones frente a posibles problemas de seguridad y de ejecución con los complementos.

- **Comunicación**: permitir a los complementos y aplicaciones host comunicarse entre sí en los límites de aislamiento llamando a métodos y pasando datos.

- **Administración de la duración**: cargar y descargar dominios de aplicación y procesos de una manera limpia y predecible (consulte [Dominios de aplicación](../../app-domains/application-domains.md)).

- **Control de versiones**: asegurarse de que las aplicaciones host y los complementos se pueden comunicar cuando se crean nuevas versiones de cualquiera de ellos.

Por último, el desarrollo de un sólido modelo de complemento es una empresa que no es trivial. Por esta razón, el .NET Framework proporciona una infraestructura para crear modelos de complementos.

> [!NOTE]
> Para más información acerca de los complementos, consulte [Complementos y extensibilidad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).

<a name="NETFrameworkAddInModelOverview"></a>

## <a name="net-framework-add-in-model-overview"></a>Introducción al modelo de complemento de .NET Framework

El modelo de complemento de .NET Framework, que se encuentra en el espacio de nombres <xref:System.AddIn>, contiene un conjunto de tipos que están diseñados para simplificar el desarrollo de extensibilidad de complementos. La unidad fundamental del modelo de complemento .NET Framework es el *contrato*, que define cómo una aplicación host y un complemento se comunican entre sí. Un contrato se expone a una aplicación host mediante una *vista* específica de la aplicación host del contrato. Del mismo modo, se expone una *vista* específica del complemento al complemento. Se usa un *adaptador* para que una aplicación host y un complemento se comuniquen entre sus respectivas vistas del contrato. Los contratos, vistas y adaptadores se conocen como segmentos y un conjunto de segmentos relacionados constituye una *canalización*. Las canalizaciones son la base sobre la que el modelo de complemento de .NET Framework admite la detección, la activación, el aislamiento de la seguridad, el aislamiento de la ejecución (mediante procesos y dominios de aplicación), la comunicación, la administración de la duración y el control de versiones.

La suma de todo ello permite a los desarrolladores compilar complementos que se integran con la funcionalidad de una aplicación host. Sin embargo, algunos escenarios requieren que las aplicaciones host muestren las interfaces de usuario proporcionadas por los complementos. Dado que cada tecnología de presentación en el .NET Framework tiene su propio modelo para implementar interfaces de usuario, el modelo de complementos de .NET Framework no admite ninguna tecnología de presentación determinada. En su lugar, WPF amplía el modelo de complemento de .NET Framework con compatibilidad con la interfaz de usuario para complementos.

<a name="WPFAddInModel"></a>

## <a name="wpf-add-ins"></a>Complementos WPF

WPF, junto con el modelo de complemento de .NET Framework, le permite abordar una gran variedad de escenarios que requieren que las aplicaciones host muestren las interfaces de usuario de los complementos. En concreto, estos escenarios se abordan con WPF con los dos modelos de programación siguientes:

1. **El complemento devuelve una interfaz de usuario**. Un complemento devuelve una interfaz de usuario a la aplicación host a través de una llamada al método, tal y como se define en el contrato. Este escenario se utiliza en los casos siguientes:

    - La apariencia de una interfaz de usuario devuelta por un complemento depende de los datos o condiciones que solo existen en tiempo de ejecución, como los informes generados dinámicamente.

    - La interfaz de usuario para los servicios que proporciona un complemento difiere de la interfaz de usuario de las aplicaciones host que pueden usar el complemento.

    - El complemento realiza principalmente un servicio para la aplicación host y notifica el estado a la aplicación host con una interfaz de usuario.

2. **El complemento es una interfaz de usuario**. Un complemento es una interfaz de usuario, tal y como se define en el contrato. Este escenario se utiliza en los casos siguientes:

    - Los complementos solo muestran los servicios que se muestran, como un anuncio.

    - La interfaz de usuario para los servicios que proporciona un complemento es común a todas las aplicaciones host que pueden usar ese complemento, como una calculadora o un selector de colores.

Estos escenarios requieren que los objetos de interfaz de usuario se puedan pasar entre la aplicación host y los dominios de aplicación de complemento. Dado que el modelo de complementos de .NET Framework se basa en la comunicación remota para comunicarse entre los dominios de aplicación, los objetos que se pasan entre ellos deben ser remotos.

Un objeto que se puede usar de forma remota es una instancia de una clase que realiza una o varias de las siguientes acciones:

- Deriva de la clase <xref:System.MarshalByRefObject>.

- Implementa la interfaz <xref:System.Runtime.Serialization.ISerializable>.

- Tiene aplicado el atributo <xref:System.SerializableAttribute>.

> [!NOTE]
> Para obtener más información sobre la creación de objetos de .NET Framework remotos, consulte [crear objetos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/wcf3swha(v=vs.100))de forma remota.

Los tipos de interfaz de usuario de WPF no son remotos. Para solucionar el problema, WPF extiende el .NET Framework modelo de complementos para habilitar la interfaz de usuario de WPF creada por los complementos para que se muestren desde las aplicaciones host. WPF proporciona esta compatibilidad mediante dos tipos: la interfaz <xref:System.AddIn.Contract.INativeHandleContract> y dos métodos estáticos implementados por la clase <xref:System.AddIn.Pipeline.FrameworkElementAdapters>: <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> y <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>. A un nivel alto, estos tipos y métodos se utilizan como se indica a continuación:

1. WPF requiere que las interfaces de usuario proporcionadas por los complementos sean clases que derivan directa o indirectamente de <xref:System.Windows.FrameworkElement>, como formas, controles, controles de usuario, paneles de diseño y páginas.

2. Siempre que el contrato declare que se va a pasar una interfaz de usuario entre el complemento y la aplicación host, debe declararse como un <xref:System.AddIn.Contract.INativeHandleContract> (no un <xref:System.Windows.FrameworkElement>); <xref:System.AddIn.Contract.INativeHandleContract> es una representación remota de la interfaz de usuario del complemento que se puede pasar a través de los límites de aislamiento.

3. Antes de que se pasara desde el dominio de aplicación del complemento, un <xref:System.Windows.FrameworkElement> se empaqueta como un <xref:System.AddIn.Contract.INativeHandleContract> mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.

4. Después de pasarse al dominio de aplicación de la aplicación host, el <xref:System.AddIn.Contract.INativeHandleContract> se debe volver a empaquetar como un <xref:System.Windows.FrameworkElement> llamando a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.

El uso de <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>y <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> depende del escenario específico. En las siguientes secciones se proporciona información acerca de cada modelo de programación.

<a name="ReturnUIFromAddInContract"></a>

## <a name="add-in-returns-a-user-interface"></a>El complemento devuelve una interfaz de usuario

Para que un complemento devuelva una interfaz de usuario a una aplicación host, se requiere lo siguiente:

1. Se deben crear la aplicación host, el complemento y la canalización, como se describe en la documentación de [extensibilidad y complementos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)) de .NET Framework.

2. El contrato debe implementar <xref:System.AddIn.Contract.IContract> y, para devolver una interfaz de usuario, el contrato debe declarar un método con un valor devuelto de tipo <xref:System.AddIn.Contract.INativeHandleContract>.

3. La interfaz de usuario que se pasa entre el complemento y la aplicación host debe derivar directa o indirectamente de <xref:System.Windows.FrameworkElement>.

4. La interfaz de usuario que devuelve el complemento se debe convertir de una <xref:System.Windows.FrameworkElement> a una <xref:System.AddIn.Contract.INativeHandleContract> antes de cruzar el límite de aislamiento.

5. La interfaz de usuario que se devuelve se debe convertir de una <xref:System.AddIn.Contract.INativeHandleContract> a una <xref:System.Windows.FrameworkElement> después de cruzar el límite de aislamiento.

6. La aplicación host muestra el <xref:System.Windows.FrameworkElement>devuelto.

Para obtener un ejemplo que muestra cómo implementar un complemento que devuelve una interfaz de usuario, vea [crear un complemento que devuelva una interfaz de usuario](how-to-create-an-add-in-that-returns-a-ui.md).

<a name="AddInIsAUI"></a>

## <a name="add-in-is-a-user-interface"></a>El complemento es una interfaz de usuario

Cuando un complemento es una interfaz de usuario, se requiere lo siguiente:

1. Se deben crear la aplicación host, el complemento y la canalización, como se describe en la documentación de [extensibilidad y complementos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)) de .NET Framework.

2. La interfaz de contrato para el complemento debe implementar <xref:System.AddIn.Contract.INativeHandleContract>.

3. El complemento que se pasa a la aplicación host debe derivar directa o indirectamente de <xref:System.Windows.FrameworkElement>.

4. El complemento se debe convertir de un <xref:System.Windows.FrameworkElement> a un <xref:System.AddIn.Contract.INativeHandleContract> antes de cruzar el límite de aislamiento.

5. El complemento se debe convertir de un <xref:System.AddIn.Contract.INativeHandleContract> a un <xref:System.Windows.FrameworkElement> después de cruzar el límite de aislamiento.

6. La aplicación host muestra el <xref:System.Windows.FrameworkElement>devuelto.

Para obtener un ejemplo que muestra cómo implementar un complemento que es una interfaz de usuario, vea [crear un complemento que sea una interfaz de usuario](how-to-create-an-add-in-that-is-a-ui.md).

<a name="ReturningMultipleUIsFromAnAddIn"></a>

## <a name="returning-multiple-uis-from-an-add-in"></a>Devolución de varias interfaces de usuario desde un complemento

A menudo, los complementos proporcionan varias interfaces de usuario para que se muestren las aplicaciones host. Por ejemplo, considere un complemento que es una interfaz de usuario que también proporciona información de estado a la aplicación host, también como una interfaz de usuario. Un complemento como este se puede implementar mediante una combinación de técnicas de los modelos de [El complemento devuelve una interfaz de usuario](#ReturnUIFromAddInContract) y [El complemento es una interfaz de usuario](#AddInIsAUI).

<a name="AddInsAndXBAPs"></a>

## <a name="add-ins-and-xaml-browser-applications"></a>Complementos y aplicaciones del explorador XAML

Hasta ahora, en los ejemplos, la aplicación host ha sido una aplicación independiente instalada. Sin embargo, las aplicaciones de explorador XAML (XBAP) también pueden hospedar complementos, aunque con los siguientes requisitos adicionales de compilación e implementación:

- El manifiesto de aplicación de XBAP se debe configurar de forma especial para descargar la canalización (carpetas y ensamblados) y el ensamblado del complemento en la caché de la aplicación ClickOnce en el equipo cliente, en la misma carpeta que la aplicación XBAP.

- El código de XBAP para detectar y cargar complementos debe usar la caché de la aplicación ClickOnce para el XBAP como la canalización y la ubicación del complemento.

- El XBAP debe cargar el complemento en un contexto de seguridad especial si el complemento hace referencia a archivos dinámicos que se encuentran en el sitio de origen. Cuando se hospedan en XBAP, los complementos solo pueden hacer referencia a archivos dinámicos que se encuentran en el sitio de origen de la aplicación host.

Estas tareas se describen con detalle en las subsecciones siguientes.

### <a name="configuring-the-pipeline-and-add-in-for-clickonce-deployment"></a>Configuración de la canalización y el complemento para la implementación de ClickOnce

Las XBAP se descargan y se ejecutan desde una carpeta segura en la caché de implementación de ClickOnce. Para que una aplicación XBAP hospede un complemento, la canalización y el ensamblado del complemento también se deben descargar en la carpeta Safe. Para lograrlo, es preciso que configure el manifiesto de aplicación para incluir tanto la canalización como el ensamblado del complemento en la descarga. Esto se realiza más fácilmente en Visual Studio, aunque la canalización y el ensamblado del complemento deben estar en la carpeta raíz del proyecto de XBAP del host para que Visual Studio detecte los ensamblados de canalización.

Por lo tanto, el primer paso consiste en compilar la canalización y el ensamblado del complemento en la raíz del proyecto de XBAP mediante el establecimiento de los resultados de la compilación de cada ensamblado de canalización y proyectos de ensamblado de complementos. En la tabla siguiente se muestran las rutas de acceso de los resultados de compilación para proyectos de ensamblado de canalización y el proyecto de ensamblado de complemento que se encuentran en la misma solución y carpeta raíz que el proyecto de XBAP de host.

Tabla 1: Crear rutas de la salida de la compilación para los ensamblados de canalización que hospeda una aplicación XBAP

|Proyecto de ensamblado de canalización|Ruta de acceso de salida de la compilación|
|-------------------------------|-----------------------|
|Contrato|`..\HostXBAP\Contracts\`|
|Vista de complemento|`..\HostXBAP\AddInViews\`|
|Adaptador del lado del complemento|`..\HostXBAP\AddInSideAdapters\`|
|Adaptador del lado del host|`..\HostXBAP\HostSideAdapters\`|
|Complemento|`..\HostXBAP\AddIns\WPFAddIn1`|

El siguiente paso consiste en especificar los ensamblados de canalización y el ensamblado de complemento como los archivos de contenido de XBAP en Visual Studio haciendo lo siguiente:

1. Incluir Incluso el ensamblado de la canalización y del complemento en el proyecto haciendo clic con el botón derecho en cada carpeta de la canalización en el Explorador de soluciones y elegir **Incluir en el proyecto**.

2. Establecer el **acción de compilación** de cada ensamblado de canalización y ensamblado de complemento en **Contenido** desde la ventana **Propiedades**.

El paso final es configurar el manifiesto de aplicación para incluir los archivos del ensamblado de la canalización como el archivo del ensamblado del complemento en la descarga. Los archivos deben encontrarse en carpetas en la raíz de la carpeta en la caché de ClickOnce que ocupa la aplicación XBAP. La configuración se puede lograr en Visual Studio haciendo lo siguiente:

1. Haga clic con el botón derecho en el proyecto XBAP, haga clic en **propiedades**, haga clic en **publicar**y, después, haga clic en el botón **archivos de aplicación** .

2. En el cuadro de diálogo **Archivos de aplicación**, establezca el **estado de la publicación** de la DLL de cada canalización y complemento en **Incluir (automático)** y establezca el **grupo de descarga** de la DLL de cada canalización y complemento en **(Requerido)** .

### <a name="using-the-pipeline-and-add-in-from-the-application-base"></a>Uso de la canalización y del complemento de la base de aplicación

Cuando la canalización y el complemento están configurados para la implementación ClickOnce, se descargan en la misma carpeta de caché ClickOnce que la aplicación XBAP. Para usar la canalización y el complemento desde el XBAP, el código de XBAP debe obtenerlos de la base de la aplicación. Los distintos tipos y miembros del modelo de complementos de .NET Framework para usar canalizaciones y complementos proporcionan una compatibilidad especial para este escenario. En primer lugar, la ruta de acceso se identifica mediante el valor de enumeración <xref:System.AddIn.Hosting.PipelineStoreLocation.ApplicationBase>. Este valor se utiliza en las sobrecargas de los miembros del complemento pertinentes para usar canalizaciones que incluyan los siguientes:

- <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>

- <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%2CSystem.String%5B%5D%29?displayProperty=nameWithType>

- <xref:System.AddIn.Hosting.AddInStore.Rebuild%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>

- <xref:System.AddIn.Hosting.AddInStore.Update%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>

### <a name="accessing-the-hosts-site-of-origin"></a>Acceso a sitio de origen del Host

Para asegurarse de que un complemento puede hacer referencia a los archivos del sitio de origen, debe cargarse con un aislamiento de seguridad equivalente a la aplicación host. Este nivel de seguridad se identifica mediante el valor de enumeración <xref:System.AddIn.Hosting.AddInSecurityLevel.Host?displayProperty=nameWithType> y se pasa al método <xref:System.AddIn.Hosting.AddInToken.Activate%2A> cuando se activa un complemento.

<a name="WPFAddInModelArchitecture"></a>

## <a name="wpf-add-in-architecture"></a>Arquitectura de complemento WPF

En el nivel más alto, como hemos visto, WPF permite que los complementos de .NET Framework implementen interfaces de usuario (que se derivan directa o indirectamente de <xref:System.Windows.FrameworkElement>) mediante <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> y <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>. El resultado es que se devuelve a la aplicación host una <xref:System.Windows.FrameworkElement> que se muestra desde la interfaz de usuario en la aplicación host.

En el caso de escenarios sencillos de complementos de la interfaz de usuario, esta es la mayor cantidad de detalles que necesita el desarrollador. En el caso de escenarios más complejos, especialmente aquellos que intentan usar servicios adicionales de WPF, como el diseño, los recursos y el enlace de datos, se requiere un conocimiento más detallado de cómo WPF amplía el modelo de complemento de .NET Framework con compatibilidad con la interfaz de usuario para comprender sus ventajas. y limitaciones.

Fundamentalmente, WPF no pasa una interfaz de usuario de un complemento a una aplicación host; en su lugar, WPF pasa el identificador de ventana de Win32 para la interfaz de usuario mediante la interoperabilidad de WPF. Como tal, cuando se pasa una interfaz de usuario de un complemento a una aplicación host, ocurre lo siguiente:

- En el lado del complemento, WPF adquiere un identificador de ventana para la interfaz de usuario que mostrará la aplicación host. El identificador de ventana está encapsulado por una clase WPF interna que deriva de <xref:System.Windows.Interop.HwndSource> e implementa <xref:System.AddIn.Contract.INativeHandleContract>. <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> devuelve una instancia de esta clase y se calculan las referencias del dominio de aplicación del complemento al dominio de aplicación de la aplicación host.

- En el lado de la aplicación host, WPF empaqueta el <xref:System.Windows.Interop.HwndSource> como una clase WPF interna que deriva de <xref:System.Windows.Interop.HwndHost> y consume <xref:System.AddIn.Contract.INativeHandleContract>. <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> devuelve una instancia de esta clase a la aplicación host.

<xref:System.Windows.Interop.HwndHost> existe para mostrar interfaces de usuario, identificadas por identificadores de ventana, de las interfaces de usuario de WPF. Para más información, consulte [Interoperabilidad de WPF y Win32](../advanced/wpf-and-win32-interoperation.md).

En Resumen, <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>y <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> existen para permitir que el identificador de ventana para una interfaz de usuario de WPF se pase desde un complemento a una aplicación host, donde está encapsulado por una <xref:System.Windows.Interop.HwndHost> y mostrando la interfaz de usuario de la aplicación host.

> [!NOTE]
> Dado que la aplicación host obtiene un <xref:System.Windows.Interop.HwndHost>, la aplicación host no puede convertir el objeto devuelto por <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> al tipo al que lo implementa el complemento (por ejemplo, un <xref:System.Windows.Controls.UserControl>).

Por su naturaleza, <xref:System.Windows.Interop.HwndHost> tiene ciertas limitaciones que afectan al modo en que las aplicaciones host pueden usarlas. Sin embargo, WPF extiende <xref:System.Windows.Interop.HwndHost> con varias funcionalidades para escenarios de complementos. A continuación se describen estas ventajas y limitaciones.

<a name="WPFAddInModelBenefits"></a>

## <a name="wpf-add-in-benefits"></a>Ventajas del complemento de WPF

Dado que las interfaces de usuario de los complementos de WPF se muestran desde las aplicaciones host mediante una clase interna que deriva de <xref:System.Windows.Interop.HwndHost>, esas interfaces de usuario están restringidas por las capacidades de <xref:System.Windows.Interop.HwndHost> con respecto a los servicios de IU de WPF, como el diseño, la representación, el enlace de datos, los estilos, las plantillas y los recursos. Sin embargo, WPF aumenta su subclase <xref:System.Windows.Interop.HwndHost> interna con capacidades adicionales que incluyen lo siguiente:

- Tabulación entre la interfaz de usuario de una aplicación host y la interfaz de usuario de un complemento. Tenga en cuenta que el modelo de programación "el complemento es una interfaz de usuario" requiere que el adaptador del complemento invalide <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> para habilitar la tabulación, si el complemento es de plena confianza o de confianza parcial.

- Respetar los requisitos de accesibilidad de las interfaces de usuario de complementos que se muestran desde las interfaces de usuario de la aplicación host.

- Habilitar las aplicaciones de WPF para que se ejecuten de forma segura en varios escenarios de dominio de aplicación.

- Impedir el acceso no válido a los identificadores de ventana de la interfaz de usuario de complemento cuando los complementos se ejecutan con aislamiento de seguridad (es decir, un espacio aislado de seguridad de confianza parcial). La llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> garantiza esta seguridad:

  - En el modelo de programación "el complemento devuelve una interfaz de usuario", la única manera de pasar el identificador de ventana para una interfaz de usuario de complemento a través del límite de aislamiento es llamar a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.

  - Para el modelo de programación "el complemento es una interfaz de usuario", se requiere invalidar <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> en el adaptador de complemento y llamar a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> (como se muestra en los ejemplos anteriores), como llama a la implementación de `QueryContract` del adaptador de complemento desde el adaptador del host.

- Se proporciona protección para la ejecución de varios dominios de aplicaciones. Dadas las limitaciones de los dominios de aplicación, las excepciones no controladas que se producen en los dominios de aplicación del complemento provocan que toda la aplicación se bloquee, aunque exista el límite de aislamiento. Sin embargo, WPF y el modelo de complemento de .NET Framework proporcionan una manera sencilla de solucionar este problema y mejorar la estabilidad de la aplicación. Un complemento de WPF que muestra una interfaz de usuario crea un <xref:System.Windows.Threading.Dispatcher> para el subproceso en el que se ejecuta el dominio de aplicación, si la aplicación host es una aplicación de WPF. Puede detectar todas las excepciones no controladas que se producen en el dominio de aplicación controlando el evento de <xref:System.Windows.Threading.Dispatcher.UnhandledException> del <xref:System.Windows.Threading.Dispatcher>del complemento de WPF. Puede obtener la <xref:System.Windows.Threading.Dispatcher> de la propiedad <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A>.

<a name="WPFAddInModelLimitations"></a>

## <a name="wpf-add-in-limitations"></a>Limitaciones del complemento de WPF

Además de las ventajas que WPF agrega a los comportamientos predeterminados proporcionados por <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost>y los identificadores de ventana, también hay limitaciones en las interfaces de usuario de complementos que se muestran desde las aplicaciones host:

- Las interfaces de usuario de complementos que se muestran desde una aplicación host no respetan el comportamiento de recorte de la aplicación host.

- El concepto de *espacio aéreo* en los escenarios de interoperabilidad también se aplica a los complementos (consulte [Información general sobre áreas de la tecnología](../advanced/technology-regions-overview.md)).

- Los servicios de interfaz de usuario de una aplicación host, como la herencia de recursos, el enlace de datos y los comandos, no están disponibles automáticamente para las interfaces de usuario de complementos. Para proporcionar estos servicios al complemento, es preciso actualizar la canalización.

- Una interfaz de usuario de complementos no se puede girar, escalar, sesgar ni verse afectada de ningún modo por una transformación (consulte [información general sobre transformaciones](../graphics-multimedia/transforms-overview.md)).

- El contenido que se encuentra dentro de las interfaces de usuario del complemento que se representa mediante las operaciones de dibujo del espacio de nombres <xref:System.Drawing> puede incluir la combinación alfa. Sin embargo, una interfaz de usuario de complemento y la interfaz de usuario de la aplicación host que la contiene deben ser de 100% opacas; en otras palabras, la propiedad `Opacity` en ambos debe establecerse en 1.

- Si la propiedad <xref:System.Windows.Window.AllowsTransparency%2A> de una ventana de la aplicación host que contiene una interfaz de usuario de complemento está establecida en `true`, el complemento no es visible. Esto es así incluso si la interfaz de usuario del complemento es 100% opaca (es decir, la propiedad `Opacity` tiene un valor de 1).

- Una interfaz de usuario de complemento debe aparecer encima de otros elementos de WPF en la misma ventana de nivel superior.

- Ninguna parte de la interfaz de usuario de un complemento se puede representar mediante un <xref:System.Windows.Media.VisualBrush>. En su lugar, el complemento puede tomar una instantánea de la interfaz de usuario generada para crear un mapa de bits que se puede pasar a la aplicación host mediante métodos definidos por el contrato.

- Los archivos multimedia no se pueden reproducir desde un <xref:System.Windows.Controls.MediaElement> en una interfaz de usuario de complemento.

- Los eventos del mouse generados para la interfaz de usuario del complemento no se han recibido ni generado por la aplicación host, y la propiedad `IsMouseOver` de la interfaz de usuario de la aplicación host tiene un valor de `false`.

- Cuando el foco se desplaza entre los controles de una interfaz de usuario de complemento, la aplicación host no recibe ni genera los eventos `GotFocus` y `LostFocus`.

- La parte de una aplicación host que contiene una interfaz de usuario de complemento aparece en blanco cuando se imprime.

- Todos los distribuidores (vea <xref:System.Windows.Threading.Dispatcher>) creados por la interfaz de usuario del complemento deben cerrarse manualmente antes de que se descargue el complemento propietario si la aplicación host continúa la ejecución. El contrato puede implementar métodos que permitan que la aplicación host señale el complemento antes de que se descargue el complemento, lo que permite que la interfaz de usuario del complemento cierre sus distribuidores.

- Si una interfaz de usuario de complemento es un <xref:System.Windows.Controls.InkCanvas> o contiene un <xref:System.Windows.Controls.InkCanvas>, no se puede descargar el complemento.

<a name="PerformanceOptimization"></a>

## <a name="performance-optimization"></a>Optimización del rendimiento

De forma predeterminada, cuando se usan varios dominios de aplicación, se cargan todos los ensamblados .NET Framework necesarios para cada aplicación en el dominio de esa aplicación. Como consecuencia, el tiempo requerido para crear nuevos dominios de aplicación e iniciar aplicaciones en ellas puede afectar al rendimiento. Sin embargo, el .NET Framework proporciona una manera de reducir las horas de inicio, ya que indica a las aplicaciones que compartan los ensamblados entre los dominios de aplicación si ya se han cargado. Para ello, se usa el atributo <xref:System.LoaderOptimizationAttribute>, que se debe aplicar al método de punto de entrada (`Main`). En este caso, solo debe usar el código para implementar la definición de aplicación (consulte [Información general sobre la administración de aplicaciones](application-management-overview.md)).

## <a name="see-also"></a>Consulte también

- <xref:System.LoaderOptimizationAttribute>
- [Complementos y extensibilidad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Dominios de aplicación](../../app-domains/application-domains.md)
- [Información general sobre .NET Framework Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kwdt6w2k(v=vs.100))
- [Convertir objetos en modo remoto](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/wcf3swha(v=vs.100))
- [Temas "Cómo..."](how-to-topics.md)
