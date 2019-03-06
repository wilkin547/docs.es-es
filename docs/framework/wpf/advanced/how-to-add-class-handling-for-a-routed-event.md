---
title: Filtrar Agregar control de clases a un evento enrutado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], class handlers
- task_core_add_class_handling_routed_properties [WPF]
- class handlers [WPF], routed events
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
ms.openlocfilehash: 8c973871336c3389161ce25ae52d2dfaef9c53a5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361777"
---
# <a name="how-to-add-class-handling-for-a-routed-event"></a>Filtrar Agregar control de clases a un evento enrutado
Los eventos enrutados se pueden controlar mediante controladores de clase o de instancia en cualquier nodo determinado en la ruta. Los controladores de clase se invocan en primer lugar y pueden usarse por implementaciones de la clase para suprimir los eventos del control de instancias o introducir otros comportamientos específicos de eventos en los eventos que pertenecen a las clases base. En este ejemplo se muestra dos técnicas estrechamente relacionadas para implementar los controladores de clase.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo usa una clase personalizada basada en la <xref:System.Windows.Controls.Canvas> panel. La premisa básica de la aplicación es que la clase personalizada introduce comportamientos en sus elementos secundarios, incluidos interceptar hace clic en cualquier botón del mouse y marcarlos como controlados, antes de la clase del elemento secundario o cualquier controlador de instancias en el se va a invocar.  
  
 El <xref:System.Windows.UIElement> clase expone un método virtual que permite el control de clases en el <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> evento, simplemente invalidando el evento. Se trata de la manera más sencilla de implementar el control de clases si este tipo de método virtual está disponible en algún lugar de la jerarquía de la clase. El siguiente código muestra la <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> implementación en "MyEditContainer" que se deriva de <xref:System.Windows.Controls.Canvas>. Marca el evento como controlado en los argumentos de la implementación y, a continuación, agrega código para aplicar el elemento de origen de un cambio visible básico.  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 Si virtual no está disponible en las clases base o para ese método concreto, control de clases se puede agregar directamente mediante un método de utilidad de la <xref:System.Windows.EventManager> (clase), <xref:System.Windows.EventManager.RegisterClassHandler%2A>. Este método solo debe llamarse dentro de la inicialización de clases que se va a agregar control de clases estática. Este ejemplo agrega otro controlador para <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> , y en este caso, la clase registrada es la clase personalizada. En cambio, al usar los métodos virtuales, la clase registrada es realmente el <xref:System.Windows.UIElement> clase base. En casos donde las clases base y subclase registran control de clases, se invocan primero los controladores de subclase. El comportamiento en una aplicación sería que, en primer lugar, este controlador mostraría su cuadro de mensaje y, a continuación, se mostraría el cambio visual en el controlador del método virtual.  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.EventManager>
- [Marcar eventos enrutados como controlados y control de clases](marking-routed-events-as-handled-and-class-handling.md)
- [Controlar un evento enrutado](how-to-handle-a-routed-event.md)
- [Información general sobre eventos enrutados](routed-events-overview.md)
