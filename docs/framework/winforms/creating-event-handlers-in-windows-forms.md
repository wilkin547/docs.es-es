---
title: Crear controladores de eventos en formularios Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- event handling [Windows Forms]
- Windows Forms controls, event handling
- Windows Forms, event handling
- events [Windows Forms], event handlers
- event handlers [Windows Forms]
ms.assetid: 6514e530-c6b8-489c-a8d2-eda7b7072701
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a18afd8ba06b5bcc70ca5a6febc10be8050891b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="0594e-102">Crear controladores de eventos en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0594e-102">Creating Event Handlers in Windows Forms</span></span>
<span data-ttu-id="0594e-103">Un controlador de eventos es un procedimiento en el código que determina qué acciones se realizan cuando se produce un evento, por ejemplo, cuando el usuario hace clic en un botón o una cola de mensajes recibe un mensaje.</span><span class="sxs-lookup"><span data-stu-id="0594e-103">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="0594e-104">Cuando se genera un evento, se ejecutan los controladores de evento que reciben el evento.</span><span class="sxs-lookup"><span data-stu-id="0594e-104">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="0594e-105">Los eventos se pueden asignar a varios controladores y los métodos que controlan eventos determinados se pueden cambiar dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="0594e-105">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="0594e-106">También puede usar el Diseñador de Windows Forms para crear controladores de evento.</span><span class="sxs-lookup"><span data-stu-id="0594e-106">You can also use the Windows Forms Designer to create event handlers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0594e-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0594e-107">In This Section</span></span>  
 [<span data-ttu-id="0594e-108">Información general sobre eventos</span><span class="sxs-lookup"><span data-stu-id="0594e-108">Events Overview</span></span>](../../../docs/framework/winforms/events-overview-windows-forms.md)  
 <span data-ttu-id="0594e-109">Explica el modelo de eventos y el rol de los delegados.</span><span class="sxs-lookup"><span data-stu-id="0594e-109">Explains the event model and the role of delegates.</span></span>  
  
 [<span data-ttu-id="0594e-110">Información general sobre controladores de eventos</span><span class="sxs-lookup"><span data-stu-id="0594e-110">Event Handlers Overview</span></span>](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)  
 <span data-ttu-id="0594e-111">Describe cómo controlar eventos.</span><span class="sxs-lookup"><span data-stu-id="0594e-111">Describes how to handle events.</span></span>  
  
 [<span data-ttu-id="0594e-112">Cómo: Crear controladores de eventos en tiempo de ejecución para Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0594e-112">How to: Create Event Handlers at Run Time for Windows Forms</span></span>](../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md)  
 <span data-ttu-id="0594e-113">Proporciona instrucciones para responder dinámicamente a los eventos de sistema o de usuario.</span><span class="sxs-lookup"><span data-stu-id="0594e-113">Gives directions for responding to system or user events dynamically.</span></span>  
  
 [<span data-ttu-id="0594e-114">Cómo: Conectar varios eventos con un único controlador de eventos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0594e-114">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>](../../../docs/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)  
 <span data-ttu-id="0594e-115">Proporciona instrucciones para asignar la misma funcionalidad a varios controles mediante eventos.</span><span class="sxs-lookup"><span data-stu-id="0594e-115">Gives directions for assigning the same functionality to multiple controls through events.</span></span>  
  
 [<span data-ttu-id="0594e-116">Orden de eventos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0594e-116">Order of Events in Windows Forms</span></span>](../../../docs/framework/winforms/order-of-events-in-windows-forms.md)  
 <span data-ttu-id="0594e-117">Describe el orden con el que se generan los eventos en los controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0594e-117">Describes the order in which events are raised in Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="0594e-118">Cómo: Crear controladores de eventos mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="0594e-118">How to: Create Event Handlers Using the Designer</span></span>](http://msdn.microsoft.com/en-us/8461e9b8-14e8-406f-936e-3726732b23d2)  
 <span data-ttu-id="0594e-119">Describe cómo usar el Diseñador de Windows Forms para crear controladores de evento.</span><span class="sxs-lookup"><span data-stu-id="0594e-119">Describes how to use the Windows Forms Designer to create event handlers.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0594e-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="0594e-120">Related Sections</span></span>  
 [<span data-ttu-id="0594e-121">Eventos</span><span class="sxs-lookup"><span data-stu-id="0594e-121">Events</span></span>](../../../docs/standard/events/index.md)  
 <span data-ttu-id="0594e-122">Proporciona vínculos a los temas sobre cómo controlar y generar eventos mediante [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0594e-122">Provides links to topics on handling and raising events using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
 [<span data-ttu-id="0594e-123">Solucionar problemas de controladores de eventos heredados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0594e-123">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 <span data-ttu-id="0594e-124">Enumera los problemas habituales que se producen con los controladores de evento en componentes heredados.</span><span class="sxs-lookup"><span data-stu-id="0594e-124">Lists common issues that occur with event handlers in inherited components.</span></span>
