---
title: "C&#243;mo: Controlar un evento enrutado | Microsoft Docs"
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
  - "propagar eventos"
  - "eventos enrutados, controlar"
ms.assetid: 157787b4-f469-4047-8777-5b034145f32e
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# C&#243;mo: Controlar un evento enrutado
En este ejemplo se muestra cómo funcionan los eventos de [propagación](GTMT) y cómo se escribe un controlador capaz de procesar los datos del [evento enrutado](GTMT).  
  
## Ejemplo  
 En [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], los elementos se organizan organizados en una estructura de [árbol de elementos](GTMT).  El elemento primario puede participar en el control de los eventos provocados inicialmente por elementos secundarios del árbol de elementos.  Esto es posible gracias al [enrutamiento de eventos](GTMT).  
  
 Los eventos enrutados suelen seguir una de las dos estrategias de enrutamiento, [propagación](GTMT) o [túnel](GTMT).  Este ejemplo se centra en el evento de [propagación](GTMT) y utiliza el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click?displayProperty=fullName> para mostrar cómo funciona el enrutamiento.  
  
 En el ejemplo siguiente se crean dos controles <xref:System.Windows.Controls.Button> y se utiliza la sintaxis de atributo de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para adjuntar un controlador de eventos a un elemento primario común, que en este ejemplo es <xref:System.Windows.Controls.StackPanel>.  En lugar de asociar los controladores de eventos individuales a cada elemento secundario <xref:System.Windows.Controls.Button>, en el ejemplo se utiliza la sintaxis de atributo para asociar el controlador de eventos al elemento primario <xref:System.Windows.Controls.StackPanel>.  Este modelo de control de eventos muestra cómo utilizar el enrutamiento de eventos como técnica para reducir el número de elementos a los que se asocia un controlador.  Todos los eventos de [propagación](GTMT) de cada <xref:System.Windows.Controls.Button> se enrutan a través del elemento primario.  
  
 Observe que en el elemento primario <xref:System.Windows.Controls.StackPanel>, el nombre del evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> especificado como atributo se certifica parcialmente nombrando la clase <xref:System.Windows.Controls.Button>.  La clase <xref:System.Windows.Controls.Button> es una clase derivada de <xref:System.Windows.Controls.Primitives.ButtonBase> que tiene el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> en su lista de miembros.  Esta técnica de la certificación parcial para asociar un controlador de eventos es necesaria si el evento controlado no existe en la lista de miembros del elemento al que está asociado el controlador del evento enrutado.  
  
 [!code-xml[RoutedEventHandle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml#xaml)]  
  
 En el siguiente ejemplo se controla el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click>.  El ejemplo notifica qué elemento controla el evento y qué elemento genera el evento.  El controlador de eventos se ejecuta cuando el usuario hace clic en cualquiera de los botones.  
  
 [!code-csharp[RoutedEventHandle#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventHandle#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventHandle/VisualBasic/MainWindow.xaml.vb#handler)]  
  
## Vea también  
 <xref:System.Windows.RoutedEvent>   
 [Información general sobre acciones del usuario](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)   
 [Detalles de la sintaxis XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)