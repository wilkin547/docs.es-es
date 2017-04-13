---
title: "Informaci&#243;n general sobre eventos adjuntos | Microsoft Docs"
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
  - "eventos adjuntos [WPF], definición"
  - "eventos adjuntos [WPF], escenarios para"
  - "eventos adjuntos y eventos enrutados [WPF]"
  - "respaldar eventos adjuntos con eventos enrutados [WPF]"
  - "definir eventos adjuntos como eventos enrutados [WPF]"
  - "controlar eventos adjuntos [WPF]"
ms.assetid: 2c40eae3-80e4-4a45-ae09-df6c9ab4d91e
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Informaci&#243;n general sobre eventos adjuntos
[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] define un componente de lenguaje y un tipo de evento denominado *evento adjunto*.  El concepto de evento adjunto permite agregar un controlador correspondiente a un evento determinado a un elemento arbitrario, en lugar de al elemento que realmente define o hereda el evento.  En este caso, ni el objeto que genera potencialmente el evento ni la instancia de control de destino definen ni "poseen" el evento de ningún modo.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="prerequisites"></a>   
## Requisitos previos  
 En este tema se supone que el usuario ha leído [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md) y [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
<a name="Syntax"></a>   
## Sintaxis de eventos adjuntos  
 Los eventos adjuntos tienen una sintaxis [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y un modelo de codificación que es preciso utilizar en el código de respaldo para admitir el uso de este tipo de eventos.  
  
 En la sintaxis [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], el evento adjunto no se especifica sólo por su nombre de evento, sino por su tipo poseedor y su nombre de evento, separados por un punto \(.\).  Dado que el nombre de evento se certifica con el nombre de su tipo poseedor, la sintaxis de eventos adjuntos permite asociar cualquier evento a cualquier elemento del que se puedan crear instancias.  
  
 Por ejemplo, a continuación se muestra la sintaxis [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para asociar un controlador para un evento adjunto personalizado, `NeedsCleaning`:  
  
 [!code-xml[WPFAquariumSln#AE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquarium/Window1.xaml#ae)]  
  
 Observe el prefijo `aqua:`, que es necesario en este caso porque el evento adjunto es un evento personalizado que procede de un xmlns asignado personalizado.  
  
<a name="WPFImplements"></a>   
## Cómo se implementan los eventos adjuntos en WPF  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], los eventos adjuntos están respaldados por un campo <xref:System.Windows.RoutedEvent> y se enrutan a través del árbol después de generarse.  Normalmente, el origen del evento adjunto \(el objeto que genera el evento\) es un origen del sistema o de servicio; en consecuencia, el objeto que ejecuta el código que genera el evento no forma parte directa del árbol de elementos.  
  
<a name="Scenarios"></a>   
## Escenarios para los eventos adjuntos  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], los eventos adjuntos están presentes en algunas áreas de características donde existe la abstracción de nivel de servicio, por ejemplo, para los eventos habilitados por la clase <xref:System.Windows.Input.Mouse> estática o por la clase <xref:System.Windows.Controls.Validation>.  Las clases que interactúan con el servicio o que lo utilizan pueden usar el evento en la sintaxis de eventos adjuntos o bien exponer el evento adjunto como evento enrutado que forma parte de la integración de la clase en las funciones del servicio.  
  
 Aunque [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] define varios eventos adjuntos, los escenarios donde los utilizará o controlará directamente son muy limitados.  En general, el evento adjunto sirve para algún fin de la arquitectura, pero luego se reenvía a un evento enrutado no asociado \(respaldado por un "contenedor" de evento [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\).  
  
 Por ejemplo, el evento adjunto <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=fullName> subyacente se puede controlar más fácilmente en cualquier <xref:System.Windows.UIElement> determinado utilizando <xref:System.Windows.UIElement.MouseDown> en ese <xref:System.Windows.UIElement> en lugar de emplear sintaxis de eventos adjuntos en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o en código.  El evento adjunto sirve para fines de la arquitectura, porque permite la expansión futura de los dispositivos de entrada.  El dispositivo hipotético sólo necesitaría generar <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=fullName> para simular una entrada del mouse y no necesitaría derivar de la clase <xref:System.Windows.Input.Mouse> para ello.  Sin embargo, este escenario implica el control de eventos mediante código, y el control mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] del evento adjunto no es pertinente a este escenario.  
  
<a name="Handling"></a>   
## Administrar eventos adjuntos en WPF  
 El proceso de control de eventos adjuntos y el código de controlador que se escribe son, básicamente, iguales que para un evento enrutado.  
  
 En general, un evento adjunto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no se diferencia mucho de un evento enrutado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Las diferencias residen en cómo se origina el evento y en cómo lo expone como miembro una clase \(lo que también afecta a la sintaxis de controlador en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\).  
  
 Sin embargo, como se indica anteriormente, los eventos adjuntos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] existentes no están destinados en particular al control en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Casi siempre, la finalidad del evento es permitir que un elemento compuesto informe de un estado a un elemento primario en la composición de controles, en cuyo caso el evento se suele generar mediante código y, además, se basa en la administración de clases de la clase primaria pertinente.  Por ejemplo, se espera que los elementos de <xref:System.Windows.Controls.Primitives.Selector> provoquen el evento adjunto <xref:System.Windows.Controls.Primitives.Selector.Selected>, que es administrado por la clase <xref:System.Windows.Controls.Primitives.Selector>; a continuación, es posible que la clase <xref:System.Windows.Controls.Primitives.Selector> lo convierta en un evento enrutado diferente, <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>.  Para obtener más información sobre el control de eventos enrutados y la administración de clases, vea [Marcar eventos enrutados como controlados y control de clases](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md).  
  
<a name="Custom"></a>   
## Definir sus propios eventos adjuntos como eventos enrutados  
 Si deriva de las clases base comunes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], puede implementar sus propios eventos adjuntos incluyendo determinados métodos de modelo en la clase y utilizando métodos de utilidad que ya están presentes en las clases base.  
  
 El modelo es el siguiente:  
  
-   Un método `Add*Handler` con dos parámetros.  El primer parámetro debe identificar el evento y el evento identificado debe coincidir con nombres que tengan \* en el nombre de método.  El segundo parámetro es el controlador que se va a agregar.  El método debe ser público y estático, sin ningún valor devuelto.  
  
-   Un método `Remove*Handler` con dos parámetros.  El primer parámetro debe identificar el evento y el evento identificado debe coincidir con nombres que tengan \* en el nombre de método.  El segundo parámetro es el controlador que se va a quitar.  El método debe ser público y estático, sin ningún valor devuelto.  
  
 El método de descriptor de acceso `Add*Handler` facilita el procesamiento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] cuando se declaran atributos de controlador de eventos adjuntos en un elemento.  Los métodos `Add*Handler` y `Remove*Handler` también permiten el acceso mediante código al almacén de controladores de eventos del evento adjunto.  
  
 Este modelo general no es lo bastante preciso para la implementación práctica en un marco de trabajo, porque cada implementación de lector de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] podría tener esquemas diferentes para identificar los eventos subyacentes en el lenguaje y la arquitectura de respaldo.  Esta es una de las razones por las que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementa los eventos adjuntos como eventos enrutados; el identificador que debe utilizarse para un evento \(<xref:System.Windows.RoutedEvent>\) ya está definido por el sistema de eventos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Asimismo, enrutar un evento constituye una extensión natural de la implementación en el concepto de nivel de lenguaje de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de un evento adjunto.  
  
 La implementación de `Add*Handler` para un evento adjunto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] está compuesto de una llamada a <xref:System.Windows.UIElement.AddHandler%2A> con el evento enrutado y el controlador como argumentos.  
  
 En general, esta estrategia de implementación y el sistema de eventos enrutados restringen el control de los eventos adjuntos a las clases derivadas de <xref:System.Windows.UIElement> o de <xref:System.Windows.ContentElement>, porque sóloo ellas tienen implementaciones de <xref:System.Windows.UIElement.AddHandler%2A>.  
  
 Por ejemplo, en el código siguiente se define el evento adjunto `NeedsCleaning` de la clase propietaria `Aquarium`; para ello se utiliza la estrategia de eventos adjuntos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consistente en declarar el evento adjunto como evento enrutado.  
  
 [!code-csharp[WPFAquariumSln#AECode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#aecode)]
 [!code-vb[WPFAquariumSln#AECode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#aecode)]  
  
 Observe que el método utilizado para establecer el campo de identificador del evento adjunto, <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>, es en realidad el mismo método que se utiliza para registrar un evento enrutado no asociado.  Tanto los eventos adjuntos como los eventos enrutados se registran en un almacén interno centralizado.  Esta implementación de almacén de eventos permite la consideración conceptual de "uso de eventos como interfaces" que se describe en [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
<a name="Raising"></a>   
## Generar un evento adjunto de WPF  
 Normalmente, no es necesario generar los eventos adjuntos existentes definidos en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante código.  Estos eventos siguen el modelo conceptual general de "servicio", donde las responsables de generar los eventos son las clases de servicio, como <xref:System.Windows.Input.InputManager>.  
  
 Sin embargo, si define un evento adjunto personalizado basado en el modelo de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consistente en basar los eventos adjuntos en eventos enrutados \(<xref:System.Windows.RoutedEvent>\), puede utilizar <xref:System.Windows.UIElement.RaiseEvent%2A> para generar un evento adjunto de cualquier objeto <xref:System.Windows.UIElement> o <xref:System.Windows.ContentElement>.  Para generar un evento enrutado \(adjunto o no\) es preciso declarar un elemento concreto del árbol de elementos como origen del evento; este origen se comunica como llamador del método <xref:System.Windows.UIElement.RaiseEvent%2A>.  Determinar qué elemento se comunica como origen en el árbol es responsabilidad del servicio.  
  
## Vea también  
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Detalles de la sintaxis XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)   
 [Clases XAML y personalizadas para WPF](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)