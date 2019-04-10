---
title: Filtrar Controlar el evento ContextMenuOpening
ms.date: 03/30/2017
helpviewer_keywords:
- ContextMenuOpening properties [WPF]
ms.assetid: 789652fb-1951-4217-934a-7843e355adf4
ms.openlocfilehash: 65a1e34d5b078c49bf59c2d9787812940c9a7494
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59340404"
---
# <a name="how-to-handle-the-contextmenuopening-event"></a>Filtrar Controlar el evento ContextMenuOpening
El <xref:System.Windows.FrameworkElement.ContextMenuOpening> se pueden controlar eventos en una aplicación para ajustar un menú contextual existente antes para mostrar o suprimir el menú que se mostraría en caso contrario, estableciendo el <xref:System.Windows.RoutedEventArgs.Handled%2A> propiedad `true` en los datos del evento. La razón típica para la configuración de <xref:System.Windows.RoutedEventArgs.Handled%2A> a `true` en el evento son reemplazar el menú completamente con un nuevo datos <xref:System.Windows.Controls.ContextMenu> objeto, que a veces requiere cancelar la operación e iniciar una nuevo abrir. Al escribir controladores para la <xref:System.Windows.FrameworkElement.ContextMenuOpening> eventos, debe ser consciente de los problemas de sincronización entre un <xref:System.Windows.Controls.ContextMenu> control y el servicio que se encarga de abrir y posicionamiento de los menús contextuales para los controles en general. En este tema se muestra algunas de las técnicas de código para el menú contextual de varios escenarios de apertura y muestra un caso donde el problema de sincronización entra en juego.  
  
 Hay varios escenarios para el control de la <xref:System.Windows.FrameworkElement.ContextMenuOpening> eventos:  
  
-   Ajuste de los elementos de menú antes de la presentación.  
  
-   Reemplazar el menú completo antes de la presentación.  
  
-   Suprimir cualquier menú contextual existente y no mostrar ningún menú contextual por completo.  
  
## <a name="example"></a>Ejemplo  
  
## <a name="adjusting-the-menu-items-before-display"></a>Ajuste de los elementos de menú antes de la presentación  
 Ajuste de los elementos de menú existentes es bastante simple y es probablemente el escenario más común. Puede hacerlo con el fin de agregar o restar las opciones del menú contextual en respuesta a la información de estado actual de la aplicación o información de estado concreta que está disponible como una propiedad del objeto donde se solicita el menú contextual.  
  
 La técnica general consiste en obtener el origen del evento, que es el control específico que hizo, y obtener el <xref:System.Windows.FrameworkElement.ContextMenu%2A> propiedad a partir de él. Normalmente desea comprobar la <xref:System.Windows.Controls.ItemsControl.Items%2A> colección para ver qué elementos de menú contextual ya existe en el menú y, a continuación, agregar o quitar adecuado nuevo <xref:System.Windows.Controls.MenuItem> hacia o desde la colección de elementos.  
  
 [!code-csharp[ContextMenuOpeningHandlers#AddItemNoHandle](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#additemnohandle)]  
  
## <a name="replacing-the-entire-menu-before-display"></a>Reemplazar el menú completo antes de la presentación  
 Un escenario alternativo es si desea reemplazar el menú contextual completo. Desde luego también puede usar una variación del código anterior, para quitar todos los elementos de un menú contextual existente y agregar otros nuevos a partir de cero del elemento. Pero es el enfoque más intuitivo para reemplazar todos los elementos en el menú contextual crear un nuevo <xref:System.Windows.Controls.ContextMenu>, rellenarlo con elementos y, a continuación, establezca el <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType> propiedad de un control como el nuevo <xref:System.Windows.Controls.ContextMenu>.  
  
 El siguiente es el código del controlador simple para reemplazar un <xref:System.Windows.Controls.ContextMenu>. El código hace referencia a un personalizado `BuildMenu` método, que se separaron porque se llama mediante más de uno de los controladores de ejemplo.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceNoReopen](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacenoreopen)]  
  
 [!code-csharp[ContextMenuOpeningHandlers#BuildMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#buildmenu)]  
  
 Sin embargo, si usa este estilo de controlador para <xref:System.Windows.FrameworkElement.ContextMenuOpening>, puede quedar expuesto un problema de sincronización si el objeto que está configurando el <xref:System.Windows.Controls.ContextMenu> no tiene un menú contextual preexistente. Cuando un usuario hace clic con botón de un control, <xref:System.Windows.FrameworkElement.ContextMenuOpening> se produce incluso si existente <xref:System.Windows.Controls.ContextMenu> está vacío o nulo. Pero en este caso, cualquier nuevo <xref:System.Windows.Controls.ContextMenu> se establece en el origen de elemento llega demasiado tarde para mostrarse. Además, si el usuario que hace clic en una segunda vez, esta vez la nueva <xref:System.Windows.Controls.ContextMenu> aparece, el valor es no nulo y el controlador correctamente reemplazará y mostrar el menú cuando el controlador ejecuta una segunda vez. Esto sugiere dos posibles soluciones:  
  
1. Asegurarse de que <xref:System.Windows.FrameworkElement.ContextMenuOpening> controladores siempre se ejecutan en los controles que tienen al menos un marcador de posición <xref:System.Windows.Controls.ContextMenu> disponibles, que se va a reemplazarse por el código del controlador. En este caso, todavía puede usar el controlador que se muestra en el ejemplo anterior, pero normalmente desea asignar un marcador de posición <xref:System.Windows.Controls.ContextMenu> en el marcado inicial:  
  
     [!code-xaml[ContextMenuOpeningHandlers#XAMLWithInitCM](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml#xamlwithinitcm)]  
  
2. Suponga que la inicial <xref:System.Windows.Controls.ContextMenu> valor puede ser null, según una lógica preliminar. Puede comprobar la <xref:System.Windows.Controls.ContextMenu> para null, o usar una marca en el código para comprobar si el controlador ha sido ejecutar al menos una vez. Dado que se asume que el <xref:System.Windows.Controls.ContextMenu> consiste en ser su controlador muestra a continuación, establece <xref:System.Windows.RoutedEventArgs.Handled%2A> a `true` en los datos del evento. Para el <xref:System.Windows.Controls.ContextMenuService> que es responsable de la presentación del menú contextual, un `true` valor <xref:System.Windows.RoutedEventArgs.Handled%2A> en el evento datos representan una solicitud para cancelar la presentación del menú contextual / control de combinación que provocó el evento.  
  
 Ahora que ha suprimido el menú contextual potencialmente sospechosos, el siguiente paso es proporcionar una nueva, a continuación, volver a mostrarlo. Establecer el nuevo es básicamente el mismo que el controlador anterior: crear un nuevo <xref:System.Windows.Controls.ContextMenu> y establezca el origen de control <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType> propiedad con ella. El paso adicional es que ahora debe forzar la presentación del menú contextual, porque se ha suprimido el primer intento. Para forzar la presentación, se establece la <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A?displayProperty=nameWithType> propiedad `true` dentro del controlador. Tenga cuidado al hacerlo, porque provoca abriendo el menú contextual en el controlador de la <xref:System.Windows.FrameworkElement.ContextMenuOpening> nuevo evento. Si volver a escribir el controlador, vuelve infinitamente recursivo. Por eso siempre debe comprobar `null` o usar una marca si abre un menú contextual desde una <xref:System.Windows.FrameworkElement.ContextMenuOpening> controlador de eventos.  
  
## <a name="suppressing-any-existing-context-menu-and-displaying-no-context-menu"></a>Suprimir cualquier menú contextual existente y no mostrar ningún menú contextual  
 El último escenario, escribir un controlador que suprime un menú totalmente, es poco habitual. Si un control determinado no está pensado para mostrar un menú contextual, hay maneras probablemente más adecuado para garantizar que suprimir el menú sólo cuando un usuario lo solicita. Pero si desea usar el controlador para suprimir un menú contextual y mostrar nada, simplemente debe establecer el controlador <xref:System.Windows.RoutedEventArgs.Handled%2A> a `true` en los datos del evento. El <xref:System.Windows.Controls.ContextMenuService> que es responsable de mostrar un menú contextual comprobará los datos del evento del evento produce en el control. Si se ha marcado el evento <xref:System.Windows.RoutedEventArgs.Handled%2A> en cualquier lugar a lo largo de la ruta, a continuación, la acción Abrir del menú contextual que inició el evento se ha suprimido.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceReopen](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacereopen)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType>
- [Información general sobre elementos base](base-elements-overview.md)
- [Información general sobre ContextMenu](../controls/contextmenu-overview.md)
