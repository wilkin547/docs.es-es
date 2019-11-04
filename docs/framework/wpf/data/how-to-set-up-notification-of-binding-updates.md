---
title: 'Cómo: Configurar la notificación de actualizaciones de enlaces'
ms.date: 03/30/2017
helpviewer_keywords:
- notifications [WPF], binding updates
- data binding [WPF], notification of binding updates
- binding [WPF], updates [WPF], notifications of
ms.assetid: 5673073e-dbe1-49da-980a-484a88f9595a
ms.openlocfilehash: dfa0f9264247f7585c1743e40fd980906556efd0
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454952"
---
# <a name="how-to-set-up-notification-of-binding-updates"></a>Cómo: Configurar la notificación de actualizaciones de enlaces
En este ejemplo se muestra cómo configurar la notificación cuando se ha actualizado la propiedad de destino del enlace (destino) o el origen del enlace (origen) de un enlace.  
  
## <a name="example"></a>Ejemplo  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] genera un evento de actualización de datos cada vez que se actualiza el origen o el destino del enlace. Internamente, este evento se usar para informar a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] que debe actualizarse porque se han cambiado los datos enlazados. Tenga en cuenta que para que estos eventos funcionen y, además, para que el enlace unidireccional o bidireccional funcione correctamente, debe implementar la clase de datos mediante la interfaz <xref:System.ComponentModel.INotifyPropertyChanged>. Para más información, consulte [Cómo: Implementar la notificación de cambio de propiedad](how-to-implement-property-change-notification.md).  
  
 Establezca la propiedad <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> o <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> (o ambos) en `true` en el enlace. El controlador que proporcione para la escucha de este evento debe adjuntarse directamente al elemento donde desee que se le informe de los cambios, o en el contexto de datos general si quiere que se le notifiquen los cambios en el contexto.  
  
 Este es un ejemplo que muestra cómo configurar las notificaciones cuando se ha actualizado una propiedad de destino.  
  
 [!code-xaml[DirectionalBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#2)]  
  
 Después puede asignar un controlador basado en el delegado EventHandler\<T>, *OnTargetUpdated* en este ejemplo, para controlar el evento:  
  
 [!code-csharp[DirectionalBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#3)]  
[!code-csharp[DirectionalBinding#EndEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#endevent)]  
  
 Los parámetros del evento pueden usarse para determinar los detalles sobre la propiedad que ha cambiado (como el tipo o el elemento específico si el mismo controlador se adjunta a más de un elemento), lo que puede resultar útil si hay varias propiedades enlazadas en un único elemento.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
