---
title: "C&#243;mo: Controlar el evento ContextMenuOpening | Microsoft Docs"
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
  - "ContextMenuOpening (evento)"
ms.assetid: 789652fb-1951-4217-934a-7843e355adf4
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Controlar el evento ContextMenuOpening
El evento <xref:System.Windows.FrameworkElement.ContextMenuOpening> se puede controlar en una aplicación para ajustar un menú contextual existente antes de su presentación o para suprimir el menú que se mostraría en situación normal estableciendo la propiedad <xref:System.Windows.RoutedEventArgs.Handled%2A> en `true` en los datos de evento.  El motivo habitual para establecer <xref:System.Windows.RoutedEventArgs.Handled%2A> en `true` en los datos de evento es reemplazar completamente el menú con un nuevo objeto <xref:System.Windows.Controls.ContextMenu>, lo que a veces requiere cancelar la operación e iniciar una nueva apertura.  Si escribe controladores para el evento <xref:System.Windows.FrameworkElement.ContextMenuOpening>, debe tener en cuenta los problemas de control de tiempo entre un control <xref:System.Windows.Controls.ContextMenu> y el servicio que es responsables de abrir y colocar los menús contextuales para los controles en general.  En este tema se ilustran algunas de las técnicas de código para varios escenarios de apertura de menús contextuales y se muestra un caso donde se hace patente el problema de control de tiempo.  
  
 Hay varios escenarios de control del evento <xref:System.Windows.FrameworkElement.ContextMenuOpening>:  
  
-   Ajustar los elementos de menú antes de la presentación.  
  
-   Reemplazar el menú completo antes de la presentación.  
  
-   Suprimir completamente cualquier menú contextual existente y no mostrar ninguno.  
  
## Ejemplo  
  
## Ajustar los elementos de menú antes de la presentación  
 Ajustar los elementos de menú existentes es bastante simple y, probablemente, es el escenario más común.  Puede hacerlo para agregar o quitar opciones en el menú contextual en respuesta a la información de estado actual de la aplicación, o a la información de estado concreta disponible como una propiedad del objeto en que se solicita el menú contextual.  
  
 La técnica general consiste en obtener el origen del evento, que es el control concreto donde que se hizo clic con el botón secundario, y obtener la propiedad <xref:System.Windows.FrameworkElement.ContextMenu%2A> de él.  Suele ser conveniente comprobar la colección <xref:System.Windows.Controls.ItemsControl.Items%2A> para ver qué elementos de menú contextual existen ya en ella y, a continuación, agregar o quitar los elementos <xref:System.Windows.Controls.MenuItem> nuevos en la colección.  
  
 [!code-csharp[ContextMenuOpeningHandlers#AddItemNoHandle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#additemnohandle)]  
  
## Reemplazar el menú completo antes de la presentación  
 Un escenario alternativo es aquél en que se desea reemplazar el menú contextual completo.  Por supuesto, puede utilizar una variación del código anterior para quitar todos los elementos de un menú contextual existente y agregar otros nuevos partiendo del elemento cero.  Pero el enfoque más intuitivo para reemplazar todos los elementos del menú contextual es crear un nuevo <xref:System.Windows.Controls.ContextMenu>, rellenarlo con elementos y, a continuación, establecer la propiedad <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=fullName> de un control en el nuevo <xref:System.Windows.Controls.ContextMenu>.  
  
 A continuación, se muestra el código de controlador simple para reemplazar un <xref:System.Windows.Controls.ContextMenu>.  En el código se hace referencia a un método `BuildMenu` personalizado que está separado porque lo llaman más de uno de los controladores del ejemplo.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceNoReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacenoreopen)]  
  
 [!code-csharp[ContextMenuOpeningHandlers#BuildMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#buildmenu)]  
  
 Sin embargo, si utiliza este estilo de controlador para un evento <xref:System.Windows.FrameworkElement.ContextMenuOpening>, potencialmente puede exponer un problema de control de tiempo si el objeto donde se establece el <xref:System.Windows.Controls.ContextMenu> no tiene un menú contextual preexistente.  Cuando un usuario hace clic con el botón secundario en un control, se provoca el evento <xref:System.Windows.FrameworkElement.ContextMenuOpening> aunque el objeto <xref:System.Windows.Controls.ContextMenu> existente esté vacío o sea null.  Sin embargo, en este caso, sea cual fuere el nuevo <xref:System.Windows.Controls.ContextMenu> que se establezca en el elemento de origen llega demasiado tarde para mostrarlo.  Además, si el usuario hace clic con el botón secundario por segunda vez, esta vez aparece el nuevo <xref:System.Windows.Controls.ContextMenu>, su valor no es null y el controlador se reemplaza correctamente y muestra el menú cuando el controlador se ejecuta por segunda vez.  Esto sugiere dos posibles soluciones alternativas:  
  
1.  Asegúrese de que los controladores de <xref:System.Windows.FrameworkElement.ContextMenuOpening> se ejecuten siempre en controles que tengan como mínimo un <xref:System.Windows.Controls.ContextMenu> marcador de posición disponible, que se reemplazará por el código del controlador.  En este caso, aún así puede utilizar el controlador mostrado en el ejemplo anterior, pero normalmente suele ser conveniente asignar un <xref:System.Windows.Controls.ContextMenu> marcador de posición en el marcado inicial:  
  
     [!code-xml[ContextMenuOpeningHandlers#XAMLWithInitCM](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml#xamlwithinitcm)]  
  
2.  Supongamos que el valor de <xref:System.Windows.Controls.ContextMenu> inicial sea null, según alguna parte de la lógica preliminar.  Podría comprobar si <xref:System.Windows.Controls.ContextMenu> es null o utilizar un marcador en el código para comprobar si el controlador se ha ejecutado al menos una vez.  Dado que se supone que <xref:System.Windows.Controls.ContextMenu> está a punto de mostrarse, a continuación el controlador establece <xref:System.Windows.RoutedEventArgs.Handled%2A> en `true` en los datos de evento.  Para el <xref:System.Windows.Controls.ContextMenuService> responsable de la presentación del menú contextual, un valor `true` para <xref:System.Windows.RoutedEventArgs.Handled%2A> en los datos de evento representa una solicitud de cancelar la presentación correspondiente a la combinación de menú contextual y control que provocó el evento.  
  
 Ahora que ha suprimido el menú contextual que podría mostrarse, el paso siguiente es proporcionar uno nuevo y mostrarlo.  Establecer el nuevo es básicamente igual que con el controlador anterior: se compila un nuevo <xref:System.Windows.Controls.ContextMenu> y se establece en él la propiedad <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=fullName> del origen del control.  La operación adicional consiste en forzar ahora la presentación del menú contextual, porque se ha suprimido el primer intento.  Para forzar la presentación, se establece la propiedad <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A?displayProperty=fullName> en `true` dentro del controlador.  Extreme las precauciones al hacerlo, porque al abrir el menú contextual en el controlador se provoca de nuevo el evento <xref:System.Windows.FrameworkElement.ContextMenuOpening>.  Si entra de nuevo en el controlador, se vuelve infinitamente recursivo.  Por este motivo, siempre hay que comprobar si existe el valor `null` o utilizar un marcador al abrir un menú contextual desde el interior de un controlador de eventos de <xref:System.Windows.FrameworkElement.ContextMenuOpening>.  
  
## Suprimir cualquier menú contextual existente y no mostrar ninguno  
 El último escenario, escribir un controlador que suprime un menú totalmente, es infrecuente.  Si un control no está pensado para mostrar un menú contextual, es probable que existan maneras más adecuadas de asegurarse de ello que suprimir el menú sólo cuando un usuario lo solicita.  Sin embargo, si desea utilizar el controlador para suprimir un menú contextual y no presentar nada, entonces el controlador debe limitarse a establecer <xref:System.Windows.RoutedEventArgs.Handled%2A> en `true` en los datos de evento.  El <xref:System.Windows.Controls.ContextMenuService> responsable de mostrar un menú contextual comprobará los datos del evento que se provocó en el control.  Si el evento está marcado como <xref:System.Windows.RoutedEventArgs.Handled%2A> en cualquier punto de la ruta, se suprime la acción de apertura de menú contextual que ha iniciado el evento.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacereopen)]  
  
## Vea también  
 <xref:System.Windows.Controls.ContextMenu>   
 <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=fullName>   
 [Información general sobre elementos base](../../../../docs/framework/wpf/advanced/base-elements-overview.md)   
 [Información general sobre ContextMenu](../../../../docs/framework/wpf/controls/contextmenu-overview.md)