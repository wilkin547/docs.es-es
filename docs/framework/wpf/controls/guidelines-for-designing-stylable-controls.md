---
title: "Instrucciones para el dise&#241;o de controles con estilos | Microsoft Docs"
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
  - "controles, diseño de estilos"
  - "diseño de estilos para controles"
ms.assetid: c52dde45-a311-4531-af4c-853371c4d5f4
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Instrucciones para el dise&#241;o de controles con estilos
Este documento resume un conjunto de procedimientos recomendados que se debe tener en cuenta al diseñar un control con estilos y plantillas de fácil uso.  Los vimos a través de muchas pruebas y errores al trabajar en los estilos del control de tema del conjunto del control integrado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Aprendimos que un estilo correcto está formado tanto por una función de un modelo de objetos bien diseñado como por el propio estilo.  El lector al que está dirigido este documento es el autor del control, y no el autor del estilo.  
  
   
  
<a name="Terminology"></a>   
## Terminología  
 "Diseño de estilos y plantillas" hace referencia al conjunto de tecnologías que permiten al autor de un control transferir los aspectos visuales de éste a su estilo y plantilla.  Este conjunto de tecnologías incluye los siguientes elementos:  
  
-   Estilos \(incluidos los establecedores de propiedades, los desencadenadores y los guiones gráficos\).  
  
-   Recursos.  
  
-   Plantillas de control.  
  
-   Plantillas de datos.  
  
 Para obtener una introducción al diseño de estilos y plantillas, vea [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
<a name="Before_You_Start__Understanding_Your_Control"></a>   
## Antes de empezar: introducción al control  
 Antes de pasar a las instrucciones, es importante entender el control y haber definido su uso común.  El diseño de estilos expone un conjunto de posibilidades que suele ser difícil de controlar.  Los controles que se escriben para usarlos mucho \(en muchas aplicaciones, por muchos programadores\) se enfrentan al desafío de que el diseño de estilos se puede utilizar para efectuar cambios difíciles de conseguir en el aspecto visual del control.  De hecho, puede que el control con estilos no se parezca en absoluto a la idea inicial de su autor.  Puesto que la flexibilidad proporcionada por los estilos es básicamente ilimitada, puede usar la idea de uso común para ayudarle a delimitar el ámbito de sus decisiones.  
  
 Para entender el uso común del control, es práctico pensar en la finalidad del mismo.  ¿Qué aporta el control a la tabla que no pueda aportar ningún otro control?  El uso común no implica ningún aspecto visual concreto, sino más bien la filosofía del control y un conjunto razonable de expectativas de uso.  Esta comprensión permite plantearse algunas suposiciones sobre el modelo de la composición y los comportamientos definidos por estilo del control en el caso común.  En el caso de <xref:System.Windows.Controls.ComboBox>, por ejemplo, entender el uso común no le ayudará a formarse una idea sobre si un objeto <xref:System.Windows.Controls.ComboBox> concreto tiene las esquinas redondeadas, pero sí lo hará sobre el hecho de que <xref:System.Windows.Controls.ComboBox>, probablemente, necesite una ventana emergente y algo de alternancia si está abierto.  
  
<a name="General_Guidelines"></a>   
## Instrucciones generales  
  
-   **No aplique el proceso de desarrollo de la plantilla de manera estricta.** El proceso de desarrollo de la plantilla de un control podría estar formado por elementos, comandos, enlaces, desencadenadores o incluso los valores de propiedades necesarios o esperados de un control para que funcione correctamente.  
  
    -   Simplifique el desarrollo al máximo posible.  
  
    -   El diseño basado en las expectativas del tiempo de diseño \(es decir, al usar una herramienta de diseño\) tiene como resultado una plantilla de control cuyo estado es incompleto.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no proporciona ninguna infraestructura de estado de "creación"; por tanto, los controles se deben crear con la expectativa de que tal estado pudiera ser válido.  
  
    -   No produzca excepciones cuando no se siga un aspecto cualquiera de un diseño de plantilla.  En estas líneas, los paneles no deben producir excepciones si tienen demasiados elementos secundarios o muy pocos.  
  
-   **Tenga en cuenta la funcionalidad periférica de los elementos de la aplicación auxiliar de la plantilla.** Los controles se deben basar en su funcionalidad básica y en propuestas reales, y definir mediante el uso común del control.  Para ello, utilice los elementos de creación y de la aplicación auxiliar en la plantilla para habilitar comportamientos y visualizaciones periféricos; es decir, los comportamientos y visualizaciones que no contribuyen a la funcionalidad básica del control.  Los elementos de la aplicación auxiliar se clasifican en tres categorías:  
  
    -   Los tipos de la aplicación auxiliar **independientes** son controles públicos y reutilizables o primitivos que se usan "anónimamente" en una plantilla; es decir, ni el elemento de la aplicación auxiliar ni el control con estilo se dan cuenta de la existencia del otro.  Técnicamente, el tipo de cualquier elemento puede ser anónimo pero, en este contexto, el término describe los tipos que encapsulan la funcionalidad especializada para habilitar escenarios concretos.  
  
    -   Los elementos de aplicación auxiliar **basados en tipo** son nuevos tipos que encapsulan la funcionalidad especializada.  Estos elementos se suelen diseñar con un intervalo de funcionalidad menor que los controles comunes o primitivos.  A diferencia de los elementos de la aplicación auxiliar independientes, los elementos de aplicación auxiliar basados en tipo son conscientes del contexto en el que se usan y, normalmente, deben compartir los datos con el control a cuya plantilla pertenecen.  
  
    -   Los elementos de aplicación auxiliar **con nombre** son controles comunes o primitivos que un control espera encontrar por su nombre dentro de la plantilla. A estos elementos se les asigna un nombre conocido dentro de la plantilla, lo que hace posible que un control encuentre el elemento e interactúe con él mediante programación.  Puede haber sólo uno elemento con un nombre concreto en una plantilla cualquiera.  
  
     En la tabla siguiente, se muestran los elementos de aplicación auxiliar usados por los estilos de control actuales \(esta lista no es una lista completa\):  
  
    |Elemento|Tipo|Utilizado por|  
    |--------------|----------|-------------------|  
    |<xref:System.Windows.Controls.ContentPresenter>|Basado en tipo|<xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.Frame>, etc. \(todos los tipos de <xref:System.Windows.Controls.ContentControl>\)|  
    |<xref:System.Windows.Controls.ItemsPresenter>|Basado en tipo|<xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.Menu>, etc. \(todos los tipos de <xref:System.Windows.Controls.ItemsControl>\)|  
    |<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|Con nombre|<xref:System.Windows.Controls.ToolBar>|  
    |<xref:System.Windows.Controls.Primitives.Popup>|Independiente|<xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ToolBar>, <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.ToolTip>, etc.|  
    |<xref:System.Windows.Controls.Primitives.RepeatButton>|Con nombre|<xref:System.Windows.Controls.Slider>, <xref:System.Windows.Controls.Primitives.ScrollBar>, etc.|  
    |<xref:System.Windows.Controls.Primitives.ScrollBar>|Con nombre|<xref:System.Windows.Controls.ScrollViewer>|  
    |<xref:System.Windows.Controls.ScrollViewer>|Independiente|<xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.Frame>, etc.|  
    |<xref:System.Windows.Controls.Primitives.TabPanel>|Independiente|<xref:System.Windows.Controls.TabControl>|  
    |<xref:System.Windows.Controls.TextBox>|Con nombre|<xref:System.Windows.Controls.ComboBox>|  
    |<xref:System.Windows.Controls.Primitives.TickBar>|Basado en tipo|<xref:System.Windows.Controls.Slider>|  
  
-   **Reduzca el número necesario de enlaces especificados por el usuario o los valores de las propiedades de los elementos de la aplicación auxiliar**.  Es normal que un elemento de aplicación auxiliar requiera algunos valores de enlaces o de propiedades para funcionar correctamente en la plantilla del control.  El elemento de la aplicación auxiliar y el control con plantilla deben establecer estos valores en la medida de lo posible.  Al establecer propiedades o enlaces, cuidado, se debe tener cuidado para no invalidar los valores establecidos por el usuario.  Los procedimientos recomendados específicos son los siguientes:  
  
    -   Los elementos de la aplicación auxiliar con nombre los debe identificar el elemento primario y éste debe establecer cualquier valor necesario del elemento de la aplicación auxiliar.  
  
    -   Los elementos de la aplicación auxiliar basados en tipo deben establecer los valores necesarios directamente en sí mismos.  De esta forma, quizá el elemento de la aplicación auxiliar deba consultar el contexto de la información en la que se usa, incluido su `TemplatedParent` \(el tipo de control de la plantilla en la que se utiliza\).  Por ejemplo, <xref:System.Windows.Controls.ContentPresenter> enlaza automáticamente la propiedad `Content` de su `TemplatedParent` a su propiedad <xref:System.Windows.Controls.ContentPresenter.Content%2A> cuando se usa en un tipo derivado de <xref:System.Windows.Controls.ContentControl>.  
  
    -   Los elementos de la aplicación auxiliar independientes no se pueden optimizar de esta manera porque, por definición, ni el elemento de aplicación auxiliar ni el primario saben que existe el otro.  
  
-   **Use la propiedad Name para marcar los elementos de una plantilla**.  Un control que necesite buscar un elemento en su estilo para tener acceso a él mediante programación debe hacerlo con la propiedad `Name` y el ejemplo de `FindName`.  Un control no debe producir ninguna excepción cuando no se encuentre un elemento, sino deshabilitar correctamente la funcionalidad que requería ese elemento.  
  
-   **Utilice los procedimientos recomendados para expresar el estado del control y el comportamiento de un estilo.** A continuación, se muestra una lista ordenada de los procedimientos recomendados para expresar los cambios del estado del control y de comportamiento de un estilo.  Debe utilizar el primer elemento de la lista que habilita su escenario.  
  
    1.  Enlace de Propiedad.  Ejemplo: enlace entre <xref:System.Windows.Controls.ComboBox.IsDropDownOpen%2A?displayProperty=fullName> y <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A?displayProperty=fullName>.  
  
    2.  Cambios de propiedad desencadenados o animaciones de propiedad.  Ejemplo: estado de desplazamiento del puntero de <xref:System.Windows.Controls.Button>.  
  
    3.  Comando.  Ejemplo: <xref:System.Windows.Controls.Primitives.ScrollBar.LineUpCommand> \/ <xref:System.Windows.Controls.Primitives.ScrollBar.LineDownCommand> de <xref:System.Windows.Controls.Primitives.ScrollBar>.  
  
    4.  Elementos independientes de la aplicación auxiliar.  Ejemplo: <xref:System.Windows.Controls.Primitives.TabPanel> de <xref:System.Windows.Controls.TabControl>.  
  
    5.  Tipos de aplicación auxiliar basados en tipo.  Ejemplo: <xref:System.Windows.Controls.ContentPresenter> de <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Primitives.TickBar> de <xref:System.Windows.Controls.Slider>.  
  
    6.  Elementos con nombre de la aplicación auxiliar.  Ejemplo: <xref:System.Windows.Controls.TextBox> de <xref:System.Windows.Controls.ComboBox>.  
  
    7.  Eventos traspasados desde los tipos con nombre de la aplicación auxiliar.  Si realiza escuchas de eventos traspasados desde un elemento de estilo, es necesario que se pueda identificar exclusivamente el elemento que genera el evento.  Ejemplo: <xref:System.Windows.Controls.Primitives.Thumb> de <xref:System.Windows.Controls.ToolBar>.  
  
    8.  Personalice el comportamiento de `OnRender`.  Ejemplo: <xref:Microsoft.Windows.Themes.ButtonChrome> de <xref:System.Windows.Controls.Button>.  
  
-   **Utilice desencadenadores de estilo \(en contraposición a los desencadenadores de plantilla\) con moderación**.  Los desencadenadores que afectan las propiedades de los elementos de la plantilla se deben declarar en la plantilla.  Los desencadenadores que afectan las propiedades del control \(sin `TargetName`\) se pueden declarar en el estilo a menos que sepa que al cambiar la plantilla, también se destruye el desencadenador.  
  
-   **Sea coherente con los modelos de estilo existentes.** Muchas veces existen varias formas de resolver un problema.  Tenga en cuenta y sea coherente con los modelos de los estilos de un control existente en la medida de lo posible.  Esto es especialmente importante para los controles que se derivan del mismo tipo base \(por ejemplo, <xref:System.Windows.Controls.ContentControl>, <xref:System.Windows.Controls.ItemsControl>, <xref:System.Windows.Controls.Primitives.RangeBase>, etc.\).  
  
-   **Exponga las propiedades para habilitar los escenarios de personalización comunes sin volver a crear plantillas**.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no admite las partes que se pueden conectar o personalizar; por tanto, al usuario de un control le quedan solo dos métodos de personalización: establecer las propiedades directamente o mediante estilos.  Teniendo esto presente, es correcto exponer un número limitado de propiedades cuyo destino sean escenarios de personalización muy comunes y prioritarios que, de otro modo, requerirían volver a crear las plantillas.  A continuación se detallan los procedimientos recomendados para el momento en el que se habilitan los escenarios de personalización y cómo se habilitan:  
  
    -   Las personalizaciones muy comunes se deben exponer como propiedades del control y las debe usar la plantilla.  
  
    -   Las personalizaciones menos comunes \(aunque no raras\) se deben exponer como propiedades adjuntas y las debe usar la plantilla.  
  
    -   Es aceptable que las personalizaciones conocidas pero raras requieran que se vuelva a crear la plantilla.  
  
<a name="Theme_Considerations"></a>   
## Consideraciones del tema  
  
-   **Los estilos del tema deben intentar ser coherentes con la semántica de la propiedad en todos los temas, pero sin garantizarlo**.  Como parte de su documentación, el control debe tener un documento que describa la semántica de la propiedad del control; es decir, el "significado" de una propiedad de un control.  Por ejemplo, el control <xref:System.Windows.Controls.ComboBox> debe definir el significado de la propiedad <xref:System.Windows.Controls.Control.Background%2A> dentro de <xref:System.Windows.Controls.ComboBox>.  Los estilos predeterminados del control deben intentar seguir la semántica definida en ese documento en todos los temas.  Los usuarios del control, por otra parte, deben tener en cuenta que la semántica de la propiedad puede cambiar de un tema a otro.  En algunos casos, una propiedad especificada no se puede expresar en las restricciones visuales requeridas por un tema concreto.  \(Por ejemplo, el tema Clásico no tiene ni un solo borde al que se pueda aplicar `Thickness` para muchos controles.\)  
  
-   **Los estilos del tema no tienen que ser coherentes con la semántica del desencadenador en todos los temas**.  El comportamiento expuesto por un estilo de control a través de los desencadenadores o animaciones puede variar de un tema a otro.  Los usuarios del control deben tener en cuenta que un control no usará necesariamente el mismo mecanismo para lograr un comportamiento concreto en todos los temas.  Por ejemplo, un tema puede usar una animación para expresar el comportamiento de desplazamiento del puntero mientras que otro usa un desencadenador.  De esta forma, se pueden producir incoherencias en la conservación del comportamiento en los controles personalizados.  \(Si se cambia la propiedad de segundo plano, por ejemplo, puede que no afecte el estado de desplazamiento del puntero del control si dicho estado se expresa con un desencadenador.  Sin embargo, si este estado se implementa utilizando una animación, al cambiar a segundo plano, se podría interrumpir irremediablemente la animación y, por consiguiente, la transición de estado.\)  
  
-   **Los estilos del tema no tiene que ser coherentes con la semántica del "diseño" en todos los temas**.  Por ejemplo, el estilo predeterminado no tiene que garantizar que un control vaya a tener el mismo tamaño en todos los temas ni que un control vaya a tener los mismos márgenes o relleno de contenido en todos los temas.  
  
## Vea también  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md)