---
title: Procedimiento Crear un evento enrutado personalizado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], creating
- events [WPF], routing
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
ms.openlocfilehash: cbfb88af4e35e3f090248982bb14d6b7a3a03cef
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401470"
---
# <a name="how-to-create-a-custom-routed-event"></a>Procedimiento Crear un evento enrutado personalizado
Para que el evento personalizado admita el enrutamiento de eventos, debe registrar un <xref:System.Windows.RoutedEvent> mediante el <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> método. Este ejemplo muestra los aspectos básicos de la creación de un evento enrutado personalizado.  
  
## <a name="example"></a>Ejemplo  
 Como se muestra en el ejemplo siguiente, primero se registra <xref:System.Windows.RoutedEvent> con el <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> método. Por Convención, el <xref:System.Windows.RoutedEvent> nombre de campo estático debe terminar con el ***evento***de sufijo. En este ejemplo, el nombre del evento es `Tap` y la estrategia de enrutamiento del evento es. <xref:System.Windows.RoutingStrategy.Bubble> Después de la llamada de registro, puede proporcionar descriptores de acceso de eventos Common Language Runtime (CLR) Add-and-Remove para el evento.  
  
 Tenga en cuenta que, aunque el evento se genera a través del método virtual `OnTap` en este ejemplo concreto, cómo se genera el evento o cómo este responde a los cambios dependerá de sus necesidades.  
  
 Tenga en cuenta también que en este ejemplo se implementa básicamente una subclase completa de <xref:System.Windows.Controls.Button>; esa subclase se compila como un ensamblado independiente y, a continuación, se crea una instancia como una clase personalizada en una página independiente. [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Este ejemplo pretende ilustrar el concepto de que los controles con subclases pueden insertarse en árboles formados por otros controles y que, en esta situación, los eventos personalizados de estos controles tienen las mismas funcionalidades de enrutamiento de eventos que cualquier elemento de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] nativo.  
  
 [!code-csharp[RoutedEventCustom#CustomClass](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xaml[RoutedEventCustom#Page](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 Los eventos de tunelización se crean de la misma manera <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> , pero <xref:System.Windows.RoutingStrategy.Tunnel> con establecido en en la llamada de registro. Por convención, a los eventos de tunelización de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se les antepone la palabra "Preview".  
  
 Para ver un ejemplo de cómo funciona la propagación de eventos, consulte [Controlar un evento enrutado](how-to-handle-a-routed-event.md).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre eventos enrutados](routed-events-overview.md)
- [Información general sobre acciones del usuario](input-overview.md)
- [Información general sobre la creación de controles](../controls/control-authoring-overview.md)
