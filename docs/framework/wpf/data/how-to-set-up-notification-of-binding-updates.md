---
title: Filtrar Configurar notificación de actualizaciones de enlaces
ms.date: 03/30/2017
helpviewer_keywords:
- notifications [WPF], binding updates
- data binding [WPF], notification of binding updates
- binding [WPF], updates [WPF], notifications of
ms.assetid: 5673073e-dbe1-49da-980a-484a88f9595a
ms.openlocfilehash: 4185198312ed98f9aaa1388626600d9f21abae55
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213967"
---
# <a name="how-to-set-up-notification-of-binding-updates"></a>Filtrar Configurar notificación de actualizaciones de enlaces
En este ejemplo se muestra cómo configurar la notificación cuando se ha actualizado la propiedad de destino del enlace (destino) o el origen del enlace (origen) de un enlace.  
  
## <a name="example"></a>Ejemplo  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] genera un evento de actualización de datos cada vez que se ha actualizado el origen de enlace o el destino. Internamente, este evento se usar para informar a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] que debe actualizarse porque se han cambiado los datos enlazados. Tenga en cuenta que para estos eventos funcionen y también para el enlace unidireccional o bidireccional funcionen correctamente, debe implementar la clase de datos mediante el <xref:System.ComponentModel.INotifyPropertyChanged> interfaz. Para más información, consulte [Cómo: Implementar la notificación de cambio de propiedad](how-to-implement-property-change-notification.md).  
  
 Establecer el <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> o <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> propiedad (o ambos) para `true` en el enlace. El controlador que proporcione para la escucha de este evento debe adjuntarse directamente al elemento donde desee que se le informe de los cambios, o en el contexto de datos general si quiere que se le notifiquen los cambios en el contexto.  
  
 Este es un ejemplo que muestra cómo configurar las notificaciones cuando se ha actualizado una propiedad de destino.  
  
 [!code-xaml[DirectionalBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#2)]  
  
 Después puede asignar un controlador basado en el delegado EventHandler\<T>, *OnTargetUpdated* en este ejemplo, para controlar el evento:  
  
 [!code-csharp[DirectionalBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#3)]  
[!code-csharp[DirectionalBinding#EndEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#endevent)]  
  
 Los parámetros del evento pueden usarse para determinar los detalles sobre la propiedad que ha cambiado (como el tipo o el elemento específico si el mismo controlador se adjunta a más de un elemento), lo que puede resultar útil si hay varias propiedades enlazadas en un único elemento.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre el enlace de datos](data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
