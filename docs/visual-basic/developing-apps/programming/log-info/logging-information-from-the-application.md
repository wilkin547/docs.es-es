---
title: "Registrar información de la aplicación (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Log object
- My.Log object
- applications [Visual Basic], logging information from
- logging
- My.Application.Log object
- examples [Visual Basic], logging application information
ms.assetid: 8bf4f047-22d6-48d6-aec5-93b98ad5b8e8
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e52aaf4c26b4fa60ee04d7df6aa96980ebbf491
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="logging-information-from-the-application-visual-basic"></a><span data-ttu-id="01efa-102">Registrar información de la aplicación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01efa-102">Logging Information from the Application (Visual Basic)</span></span>
<span data-ttu-id="01efa-103">Esta sección contiene temas que explican cómo registrar información sobre su aplicación usando el objeto `My.Application.Log` o `My.Log` y cómo ampliar las capacidades de registro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="01efa-103">This section contains topics that cover how to log information from your application using the `My.Application.Log` or `My.Log` object, and how to extend the application's logging capabilities.</span></span>  
  
 <span data-ttu-id="01efa-104">El objeto `Log` proporciona métodos para escribir información en los agentes de escucha de registro de la aplicación y la propiedad avanzada `Log` del objeto `TraceSource` proporciona información de configuración detallada.</span><span class="sxs-lookup"><span data-stu-id="01efa-104">The `Log` object provides methods for writing information to the application's log listeners, and the `Log` object's advanced `TraceSource` property provides detailed configuration information.</span></span> <span data-ttu-id="01efa-105">El archivo de configuración de la aplicación configura el objeto `Log`.</span><span class="sxs-lookup"><span data-stu-id="01efa-105">The `Log` object is configured by the application's configuration file.</span></span>  
  
 <span data-ttu-id="01efa-106">El objeto `My.Log` solo está disponible para las aplicaciones ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="01efa-106">The `My.Log` object is available only for ASP.NET applications.</span></span> <span data-ttu-id="01efa-107">Para las aplicaciones cliente, use `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="01efa-107">For client applications, use `My.Application.Log`.</span></span> <span data-ttu-id="01efa-108">Para obtener más información, consulta <xref:Microsoft.VisualBasic.Logging.Log>.</span><span class="sxs-lookup"><span data-stu-id="01efa-108">For more information, see <xref:Microsoft.VisualBasic.Logging.Log>.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="01efa-109">Tareas</span><span class="sxs-lookup"><span data-stu-id="01efa-109">Tasks</span></span>  
  
|<span data-ttu-id="01efa-110">Para</span><span class="sxs-lookup"><span data-stu-id="01efa-110">To</span></span>|<span data-ttu-id="01efa-111">Vea</span><span class="sxs-lookup"><span data-stu-id="01efa-111">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="01efa-112">Escribir información de eventos en los registros de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="01efa-112">Write event information to the application's logs.</span></span>|[<span data-ttu-id="01efa-113">Escribir mensajes de registro</span><span class="sxs-lookup"><span data-stu-id="01efa-113">How to: Write Log Messages</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)|  
|<span data-ttu-id="01efa-114">Escribir información de excepciones en los registros de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="01efa-114">Write exception information to the application's logs.</span></span>|[<span data-ttu-id="01efa-115">Registrar excepciones</span><span class="sxs-lookup"><span data-stu-id="01efa-115">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)|  
|<span data-ttu-id="01efa-116">Escribir información de seguimiento en los registros de la aplicación cuando se inicia y se cierra la aplicación.</span><span class="sxs-lookup"><span data-stu-id="01efa-116">Write trace information to the application's logs when the application starts and shuts down.</span></span>|[<span data-ttu-id="01efa-117">Registrar mensajes cuando se inicia o se cierra la aplicación</span><span class="sxs-lookup"><span data-stu-id="01efa-117">How to: Log Messages When the Application Starts or Shuts Down</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-messages-when-the-application-starts-or-shuts-down.md)|  
|<span data-ttu-id="01efa-118">Configurar `My.Application.Log` para que escriba información en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="01efa-118">Configure `My.Application.Log` to write information to a text file.</span></span>|[<span data-ttu-id="01efa-119">Escribir información de eventos en un archivo de texto</span><span class="sxs-lookup"><span data-stu-id="01efa-119">How to: Write Event Information to a Text File</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md)|  
|<span data-ttu-id="01efa-120">Configurar `My.Application.Log` para escribir información en un registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="01efa-120">Configure `My.Application.Log` to write information to an event log.</span></span>|[<span data-ttu-id="01efa-121">Cómo: Escribir el registro de eventos de una aplicación</span><span class="sxs-lookup"><span data-stu-id="01efa-121">How to: Write to an Application Event Log</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md)|  
|<span data-ttu-id="01efa-122">Cambiar la ubicación dónde `My.Application.Log` escribe información.</span><span class="sxs-lookup"><span data-stu-id="01efa-122">Change where `My.Application.Log` writes information.</span></span>|[<span data-ttu-id="01efa-123">Tutorial: Cambiar el lugar donde My.Application.Log escribe información</span><span class="sxs-lookup"><span data-stu-id="01efa-123">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)|  
|<span data-ttu-id="01efa-124">Determinar dónde `My.Application.Log` escribe información.</span><span class="sxs-lookup"><span data-stu-id="01efa-124">Determine where `My.Application.Log` writes information.</span></span>|[<span data-ttu-id="01efa-125">Tutorial: Determinar el lugar en el que My.Application.Log escribe la información</span><span class="sxs-lookup"><span data-stu-id="01efa-125">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)|  
|<span data-ttu-id="01efa-126">Crear un agente de escucha de registro personalizado para `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="01efa-126">Create a custom log listener for `My.Application.Log`.</span></span>|[<span data-ttu-id="01efa-127">Tutorial: Crear agentes de escucha de registro personalizados</span><span class="sxs-lookup"><span data-stu-id="01efa-127">Walkthrough: Creating Custom Log Listeners</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md)|  
|<span data-ttu-id="01efa-128">Filtrar el resultado de los registros `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="01efa-128">Filter the output of the `My.Application.Log` logs.</span></span>|[<span data-ttu-id="01efa-129">Tutorial: Filtrar el resultado de My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="01efa-129">Walkthrough: Filtering My.Application.Log Output</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)|  
  
## <a name="see-also"></a><span data-ttu-id="01efa-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="01efa-130">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 [<span data-ttu-id="01efa-131">Trabajar con registros de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="01efa-131">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [<span data-ttu-id="01efa-132">Solución de problemas: Agentes de escucha de registro</span><span class="sxs-lookup"><span data-stu-id="01efa-132">Troubleshooting: Log Listeners</span></span>](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)
