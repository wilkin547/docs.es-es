---
title: 'Cómo: Agregar control de clases a un evento enrutado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], class handlers
- task_core_add_class_handling_routed_properties [WPF]
- class handlers [WPF], routed events
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
ms.openlocfilehash: 85c3491c9035d807b4c654659a8641121bb5709f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-class-handling-for-a-routed-event"></a>Cómo: Agregar control de clases a un evento enrutado
Los eventos enrutados pueden controlarse mediante controladores de clase o de instancia en cualquier nodo determinado en la ruta. Controladores de clase se invocan en primer lugar y las implementaciones de clase pueden utilizar para suprimir los eventos del control de instancias o introducir otros comportamientos específicos de eventos en los eventos que pertenecen a las clases base. En este ejemplo se muestra dos técnicas estrechamente relacionadas para implementar controladores de clases.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo utiliza una clase personalizada basada en la <xref:System.Windows.Controls.Canvas> panel. La idea básica de la aplicación es que la clase personalizada introduce comportamientos en sus elementos secundarios, incluidos interceptando hace clic en cualquier botón primario del mouse y marcarlos como controlados, antes de la clase de elemento secundarios o los controladores de instancia en la se invocará.  
  
 El <xref:System.Windows.UIElement> clase expone un método virtual que permite el control de clases en el <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> evento, simplemente invalidando el evento. Se trata de la manera más sencilla de implementar el control de clases si este tipo de método virtual está disponible en algún lugar de la jerarquía de la clase. El código siguiente muestra el <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> implementación en "MyEditContainer", que se deriva de <xref:System.Windows.Controls.Canvas>. La implementación marca el evento como controlado en los argumentos y, a continuación, agrega código para asignar el elemento de origen un cambio básico visible.  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 Si virtual ya no está disponible en las clases base o para ese método concreto, control de clases puede agregarse directamente mediante un método de utilidad de la <xref:System.Windows.EventManager> (clase), <xref:System.Windows.EventManager.RegisterClassHandler%2A>. Este método solo debe llamarse dentro de la inicialización de clases que se va a agregar control de clases estática. Este ejemplo agrega otro controlador para <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> , y en este caso, la clase registrada es la clase personalizada. En cambio, al utilizar los métodos virtuales, la clase registrada es realmente el <xref:System.Windows.UIElement> clase base. En casos donde las clases base como las subclases registran control de clases, se invocan en primer lugar los controladores de la subclase. El comportamiento en una aplicación sería que primero este controlador mostraría su cuadro de mensajes y, a continuación, se mostraría el cambio visual en el controlador del método virtual.  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.EventManager>  
 [Marcar eventos enrutados como controlados y control de clases](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)  
 [Controlar un evento enrutado](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md)  
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
