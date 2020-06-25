---
title: Crear controladores de eventos
description: Obtenga información sobre cómo se pueden asignar eventos en Windows Forms a varios controladores y cómo se pueden cambiar dinámicamente los métodos que controlan eventos concretos.
ms.date: 03/30/2017
helpviewer_keywords:
- event handling [Windows Forms]
- Windows Forms controls, event handling
- Windows Forms, event handling
- events [Windows Forms], event handlers
- event handlers [Windows Forms]
ms.assetid: 6514e530-c6b8-489c-a8d2-eda7b7072701
ms.openlocfilehash: 4dca198be69c200ea8dfc741a43801bf8f631b9d
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85326019"
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="b8bb8-103">Crear controladores de eventos en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b8bb8-103">Creating Event Handlers in Windows Forms</span></span>

<span data-ttu-id="b8bb8-104">Un controlador de eventos es un procedimiento en el código que determina qué acciones se realizan cuando se produce un evento, por ejemplo, cuando el usuario hace clic en un botón o una cola de mensajes recibe un mensaje.</span><span class="sxs-lookup"><span data-stu-id="b8bb8-104">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="b8bb8-105">Cuando se genera un evento, se ejecutan los controladores de evento que reciben el evento.</span><span class="sxs-lookup"><span data-stu-id="b8bb8-105">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="b8bb8-106">Los eventos se pueden asignar a varios controladores y los métodos que controlan eventos determinados se pueden cambiar dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="b8bb8-106">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="b8bb8-107">También puede usar el Diseñador de Windows Forms de Visual Studio para crear controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="b8bb8-107">You can also use the Windows Forms Designer in Visual Studio to create event handlers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b8bb8-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b8bb8-108">In This Section</span></span>

 <span data-ttu-id="b8bb8-109">[Información general sobre eventos](events-overview-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="b8bb8-109">[Events Overview](events-overview-windows-forms.md)</span></span>\
 <span data-ttu-id="b8bb8-110">Explica el modelo de eventos y el rol de los delegados.</span><span class="sxs-lookup"><span data-stu-id="b8bb8-110">Explains the event model and the role of delegates.</span></span>

 <span data-ttu-id="b8bb8-111">[Información general sobre controladores de eventos](event-handlers-overview-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="b8bb8-111">[Event Handlers Overview](event-handlers-overview-windows-forms.md)</span></span>\
 <span data-ttu-id="b8bb8-112">Describe cómo controlar eventos.</span><span class="sxs-lookup"><span data-stu-id="b8bb8-112">Describes how to handle events.</span></span>

 <span data-ttu-id="b8bb8-113">[Cómo: crear controladores de eventos en tiempo de ejecución para Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="b8bb8-113">[How to: Create Event Handlers at Run Time for Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)</span></span>\
 <span data-ttu-id="b8bb8-114">Proporciona instrucciones para responder dinámicamente a los eventos de sistema o de usuario.</span><span class="sxs-lookup"><span data-stu-id="b8bb8-114">Gives directions for responding to system or user events dynamically.</span></span>

 <span data-ttu-id="b8bb8-115">[Cómo: conectar varios eventos a un solo controlador de eventos en Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="b8bb8-115">[How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)</span></span>\
 <span data-ttu-id="b8bb8-116">Proporciona instrucciones para asignar la misma funcionalidad a varios controles mediante eventos.</span><span class="sxs-lookup"><span data-stu-id="b8bb8-116">Gives directions for assigning the same functionality to multiple controls through events.</span></span>

 <span data-ttu-id="b8bb8-117">[Orden de los eventos en Windows Forms](order-of-events-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="b8bb8-117">[Order of Events in Windows Forms](order-of-events-in-windows-forms.md)</span></span>\
 <span data-ttu-id="b8bb8-118">Describe el orden con el que se generan los eventos en los controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b8bb8-118">Describes the order in which events are raised in Windows Forms controls.</span></span>

 <span data-ttu-id="b8bb8-119">[Cómo: crear controladores de eventos mediante el diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Describe cómo usar la Diseñador de Windows Forms para crear controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="b8bb8-119">[How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Describes how to use the Windows Forms Designer to create event handlers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="b8bb8-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="b8bb8-120">Related Sections</span></span>

 <span data-ttu-id="b8bb8-121">[Ceso](../../standard/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="b8bb8-121">[Events](../../standard/events/index.md)</span></span>\
 <span data-ttu-id="b8bb8-122">Proporciona vínculos a temas sobre cómo controlar y generar eventos mediante el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b8bb8-122">Provides links to topics on handling and raising events using the .NET Framework.</span></span>

 <span data-ttu-id="b8bb8-123">[Solución de problemas de controladores de eventos heredados en Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)</span><span class="sxs-lookup"><span data-stu-id="b8bb8-123">[Troubleshooting Inherited Event Handlers in Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)</span></span>\
 <span data-ttu-id="b8bb8-124">Enumera los problemas habituales que se producen con los controladores de evento en componentes heredados.</span><span class="sxs-lookup"><span data-stu-id="b8bb8-124">Lists common issues that occur with event handlers in inherited components.</span></span>
