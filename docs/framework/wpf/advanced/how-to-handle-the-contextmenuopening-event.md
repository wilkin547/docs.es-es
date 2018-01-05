---
title: "Cómo: Controlar el evento ContextMenuOpening"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ContextMenuOpening properties [WPF]
ms.assetid: 789652fb-1951-4217-934a-7843e355adf4
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5eec8646a48f94fb9ffdcad14849416732618a06
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-handle-the-contextmenuopening-event"></a>Cómo: Controlar el evento ContextMenuOpening
El <xref:System.Windows.FrameworkElement.ContextMenuOpening> evento se puede administrar en una aplicación para ajustar un menú contextual existente antes para mostrar o suprimir el menú que se mostraría en caso contrario, establezca el <xref:System.Windows.RoutedEventArgs.Handled%2A> propiedad `true` en los datos del evento. El motivo habitual para configuración <xref:System.Windows.RoutedEventArgs.Handled%2A> a `true` en el evento datos consiste en reemplazar el menú completamente con un nuevo <xref:System.Windows.Controls.ContextMenu> de objeto, que a veces requiere cancelar la operación e iniciar una nueva apertura. Si escribe controladores para la <xref:System.Windows.FrameworkElement.ContextMenuOpening> eventos, debe tener en cuenta los problemas de sincronización entre un <xref:System.Windows.Controls.ContextMenu> control y el servicio que se encarga de abrir y colocar menús contextuales para los controles en general. En este tema se muestra algunas de las técnicas de código para el menú contextual de varios escenarios de apertura y muestra un caso donde el problema de sincronización entra en juego.  
  
 Hay varios escenarios para el control de la <xref:System.Windows.FrameworkElement.ContextMenuOpening> eventos:  
  
-   Ajustar los elementos de menú antes de la presentación.  
  
-   Reemplazar el menú completo antes de la presentación.  
  
-   Suprimir cualquier menú contextual existente y no mostrar el menú contextual ninguna por completo.  
  
## <a name="example"></a>Ejemplo  
  
## <a name="adjusting-the-menu-items-before-display"></a>Ajustar los elementos de menú antes de la presentación  
 Ajustar los elementos de menú existentes es bastante simple y es probablemente el escenario más común. Puede hacer esto con el fin de agregar o restar opciones del menú contextual en respuesta a la información de estado actual de la aplicación o información de estado concreto que está disponible como una propiedad en el objeto que se solicita el menú contextual.  
  
 La técnica general consiste en obtener el origen del evento, que es el control concreto que se hace doble clic, y obtener el <xref:System.Windows.FrameworkElement.ContextMenu%2A> propiedad del mismo. Suele ser conveniente comprobar el <xref:System.Windows.Controls.ItemsControl.Items%2A> colección para ver qué elementos de menú contextual ya existe en el menú y, a continuación, agregar o quitar adecuado nuevos <xref:System.Windows.Controls.MenuItem> elementos a o desde la colección.  
  
 [!code-csharp[ContextMenuOpeningHandlers#AddItemNoHandle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#additemnohandle)]  
  
## <a name="replacing-the-entire-menu-before-display"></a>Reemplazar el menú completo antes de la presentación  
 Un escenario alternativo es si desea reemplazar el menú contextual completo. Por supuesto puede utilizar también una variación del código anterior, para quitar todos los elementos de un menú contextual existente y agregar nuevos a partir de elemento de cero. Pero es el enfoque más intuitivo para reemplazar todos los elementos en el menú contextual crear un nuevo <xref:System.Windows.Controls.ContextMenu>rellenarlo con elementos y, a continuación, establezca el <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType> propiedad de un control como el nuevo <xref:System.Windows.Controls.ContextMenu>.  
  
 Éste es el código de controlador simple para reemplazar un <xref:System.Windows.Controls.ContextMenu>. El código hace referencia a una personalizada `BuildMenu` método, que está separada de la salida porque se llama por más de uno de los controladores de ejemplo.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceNoReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacenoreopen)]  
  
 [!code-csharp[ContextMenuOpeningHandlers#BuildMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#buildmenu)]  
  
 Sin embargo, si usa este estilo de controlador para <xref:System.Windows.FrameworkElement.ContextMenuOpening>, podría exponer un problema de tiempo si el objeto que está configurando la <xref:System.Windows.Controls.ContextMenu> no tiene un menú contextual preexistentes. Cuando un usuario seleccione un control, <xref:System.Windows.FrameworkElement.ContextMenuOpening> se produce incluso si existente <xref:System.Windows.Controls.ContextMenu> está vacío o es null. Pero en este caso, cualquier nuevo <xref:System.Windows.Controls.ContextMenu> establecida en el origen elemento llega demasiado tarde para mostrarse. Además, si el usuario haga clic en una segunda vez, en esta ocasión el nuevo <xref:System.Windows.Controls.ContextMenu> aparece, el valor no es null y el controlador correctamente reemplazará y mostrar el menú cuando el controlador ejecuta una segunda vez. Esto sugiere dos posibles soluciones:  
  
1.  Asegurarse de que <xref:System.Windows.FrameworkElement.ContextMenuOpening> controladores siempre se ejecutan con controles que tienen al menos un marcador de posición <xref:System.Windows.Controls.ContextMenu> disponibles, lo que piensa que será sustituido por el código del controlador. En este caso, todavía puede usar el controlador que se muestra en el ejemplo anterior, pero normalmente desea asignar un marcador de posición <xref:System.Windows.Controls.ContextMenu> en el marcado inicial:  
  
     [!code-xaml[ContextMenuOpeningHandlers#XAMLWithInitCM](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml#xamlwithinitcm)]  
  
2.  Se asume que la inicial <xref:System.Windows.Controls.ContextMenu> valor podría ser null, en función de alguna lógica preliminar. Se puede realizar cualquier comprobación <xref:System.Windows.Controls.ContextMenu> o de valores null, utilice una marca en el código para comprobar si el controlador se ha ejecutar al menos una vez. Dado que asume que el <xref:System.Windows.Controls.ContextMenu> consiste en que aparece, su controlador, a continuación, establece <xref:System.Windows.RoutedEventArgs.Handled%2A> a `true` en los datos del evento. Para el <xref:System.Windows.Controls.ContextMenuService> que es responsable de la presentación del menú contextual, un `true` valor <xref:System.Windows.RoutedEventArgs.Handled%2A> en el evento datos representan una solicitud para cancelar la presentación para el menú contextual / control de combinación que provocó el evento.  
  
 Ahora que se ha suprimido el menú contextual que podría mostrarse, el paso siguiente es proporcionar uno nuevo, a continuación, volver a mostrarlo. Establecer el nuevo uno es básicamente el mismo que el controlador anterior: crear un nuevo <xref:System.Windows.Controls.ContextMenu> y establezca el origen de control <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType> propiedad con él. El paso adicional es que ahora debe forzar la presentación del menú contextual, porque se ha suprimido el primer intento. Para forzar la presentación, establezca el <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A?displayProperty=nameWithType> propiedad `true` dentro del controlador. Tenga cuidado al hacer esto, dado que abrir el menú contextual en el controlador genera el <xref:System.Windows.FrameworkElement.ContextMenuOpening> nuevo evento. Si se vuelva a escribir su controlador, se vuelve infinitamente recursivo. Por lo tanto, siempre debe comprobar `null` o usar una marca si abre un menú contextual desde una <xref:System.Windows.FrameworkElement.ContextMenuOpening> controlador de eventos.  
  
## <a name="suppressing-any-existing-context-menu-and-displaying-no-context-menu"></a>Suprimir cualquier menú contextual existente y no mostrar ningún menú contextual  
 El último escenario, escribir un controlador que suprime un menú totalmente, es poco habitual. Si un control determinado no está pensado para mostrar un menú contextual, hay formas suele ser más apropiados para garantizar esto que suprimiendo el menú solo cuando un usuario lo solicita. Pero si desea utilizar el controlador para suprimir un menú contextual y mostrar nada, simplemente debe establecer el controlador <xref:System.Windows.RoutedEventArgs.Handled%2A> a `true` en los datos del evento. El <xref:System.Windows.Controls.ContextMenuService> que es responsable de mostrar un menú contextual comprobará los datos de evento del evento genera en el control. Si se ha marcado el evento <xref:System.Windows.RoutedEventArgs.Handled%2A> en cualquier lugar a lo largo de la ruta, a continuación, la acción Abrir del menú contextual que inició el evento se suprime.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacereopen)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.ContextMenu>  
 <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType>  
 [Información general sobre elementos base](../../../../docs/framework/wpf/advanced/base-elements-overview.md)  
 [Información general sobre ContextMenu](../../../../docs/framework/wpf/controls/contextmenu-overview.md)
