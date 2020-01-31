---
title: Crear controladores de eventos
ms.date: 03/30/2017
helpviewer_keywords:
- event handling [Windows Forms]
- Windows Forms controls, event handling
- Windows Forms, event handling
- events [Windows Forms], event handlers
- event handlers [Windows Forms]
ms.assetid: 6514e530-c6b8-489c-a8d2-eda7b7072701
ms.openlocfilehash: 90acb3c7691acbcb528ae66692af67c2fb28eeaf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742336"
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="c4875-102">Crear controladores de eventos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c4875-102">Creating Event Handlers in Windows Forms</span></span>

<span data-ttu-id="c4875-103">Un controlador de eventos es un procedimiento en el código que determina qué acciones se realizan cuando se produce un evento, por ejemplo, cuando el usuario hace clic en un botón o una cola de mensajes recibe un mensaje.</span><span class="sxs-lookup"><span data-stu-id="c4875-103">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="c4875-104">Cuando se genera un evento, se ejecutan los controladores de evento que reciben el evento.</span><span class="sxs-lookup"><span data-stu-id="c4875-104">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="c4875-105">Los eventos se pueden asignar a varios controladores y los métodos que controlan eventos determinados se pueden cambiar dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="c4875-105">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="c4875-106">También puede usar el Diseñador de Windows Forms de Visual Studio para crear controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="c4875-106">You can also use the Windows Forms Designer in Visual Studio to create event handlers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c4875-107">Esta sección</span><span class="sxs-lookup"><span data-stu-id="c4875-107">In This Section</span></span>

 <span data-ttu-id="c4875-108">[Información general sobre eventos](events-overview-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="c4875-108">[Events Overview](events-overview-windows-forms.md)</span></span>\
 <span data-ttu-id="c4875-109">Explica el modelo de eventos y el rol de los delegados.</span><span class="sxs-lookup"><span data-stu-id="c4875-109">Explains the event model and the role of delegates.</span></span>

 <span data-ttu-id="c4875-110">[Información general sobre controladores de eventos](event-handlers-overview-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="c4875-110">[Event Handlers Overview](event-handlers-overview-windows-forms.md)</span></span>\
 <span data-ttu-id="c4875-111">Describe cómo controlar eventos.</span><span class="sxs-lookup"><span data-stu-id="c4875-111">Describes how to handle events.</span></span>

 <span data-ttu-id="c4875-112">[Cómo: crear controladores de eventos en tiempo de ejecución para Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="c4875-112">[How to: Create Event Handlers at Run Time for Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)</span></span>\
 <span data-ttu-id="c4875-113">Proporciona instrucciones para responder dinámicamente a los eventos de sistema o de usuario.</span><span class="sxs-lookup"><span data-stu-id="c4875-113">Gives directions for responding to system or user events dynamically.</span></span>

 <span data-ttu-id="c4875-114">[Cómo: conectar varios eventos a un solo controlador de eventos en Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="c4875-114">[How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)</span></span>\
 <span data-ttu-id="c4875-115">Proporciona instrucciones para asignar la misma funcionalidad a varios controles mediante eventos.</span><span class="sxs-lookup"><span data-stu-id="c4875-115">Gives directions for assigning the same functionality to multiple controls through events.</span></span>

 <span data-ttu-id="c4875-116">[Orden de los eventos en Windows Forms](order-of-events-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="c4875-116">[Order of Events in Windows Forms](order-of-events-in-windows-forms.md)</span></span>\
 <span data-ttu-id="c4875-117">Describe el orden con el que se generan los eventos en los controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c4875-117">Describes the order in which events are raised in Windows Forms controls.</span></span>

 <span data-ttu-id="c4875-118">[Cómo: crear controladores de eventos mediante el diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Describe cómo usar la Diseñador de Windows Forms para crear controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="c4875-118">[How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Describes how to use the Windows Forms Designer to create event handlers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="c4875-119">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="c4875-119">Related Sections</span></span>

 <span data-ttu-id="c4875-120">[Eventos](../../standard/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="c4875-120">[Events](../../standard/events/index.md)</span></span>\
 <span data-ttu-id="c4875-121">Proporciona vínculos a temas sobre cómo controlar y generar eventos mediante el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c4875-121">Provides links to topics on handling and raising events using the .NET Framework.</span></span>

 <span data-ttu-id="c4875-122">[Solucionar problemas de controladores de eventos heredados en Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)</span><span class="sxs-lookup"><span data-stu-id="c4875-122">[Troubleshooting Inherited Event Handlers in Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)</span></span>\
 <span data-ttu-id="c4875-123">Enumera los problemas habituales que se producen con los controladores de evento en componentes heredados.</span><span class="sxs-lookup"><span data-stu-id="c4875-123">Lists common issues that occur with event handlers in inherited components.</span></span>
