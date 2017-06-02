---
title: "C&#243;mo: Agregar un controlador de eventos mediante c&#243;digo | Microsoft Docs"
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
  - "controladores de eventos, agregar"
  - "XAML, agregar controladores de eventos"
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Agregar un controlador de eventos mediante c&#243;digo
En este ejemplo se muestra cómo agregar un controlador de eventos a un elemento mediante código.  
  
 Si desea agregar un controlador de eventos a un elemento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], y se ha cargado ya la página de marcado que contiene el elemento, debe agregar el controlador mediante código.  Como alternativa, si está construyendo el árbol de elementos para una aplicación mediante código solamente y no se declara ningún elemento mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], puede llamar a métodos concretos para agregar controladores de eventos al árbol de elementos construido.  
  
## Ejemplo  
 En el ejemplo siguiente se agrega un nuevo <xref:System.Windows.Controls.Button> a una página existente que se define inicialmente en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Un archivo de código subyacente implementa un método de control de eventos y, a continuación, agrega ese método como un nuevo controlador de eventos de <xref:System.Windows.Controls.Button>.  
  
 En el ejemplo de [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)] se utiliza el operador `+=` para asignar un controlador a un evento.  Se trata del mismo operador que se utiliza para asignar un controlador en el modelo de control de eventos [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)].  [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] no admite a este operador para la adición de controladores de eventos.  En su lugar, requiere una de estas dos técnicas:  
  
-   Utilice el método <xref:System.Windows.UIElement.AddHandler%2A>, junto con un operador `AddressOf`, para hacer referencia a la implementación del controlador de eventos.  
  
-   Utilice la palabra clave `Handles` como parte de la definición del controlador de eventos.  Esta técnica no se muestra aquí; vea [Control de eventos en Visual Basic y WPF](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
 [!code-xml[RoutedEventAddRemoveHandler#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  Agregar un controlador de eventos en la página [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] analizada inicialmente es mucho más sencillo.  Dentro del elemento de objeto donde desea agregar el controlador de eventos, agregue un atributo que coincida con el nombre del evento que desea controlar.  A continuación, especifique el valor de ese atributo como el nombre del método de control de eventos que definió en el archivo de código subyacente de la página [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Para obtener más información, vea [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) o [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
## Vea también  
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)