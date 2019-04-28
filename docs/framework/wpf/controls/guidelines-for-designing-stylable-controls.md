---
title: Instrucciones para el diseño de controles con estilos
ms.date: 03/30/2017
helpviewer_keywords:
- style design for controls [WPF]
- controls [WPF], style design
ms.assetid: c52dde45-a311-4531-af4c-853371c4d5f4
ms.openlocfilehash: 756cc821b1a9fe20741e390a1fe6e84d12cc6363
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009973"
---
# <a name="guidelines-for-designing-stylable-controls"></a>Instrucciones para el diseño de controles con estilos
En este documento se resume un conjunto de procedimientos recomendados que se deben tener en cuenta al diseñar un control con el que pretende crear estilos y plantillas con facilidad. Este conjunto de procedimientos se obtiene de una gran serie de pruebas y errores al trabajar con estilos de control de temas para el conjunto de controles [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] integrado. Se ha observado que una aplicación de estilos correcta es tanto una función de un modelo de objeto bien diseñado como del propio estilo. Este documento está destinado a los autores de controles, y no a los autores de estilos.  
  
  <a name="Terminology"></a>   
## <a name="terminology"></a>Terminología  
 La "aplicación de estilos y las plantillas" hacen referencia al conjunto de tecnologías que permiten a un autor de controles aplazar los aspectos visuales del control al estilo y la plantilla del control. Este conjunto de tecnologías incluye:  
  
- estilos (incluidos los configuradores de propiedad, los desencadenadores y los guiones gráficos),  
  
- recursos,  
  
- plantillas de control,  
  
- plantillas de datos.  
  
 Para obtener una introducción a los estilos y plantillas, vea [Aplicar estilos y plantillas](styling-and-templating.md).  
  
<a name="Before_You_Start__Understanding_Your_Control"></a>   
## <a name="before-you-start-understanding-your-control"></a>Antes de empezar: Introducción al Control  
 Antes de empezar con estas instrucciones, es importante conocer y definir el uso común de un control propio. La aplicación de estilos brinda un conjunto de posibilidades que suele ser difícil de controlar. Los controles escritos para un uso general (es decir, en muchas aplicaciones y por parte de muchos desarrolladores) se enfrentan al desafío de que la aplicación de estilo puede utilizarse para realizar cambios de gran alcance en el aspecto visual del control. De hecho, el control con estilo puede no asemejarse ni siquiera a las intenciones del autor del control. Habida cuenta de que la aplicación de estilo suele ofrecer una flexibilidad sin límites, puede basarse en la idea del uso común para ayudar a definir el ámbito de sus decisiones.  
  
 Para entender el uso común del control, es conveniente pensar en la propuesta de valor del control. ¿Qué aporta este control a la tabla que no puede ofrecer ningún otro control? El uso común no conlleva ningún aspecto visual concreto, sino más bien la filosofía del control y un conjunto razonable de expectativas sobre su uso. Este conocimiento permite realizar algunas suposiciones sobre el modelo de composición y los comportamientos definidos por el estilo del control en el caso habitual. En el caso de <xref:System.Windows.Controls.ComboBox>, por ejemplo, conocer el uso común no aporta ninguna información sobre si un determinado <xref:System.Windows.Controls.ComboBox> tiene esquinas redondeadas, pero le proporcionará información sobre el hecho de que el <xref:System.Windows.Controls.ComboBox> probablemente necesita una ventana emergente y cierto nivel de alternancia si está abierto.  
  
<a name="General_Guidelines"></a>   
## <a name="general-guidelines"></a>Instrucciones generales  
  
- **No aplicar de manera estricta los contratos de plantilla.** El contrato de la plantilla de un control puede constar de elementos, comandos, enlaces, desencadenadores o incluso configuraciones de propiedades necesarios o previstos para que un control funcione correctamente.  
  
    - Minimice los contratos lo máximo posible.  
  
    - Diseño con la expectativa de que, durante el período de diseño (es decir, al usar una herramienta de diseño), es habitual que una plantilla de control presente el estado de incompleta. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no ofrece una infraestructura con el estado de "redacción", por lo que los controles deben crearse con la expectativa de que dicho estado puede ser válido.  
  
    - No lance excepciones cuando no se respeta cualquier aspecto de un contrato de plantilla. En este sentido, los paneles no deben iniciar excepciones si tienen demasiados o muy pocos elementos secundarios.  
  
- **Funcionalidad periférica de factor en elementos del asistente con plantillas.** Cada control debe centrarse en su funcionalidad principal y en su propuesta de valor verdadero, cuya definición debe realizarse según el uso común del control. Para ello, use los elementos de redacción y del asistente dentro de la plantilla, a fin de habilitar las visualizaciones y los comportamientos periféricos, es decir, aquellos comportamientos y visualizaciones que no contribuyen a la funcionalidad principal del control. Los elementos del asistente se dividen en tres categorías:  
  
    - Los tipos del asistente **independientes** son controles públicos y reutilizables o primitivos que se usan de forma "anónima" en una plantilla, lo que significa que ni el elemento del asistente ni el control con estilo tienen constancia del otro. Técnicamente, cualquier elemento puede ser un tipo anónimo, pero en este contexto, el término describe los tipos que encapsulan la funcionalidad especializada para habilitar escenarios concretos.  
  
    - Los elementos del asistente **basados en tipos** son nuevos tipos que encapsulan la funcionalidad especializada. Estos elementos se suelen diseñar con un intervalo de funcionalidad menor que los controles comunes o primitivos. A diferencia de los elementos del asistente independientes, los elementos del asistente basados en tipos son conscientes del contexto en el que se utilizan y normalmente deben compartir los datos con el control a cuya plantilla pertenecen.  
  
    - Los elementos del asistente **con nombre** son controles comunes o primitivos que un control espera encontrar por su nombre dentro de su plantilla. A estos elementos se les asigna un nombre conocido en la plantilla, de tal manera que se permite a un control encontrar el elemento e interactuar con él mediante programación. En cualquier plantilla solo puede haber un elemento con un nombre determinado.  
  
     En la tabla siguiente se muestran los elementos del asistente que hoy emplean los estilos del control, aunque no se trata de una lista exhaustiva:  
  
    |Elemento|Tipo|Utilizada por|  
    |-------------|----------|-------------|  
    |<xref:System.Windows.Controls.ContentPresenter>|Basado en tipos|<xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.Frame>, etc. (todos los <xref:System.Windows.Controls.ContentControl> tipos)|  
    |<xref:System.Windows.Controls.ItemsPresenter>|Basado en tipos|<xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.Menu>, etc. (todos los <xref:System.Windows.Controls.ItemsControl> tipos)|  
    |<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|Con nombre|<xref:System.Windows.Controls.ToolBar>|  
    |<xref:System.Windows.Controls.Primitives.Popup>|Independiente|<xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ToolBar>, <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.ToolTip>, etc.|  
    |<xref:System.Windows.Controls.Primitives.RepeatButton>|Con nombre|<xref:System.Windows.Controls.Slider>, <xref:System.Windows.Controls.Primitives.ScrollBar>, etc.|  
    |<xref:System.Windows.Controls.Primitives.ScrollBar>|Con nombre|<xref:System.Windows.Controls.ScrollViewer>|  
    |<xref:System.Windows.Controls.ScrollViewer>|Independiente|<xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.Frame>, etc.|  
    |<xref:System.Windows.Controls.Primitives.TabPanel>|Independiente|<xref:System.Windows.Controls.TabControl>|  
    |<xref:System.Windows.Controls.TextBox>|Con nombre|<xref:System.Windows.Controls.ComboBox>|  
    |<xref:System.Windows.Controls.Primitives.TickBar>|Basado en tipos|<xref:System.Windows.Controls.Slider>|  
  
- **Minimizar las configuraciones de propiedad o los enlaces especificados por el usuario necesarios en los elementos del asistente**. Es habitual que un elemento del asistente requiera determinados enlaces o configuraciones de propiedad para poder funcionar correctamente en una plantilla de control. En la medida de lo posible, el elemento del asistente y el control con plantilla deben establecer esta configuración. Al establecer propiedades o enlaces, hay que tener precaución de no invalidar los valores establecidos por el usuario. Los procedimientos recomendados específicos son los siguientes:  
  
    - Los elementos del asistente con nombre deben identificarse mediante el elemento primario, y este último debe establecer la configuración necesaria en el elemento del asistente.  
  
    - Los elementos del asistente basados en tipos deben establecer directamente en ellos mismos la configuración requerida. Para ello, es posible que el elemento del asistente deba consultar información del contexto en que se usa, incluido su `TemplatedParent` (el tipo de control de la plantilla en que se usa). Por ejemplo, <xref:System.Windows.Controls.ContentPresenter> enlaza automáticamente la `Content` propiedad de su `TemplatedParent` a su <xref:System.Windows.Controls.ContentPresenter.Content%2A> propiedad cuando se usa en un <xref:System.Windows.Controls.ContentControl> tipo derivado.  
  
    - No se pueden optimizar de esta forma los elementos del asistente independientes porque, por definición, ni el elemento del asistente ni el primario saben nada el uno del otro.  
  
- **Usar la propiedad Name para marcar los elementos dentro de una plantilla**. Un control que necesita buscar un elemento en su estilo para tener acceso a él mediante programación debe hacerlo mediante la propiedad `Name` y el paradigma `FindName`. Un control no debería producir una excepción cuando no se encuentra un elemento, pero de forma silenciosa y sencilla debe deshabilitar la funcionalidad que requiere ese elemento.  
  
- **Usar procedimientos recomendados para expresar el estado del control y el comportamiento de un estilo.** A continuación se presenta una lista ordenada de los procedimientos recomendados para expresar los cambios de estado del control y el comportamiento de un estilo. Debe usar el primer elemento de la lista que habilita su escenario.  
  
    1. Enlace de propiedades. Ejemplo: enlace entre <xref:System.Windows.Controls.ComboBox.IsDropDownOpen%2A?displayProperty=nameWithType> y <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A?displayProperty=nameWithType>.  
  
    2. Animaciones de propiedades o cambios de propiedades desencadenados. Ejemplo: el estado de desplazamiento de un <xref:System.Windows.Controls.Button>.  
  
    3. Comando. Ejemplo: <xref:System.Windows.Controls.Primitives.ScrollBar.LineUpCommand>  /  <xref:System.Windows.Controls.Primitives.ScrollBar.LineDownCommand> en <xref:System.Windows.Controls.Primitives.ScrollBar>.  
  
    4. Elementos del asistente independientes. Ejemplo: <xref:System.Windows.Controls.Primitives.TabPanel> en <xref:System.Windows.Controls.TabControl>.  
  
    5. Tipos del asistente basados en tipos. Ejemplo: <xref:System.Windows.Controls.ContentPresenter> en <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Primitives.TickBar> en <xref:System.Windows.Controls.Slider>.  
  
    6. Elementos del asistente con nombre. Ejemplo: <xref:System.Windows.Controls.TextBox> en <xref:System.Windows.Controls.ComboBox>.  
  
    7. Eventos traspasados desde los tipos del asistente con nombre. Si realiza escuchas de eventos traspasados desde un elemento de estilo, debe requerir que el elemento que genera el evento se pueda identificar de manera exclusiva. Ejemplo: <xref:System.Windows.Controls.Primitives.Thumb> en <xref:System.Windows.Controls.ToolBar>.  
  
    8. Comportamiento personalizado de `OnRender`. Ejemplo: <xref:Microsoft.Windows.Themes.ButtonChrome> en <xref:System.Windows.Controls.Button>.  
  
- **Usar desencadenadores de estilo (a diferencia de los desencadenadores de plantilla) con moderación**. Los desencadenadores que afectan a las propiedades de elementos en la plantilla se deben declarar en la plantilla. Los desencadenadores que afectan a las propiedades del control (no `TargetName`) se pueden declarar en el estilo, a menos que sepa que el cambio de la plantilla también destruye el desencadenador.  
  
- **Ser coherente con los patrones de estilo existentes.** Muchas veces, hay varias formas de resolver un problema. Debe conocer los patrones de aplicación de estilos de control existentes y, cuando sea posible, mantener la coherencia con ellos. Esto es especialmente importante para los controles que derivan del mismo tipo base (por ejemplo, <xref:System.Windows.Controls.ContentControl>, <xref:System.Windows.Controls.ItemsControl>, <xref:System.Windows.Controls.Primitives.RangeBase>, y así sucesivamente).  
  
- **Exponer propiedades para habilitar escenarios de personalización comunes sin volver a crear plantillas**. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no admite partes acoplables/personalizables, por lo que un usuario de control solo puede usar dos métodos de personalización: configurar propiedades directamente o configurar propiedades con estilos. Habida cuenta de lo anterior, resulta conveniente exponer un número limitado de propiedades orientadas a escenarios de personalización muy comunes y de alta prioridad, ya que, de lo contrario, sería necesario volver a crear plantillas. A continuación se presentan procedimientos recomendados para saber cuándo y cómo habilitar escenarios de personalización:  
  
    - Las personalizaciones muy comunes deben exponerse como propiedades en el control, a fin de que la plantilla pueda usarlas.  
  
    - Las personalizaciones menos comunes (aunque no poco habituales) deben exponerse como propiedades adjuntas que la plantilla debe usar.  
  
    - Resulta aceptable que sea necesario volver a crear plantillas en el caso de las personalizaciones conocidas pero poco habituales.  
  
<a name="Theme_Considerations"></a>   
## <a name="theme-considerations"></a>Consideraciones sobre temas  
  
- **Los estilos de temas deben tratar de tener una semántica de propiedades coherente en todos los temas, pero sin garantizarlo**. Como parte de su documentación, el control debe tener un documento en que se describa la semántica de la propiedad del control, es decir, el "significado" de una propiedad para un control. Por ejemplo, el <xref:System.Windows.Controls.ComboBox> control debe definir el significado de la <xref:System.Windows.Controls.Control.Background%2A> propiedad dentro de <xref:System.Windows.Controls.ComboBox>. Los estilos predeterminados del control deben intentar seguir la semántica definida en ese documento en todos los temas. Por otro lado, los usuarios del control deben ser conscientes de que la semántica de la propiedad puede cambiar de un tema a otro. En algunos casos, es posible que una propiedad determinada no pueda expresarse dentro de las restricciones visuales requeridas por un tema concreto. (Por ejemplo, el tema Clásico no tiene un solo borde en el que `Thickness` se puede aplicar a muchos controles).  
  
- **Los estilos de temas no necesitan tener una semántica de desencadenadores coherente en todos los temas**. El comportamiento expuesto por un estilo de control mediante desencadenadores o animaciones puede variar de un tema a otro. Los usuarios del control deben ser conscientes de que un control no usará necesariamente el mismo mecanismo para lograr un comportamiento concreto en todos los temas. Un tema, por ejemplo, puede usar una animación para expresar el comportamiento de selección mediante movimiento del mouse mientras que otro tema usa un desencadenador. Esto puede provocar incoherencias en la conservación del comportamiento en los controles personalizados. (Cambiar la propiedad de segundo plano, por ejemplo, podría no afectar al estado de selección mediante movimiento del mouse del control si dicho estado se expresa mediante un desencadenador. Sin embargo, si el estado se implementa utilizando una animación, cambiar a segundo plano podría interrumpir irreparablemente la animación y, por lo tanto, la transición de estado).  
  
- **Los estilos de temas no necesitan tener una semántica de "diseño" coherente en todos los temas**. Por ejemplo, el estilo predeterminado no necesita garantizar que un control puede ocupar el mismo tamaño en todos los temas o garantizar que un control tendrá los mismos márgenes de contenido o espaciado interno en todos los temas.  
  
## <a name="see-also"></a>Vea también

- [Aplicar estilos y plantillas](styling-and-templating.md)
- [Información general sobre la creación de controles](control-authoring-overview.md)
