---
title: "Control de eventos en Visual Basic y WPF | Microsoft Docs"
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
  - "controladores de eventos, Visual Basic"
  - "Visual Basic, controladores de eventos"
ms.assetid: ad4eb9aa-3afc-4a71-8cf6-add3fbea54a1
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Control de eventos en Visual Basic y WPF
En concreto para el lenguaje [!INCLUDE[TLA#tla_visualbnet](../../../../includes/tlasharptla-visualbnet-md.md)], puede utilizar la palabra clave `Handles` específica del lenguaje para asociar controladores de eventos a instancias, en lugar de asociar controladores de eventos a atributos o de utilizar el método <xref:System.Windows.UIElement.AddHandler%2A>.  Sin embargo, la técnica de `Handles` para adjuntar controladores a instancias tiene algunas limitaciones, porque la sintaxis de `Handles` no puede admitir algunas de las características específicas de [evento enrutado](GTMT) del sistema de eventos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
## Utilizar "Handles" en un aplicación de WPF  
 Los controladores de eventos que se conectan a instancias y eventos mediante `Handles` se deben definir dentro de la declaración de clase parcial de la instancia; este requisito también se aplica a los controladores de eventos que se asignan a través de valores de atributo de elementos.  Sólo puede especificar `Handles` para un elemento en la página que tiene un valor de propiedad <xref:System.Windows.FrameworkContentElement.Name%2A> \(o el [x:Name \(Directiva\)](../../../../docs/framework/xaml-services/x-name-directive.md) declarado\).  Esto es porque la propiedad <xref:System.Windows.FrameworkContentElement.Name%2A> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] crea la referencia de instancia necesaria para admitir el formato de referencia *Instancia.Evento* que la sintaxis de `Handles` requiere.  El único elemento que se puede utilizar para `Handles` sin una referencia a <xref:System.Windows.FrameworkContentElement.Name%2A> es la instancia del elemento raíz que define la clase parcial.  
  
 Puede asignar el mismo controlador a varios elementos separando las referencias *Instancia.Evento* que aparecen después de `Handles` con comas.  
  
 Puede utilizar `Handles` para asignar más de un controlador a la misma referencia *Instancia.Evento*.  No asigne importancia al orden en el que se proporcionan los controladores en la referencia de `Handles`; suponga que los controladores que controlan el mismo evento se pueden invocar en cualquier orden.  
  
 Para quitar un controlador que se agregó con `Handles` en la declaración, puede llamar a <xref:System.Windows.UIElement.RemoveHandler%2A>.  
  
 Puede utilizar `Handles` para asociar controladores para [eventos enrutados](GTMT), siempre que asocie los controladores a las instancias que definen el evento controlado en sus tablas de miembros.  Para los [eventos enrutados](GTMT), los controladores que se asocian con `Handles` siguen las mismas reglas de enrutamiento que los asociados como atributos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o con la firma común de <xref:System.Windows.UIElement.AddHandler%2A>.  Esto significa que si el evento está marcado ya como controlado \(la propiedad <xref:System.Windows.RoutedEventArgs.Handled%2A> de los datos de evento es `True`\), entonces los controladores asociados con `Handles` no se invocan en respuesta a esa instancia de evento.  El evento podría marcarse como controlado por controladores de instancia en otro elemento de la ruta, o por el control de clases del elemento actual o de otros anteriores en la ruta.  Para los eventos de entrada que admiten eventos emparejados de tunelización y propagación, la ruta de túnel puede haber marcado como controlado el par de eventos.  Para obtener más información acerca de los eventos enrutados, vea [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
## Limitaciones de "Handles" para la adición de controladores  
 `Handles` no puede hacer referencia a los controladores correspondientes a [eventos adjuntos](GTMT).  Debe utilizar el método de descriptor de acceso `add` para ese evento adjunto o atributos de evento *nombreDeTipo.nombreDeEvento* en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Para obtener información detallada, vea [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 Para los [eventos enrutados](GTMT), únicamente se puede usar `Handles` para asignar controladores para instancias para las que ese evento exista en la tabla de miembros de instancia.  Sin embargo, con los eventos enrutados en general, un elemento primario puede ser un agente de escucha para un evento a partir de los elementos secundarios, aunque el elemento primario no tenga ese evento en su tabla de miembros.  En la sintaxis de atributo, puede especificar esto mediante un atributo en formato *nombreDeTipo.nombreDeMiembro* que certifica cuál de los tipos define en realidad el evento que desea controlar.  Por ejemplo, un elemento `Page` primario \(sin ningún evento `Clic`k definido\) puede realizar escuchas para eventos del clic de botón asignando un controlador de atributo en formato `Button.Click`.  Sin embargo, `Handles` no admite el formato *nombreDeTipo.nombreDeMiembro*, porque debe admitir un formato de *Instancia.Evento* en conflicto.  Para obtener información detallada, vea [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 `Handles` no puede asociar controladores que se invocan para eventos que ya están marcados como controlados.  En su lugar, debe utilizar código y llamar a la sobrecarga `handledEventsToo` del método <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29>.  
  
> [!NOTE]
>  No utilice la sintaxis `Handles` en el código [!INCLUDE[vb_current_short](../../../../includes/vb-current-short-md.md)] al especificar un controlador de eventos para el mismo evento en XAML.  En este caso, se llama al controlador de eventos dos veces.  
  
## Cómo implementa WPF la funcionalidad de "Handles"  
 Al compilar una página [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], el archivo intermedio declara referencias `Friend``WithEvents` a todos los elementos de la página cuya propiedad <xref:System.Windows.FrameworkContentElement.Name%2A> está establecida \(o cuyo [x:Name \(Directiva\)](../../../../docs/framework/xaml-services/x-name-directive.md) se ha declarado\).  Cada instancia con nombre es potencialmente un elemento que se puede asignar a un controlador a través de `Handles`.  
  
> [!NOTE]
>  Dentro de [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], [!INCLUDE[TLA2#tla_intellisense](../../../../includes/tla2sharptla-intellisense-md.md)] puede completar los elementos que están disponibles una referencia a `Handles` de una página.  Sin embargo, podría necesitarse un paso de compilación para que el archivo intermedio rellene todas las referencias `Friends`.  
  
## Vea también  
 <xref:System.Windows.UIElement.AddHandler%2A>   
 [Marcar eventos enrutados como controlados y control de clases](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)   
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)