---
title: "Cómo: Agregar control de clases a un evento enrutado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], class handlers
- task_core_add_class_handling_routed_properties [WPF]
- class handlers [WPF], routed events
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1f0315bbd1d1a5ab2ae08d8bc1810e240cb6a5a7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-class-handling-for-a-routed-event"></a><span data-ttu-id="002a9-102">Cómo: Agregar control de clases a un evento enrutado</span><span class="sxs-lookup"><span data-stu-id="002a9-102">How to: Add Class Handling for a Routed Event</span></span>
<span data-ttu-id="002a9-103">Los eventos enrutados pueden controlarse mediante controladores de clase o de instancia en cualquier nodo determinado en la ruta.</span><span class="sxs-lookup"><span data-stu-id="002a9-103">Routed events can be handled either by class handlers or instance handlers on any given node in the route.</span></span> <span data-ttu-id="002a9-104">Controladores de clase se invocan en primer lugar y las implementaciones de clase pueden utilizar para suprimir los eventos del control de instancias o introducir otros comportamientos específicos de eventos en los eventos que pertenecen a las clases base.</span><span class="sxs-lookup"><span data-stu-id="002a9-104">Class handlers are invoked first, and can be used by class implementations to suppress events from instance handling or introduce other event specific behaviors on events that are owned by base classes.</span></span> <span data-ttu-id="002a9-105">En este ejemplo se muestra dos técnicas estrechamente relacionadas para implementar controladores de clases.</span><span class="sxs-lookup"><span data-stu-id="002a9-105">This example illustrates two closely related techniques for implementing class handlers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="002a9-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="002a9-106">Example</span></span>  
 <span data-ttu-id="002a9-107">Este ejemplo utiliza una clase personalizada basada en la <xref:System.Windows.Controls.Canvas> panel.</span><span class="sxs-lookup"><span data-stu-id="002a9-107">This example uses a custom class based on the <xref:System.Windows.Controls.Canvas> panel.</span></span> <span data-ttu-id="002a9-108">La idea básica de la aplicación es que la clase personalizada introduce comportamientos en sus elementos secundarios, incluidos interceptando hace clic en cualquier botón primario del mouse y marcarlos como controlados, antes de la clase de elemento secundarios o los controladores de instancia en la se invocará.</span><span class="sxs-lookup"><span data-stu-id="002a9-108">The basic premise of the application is that the custom class introduces behaviors on its child elements, including intercepting any left mouse button clicks and marking them handled, before the child element class or any instance handlers on it will be invoked.</span></span>  
  
 <span data-ttu-id="002a9-109">El <xref:System.Windows.UIElement> clase expone un método virtual que permite el control de clases en el <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> evento, simplemente invalidando el evento.</span><span class="sxs-lookup"><span data-stu-id="002a9-109">The <xref:System.Windows.UIElement> class exposes a virtual method that enables class handling on the <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> event, by simply overriding the event.</span></span> <span data-ttu-id="002a9-110">Se trata de la manera más sencilla de implementar el control de clases si este tipo de método virtual está disponible en algún lugar de la jerarquía de la clase.</span><span class="sxs-lookup"><span data-stu-id="002a9-110">This is the simplest way to implement class handling if such a virtual method is available somewhere in your class' hierarchy.</span></span> <span data-ttu-id="002a9-111">El código siguiente muestra el <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> implementación en "MyEditContainer", que se deriva de <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="002a9-111">The following code shows the <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> implementation in the "MyEditContainer" that is derived from <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="002a9-112">La implementación marca el evento como controlado en los argumentos y, a continuación, agrega código para asignar el elemento de origen un cambio básico visible.</span><span class="sxs-lookup"><span data-stu-id="002a9-112">The implementation marks the event as handled in the arguments, and then adds some code to give the source element a basic visible change.</span></span>  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 <span data-ttu-id="002a9-113">Si virtual ya no está disponible en las clases base o para ese método concreto, control de clases puede agregarse directamente mediante un método de utilidad de la <xref:System.Windows.EventManager> (clase), <xref:System.Windows.EventManager.RegisterClassHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="002a9-113">If no virtual is available on base classes or for that particular method, class handling can be added directly using a utility method of the <xref:System.Windows.EventManager> class, <xref:System.Windows.EventManager.RegisterClassHandler%2A>.</span></span> <span data-ttu-id="002a9-114">Este método solo debe llamarse dentro de la inicialización de clases que se va a agregar control de clases estática.</span><span class="sxs-lookup"><span data-stu-id="002a9-114">This method should only be called within the static initialization of classes that are adding class handling.</span></span> <span data-ttu-id="002a9-115">Este ejemplo agrega otro controlador para <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> , y en este caso, la clase registrada es la clase personalizada.</span><span class="sxs-lookup"><span data-stu-id="002a9-115">This example adds another handler for <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> , and in this case the registered class is the custom class.</span></span> <span data-ttu-id="002a9-116">En cambio, al utilizar los métodos virtuales, la clase registrada es realmente el <xref:System.Windows.UIElement> clase base.</span><span class="sxs-lookup"><span data-stu-id="002a9-116">In contrast, when using the virtuals, the registered class is really the <xref:System.Windows.UIElement> base class.</span></span> <span data-ttu-id="002a9-117">En casos donde las clases base como las subclases registran control de clases, se invocan en primer lugar los controladores de la subclase.</span><span class="sxs-lookup"><span data-stu-id="002a9-117">In cases where base classes and subclass each register class handling, the subclass handlers are invoked first.</span></span> <span data-ttu-id="002a9-118">El comportamiento en una aplicación sería que primero este controlador mostraría su cuadro de mensajes y, a continuación, se mostraría el cambio visual en el controlador del método virtual.</span><span class="sxs-lookup"><span data-stu-id="002a9-118">The behavior in an application would be that first this handler would show its message box and then the visual change in the virtual method's handler would be shown.</span></span>  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## <a name="see-also"></a><span data-ttu-id="002a9-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="002a9-119">See Also</span></span>  
 <xref:System.Windows.EventManager>  
 [<span data-ttu-id="002a9-120">Marcar eventos enrutados como controlados y control de clases</span><span class="sxs-lookup"><span data-stu-id="002a9-120">Marking Routed Events as Handled, and Class Handling</span></span>](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)  
 [<span data-ttu-id="002a9-121">Controlar un evento enrutado</span><span class="sxs-lookup"><span data-stu-id="002a9-121">Handle a Routed Event</span></span>](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md)  
 [<span data-ttu-id="002a9-122">Información general sobre eventos enrutados</span><span class="sxs-lookup"><span data-stu-id="002a9-122">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
