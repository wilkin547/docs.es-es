---
title: "C&#243;mo: Agregar control de clases a un evento enrutado | Microsoft Docs"
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
  - "controladores de clases, eventos enrutados"
  - "eventos enrutados, controladores de clases"
  - "task_core_add_class_handling_routed_event"
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Agregar control de clases a un evento enrutado
Los eventos enrutados se pueden controlar mediante controladores de clase o de instancia en cualquier nodo concreto de la ruta.  En primer lugar, se invocan los controladores de clase, que las implementaciones de clase pueden utilizar para suprimir eventos del control de instancias o introducir otros comportamientos específicos de eventos en eventos que pertenecen a las clases base.  En este ejemplo se muestran dos técnicas estrechamente relacionadas para implementar controladores de clase.  
  
## Ejemplo  
 En este ejemplo se utiliza una clase personalizada basada en el panel <xref:System.Windows.Controls.Canvas>.  La premisa básica de la aplicación es que la clase personalizada introduce comportamientos en sus elementos secundarios, lo que incluye interceptar los clics con el botón primario del mouse y marcarlos como controlados, antes de invocar a la clase del elemento secundario o a cualquier controlador de instancia.  
  
 La clase <xref:System.Windows.UIElement> expone un método virtual que habilita el control de clases en el evento <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown>, simplemente invalidando el evento.  Ésta es la manera más simple de implementar el control de clases si este tipo de método virtual está disponible en algún punto de la jerarquía de la clase.  En el código siguiente se muestra la implementación de <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> en "MyEditContainer", que se deriva de <xref:System.Windows.Controls.Canvas>.  La implementación marca el evento como controlado en los argumentos y, a continuación, agrega código para aplicar al elemento de origen un cambio básico visible.  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 Si no hay ningún método virtual disponible en las clases base o para ese método concreto, el control de clases se puede agregar directamente mediante un método de utilidad de la clase <xref:System.Windows.EventManager>, <xref:System.Windows.EventManager.RegisterClassHandler%2A>.  Únicamente debe llamarse a este método dentro de la inicialización estática de clases que agregan el control de clases.  En este ejemplo se agrega otro controlador para <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> y, en este caso, la clase registrada es la clase personalizada.  En contraste, cuando se utilizan métodos virtuales, la clase registrada es, en realidad, la clase base <xref:System.Windows.UIElement>.  En aquellos casos en que tanto las clases base como las subclases registran el control de clases, se invocan primero los controladores subclases.  El comportamiento en una aplicación sería: en primer lugar, este controlador mostraría su cuadro de mensaje y, a continuación, se mostraría el cambio visual en el controlador del método virtual.  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## Vea también  
 <xref:System.Windows.EventManager>   
 [Marcar eventos enrutados como controlados y control de clases](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)   
 [Controlar un evento enrutado](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md)   
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)