---
title: Filtrar Crear un evento enrutado personalizado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], creating
- events [WPF], routing
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
ms.openlocfilehash: c351bec05fa8ad8438cb8521f6ab1e6277a40b1d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373405"
---
# <a name="how-to-create-a-custom-routed-event"></a>Filtrar Crear un evento enrutado personalizado
Para que el evento personalizado admitir el enrutamiento de eventos, deberá registrar una <xref:System.Windows.RoutedEvent> utilizando el <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> método. Este ejemplo muestra los aspectos básicos de la creación de un evento enrutado personalizado.  
  
## <a name="example"></a>Ejemplo  
 Como se muestra en el ejemplo siguiente, primero se registre un <xref:System.Windows.RoutedEvent> utilizando el <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> método. Por convención, el <xref:System.Windows.RoutedEvent> nombre del campo estático debe terminar con el sufijo ***eventos***. En este ejemplo, el nombre del evento es `Tap` y la estrategia de enrutamiento del evento es <xref:System.Windows.RoutingStrategy.Bubble>. Después de la llamada de registro, puede proporcionar los descriptores de acceso de eventos de [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] add y remove del evento.  
  
 Tenga en cuenta que, aunque el evento se genera a través del método virtual `OnTap` en este ejemplo concreto, cómo se genera el evento o cómo este responde a los cambios dependerá de sus necesidades.  
  
 Tenga en cuenta también que este ejemplo implementa básicamente una subclase completa de <xref:System.Windows.Controls.Button>; esa subclase se compila como un ensamblado independiente y, a continuación, crea una instancia como una clase personalizada en otro [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] página. Este ejemplo pretende ilustrar el concepto de que los controles con subclases pueden insertarse en árboles formados por otros controles y que, en esta situación, los eventos personalizados de estos controles tienen las mismas funcionalidades de enrutamiento de eventos que cualquier elemento de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] nativo.  
  
 [!code-csharp[RoutedEventCustom#CustomClass](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xaml[RoutedEventCustom#Page](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 Los eventos de tunelización se crean la misma manera, pero con <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> establecido en <xref:System.Windows.RoutingStrategy.Tunnel> en la llamada de registro. Por convención, a los eventos de tunelización de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se les antepone la palabra "Preview".  
  
 Para ver un ejemplo de cómo funciona la propagación de eventos, consulte [Controlar un evento enrutado](how-to-handle-a-routed-event.md).  
  
## <a name="see-also"></a>Vea también
- [Información general sobre eventos enrutados](routed-events-overview.md)
- [Información general sobre acciones del usuario](input-overview.md)
- [Información general sobre la creación de controles](../controls/control-authoring-overview.md)
