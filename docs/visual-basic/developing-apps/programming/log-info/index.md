---
description: 'Más información acerca de: Registrar información de la aplicación (Visual Basic)'
title: Registrar información de la aplicación
ms.date: 07/20/2015
helpviewer_keywords:
- Log object
- My.Log object
- applications [Visual Basic], logging information from
- logging
- My.Application.Log object
- examples [Visual Basic], logging application information
ms.assetid: 8bf4f047-22d6-48d6-aec5-93b98ad5b8e8
ms.openlocfilehash: 6e0adf45c12d98c8bc6d177d85accf9bee347f75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99775076"
---
# <a name="logging-information-from-the-application-visual-basic"></a><span data-ttu-id="a2cfe-103">Registrar información de la aplicación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2cfe-103">Logging Information from the Application (Visual Basic)</span></span>

<span data-ttu-id="a2cfe-104">Esta sección contiene temas que explican cómo registrar información sobre su aplicación usando el objeto `My.Application.Log` o `My.Log` y cómo ampliar las capacidades de registro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a2cfe-104">This section contains topics that cover how to log information from your application using the `My.Application.Log` or `My.Log` object, and how to extend the application's logging capabilities.</span></span>  
  
 <span data-ttu-id="a2cfe-105">El objeto `Log` proporciona métodos para escribir información en los agentes de escucha de registro de la aplicación y la propiedad avanzada `Log` del objeto `TraceSource` proporciona información de configuración detallada.</span><span class="sxs-lookup"><span data-stu-id="a2cfe-105">The `Log` object provides methods for writing information to the application's log listeners, and the `Log` object's advanced `TraceSource` property provides detailed configuration information.</span></span> <span data-ttu-id="a2cfe-106">El archivo de configuración de la aplicación configura el objeto `Log`.</span><span class="sxs-lookup"><span data-stu-id="a2cfe-106">The `Log` object is configured by the application's configuration file.</span></span>  
  
 <span data-ttu-id="a2cfe-107">El objeto `My.Log` solo está disponible para las aplicaciones ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a2cfe-107">The `My.Log` object is available only for ASP.NET applications.</span></span> <span data-ttu-id="a2cfe-108">Para las aplicaciones cliente, use `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="a2cfe-108">For client applications, use `My.Application.Log`.</span></span> <span data-ttu-id="a2cfe-109">Para obtener más información, vea <xref:Microsoft.VisualBasic.Logging.Log>.</span><span class="sxs-lookup"><span data-stu-id="a2cfe-109">For more information, see <xref:Microsoft.VisualBasic.Logging.Log>.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="a2cfe-110">Tareas</span><span class="sxs-lookup"><span data-stu-id="a2cfe-110">Tasks</span></span>  
  
|<span data-ttu-id="a2cfe-111">En</span><span class="sxs-lookup"><span data-stu-id="a2cfe-111">To</span></span>|<span data-ttu-id="a2cfe-112">Vea</span><span class="sxs-lookup"><span data-stu-id="a2cfe-112">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="a2cfe-113">Escribir información de eventos en los registros de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a2cfe-113">Write event information to the application's logs.</span></span>|[<span data-ttu-id="a2cfe-114">Cómo: Escribir mensajes de registro</span><span class="sxs-lookup"><span data-stu-id="a2cfe-114">How to: Write Log Messages</span></span>](how-to-write-log-messages.md)|  
|<span data-ttu-id="a2cfe-115">Escribir información de excepciones en los registros de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a2cfe-115">Write exception information to the application's logs.</span></span>|[<span data-ttu-id="a2cfe-116">Cómo: Registrar excepciones</span><span class="sxs-lookup"><span data-stu-id="a2cfe-116">How to: Log Exceptions</span></span>](how-to-log-exceptions.md)|  
|<span data-ttu-id="a2cfe-117">Escribir información de seguimiento en los registros de la aplicación cuando se inicia y se cierra la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a2cfe-117">Write trace information to the application's logs when the application starts and shuts down.</span></span>|[<span data-ttu-id="a2cfe-118">Cómo: Registrar mensajes cuando se inicia o se cierra la aplicación</span><span class="sxs-lookup"><span data-stu-id="a2cfe-118">How to: Log Messages When the Application Starts or Shuts Down</span></span>](how-to-log-messages-when-the-application-starts-or-shuts-down.md)|  
|<span data-ttu-id="a2cfe-119">Configurar `My.Application.Log` para que escriba información en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="a2cfe-119">Configure `My.Application.Log` to write information to a text file.</span></span>|[<span data-ttu-id="a2cfe-120">Cómo: Escribir información de eventos en un archivo de texto</span><span class="sxs-lookup"><span data-stu-id="a2cfe-120">How to: Write Event Information to a Text File</span></span>](how-to-write-event-information-to-a-text-file.md)|  
|<span data-ttu-id="a2cfe-121">Configurar `My.Application.Log` para escribir información en un registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="a2cfe-121">Configure `My.Application.Log` to write information to an event log.</span></span>|[<span data-ttu-id="a2cfe-122">Cómo: Escribir el registro de eventos de una aplicación</span><span class="sxs-lookup"><span data-stu-id="a2cfe-122">How to: Write to an Application Event Log</span></span>](how-to-write-to-an-application-event-log.md)|  
|<span data-ttu-id="a2cfe-123">Cambiar la ubicación dónde `My.Application.Log` escribe información.</span><span class="sxs-lookup"><span data-stu-id="a2cfe-123">Change where `My.Application.Log` writes information.</span></span>|[<span data-ttu-id="a2cfe-124">Tutorial: Cambiar el lugar en el que My.Application.Log escribe la información</span><span class="sxs-lookup"><span data-stu-id="a2cfe-124">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](walkthrough-changing-where-my-application-log-writes-information.md)|  
|<span data-ttu-id="a2cfe-125">Determinar dónde `My.Application.Log` escribe información.</span><span class="sxs-lookup"><span data-stu-id="a2cfe-125">Determine where `My.Application.Log` writes information.</span></span>|[<span data-ttu-id="a2cfe-126">Tutorial: Determinar el lugar en el que My.Application.Log escribe la información</span><span class="sxs-lookup"><span data-stu-id="a2cfe-126">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](walkthrough-determining-where-my-application-log-writes-information.md)|  
|<span data-ttu-id="a2cfe-127">Crear un agente de escucha de registro personalizado para `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="a2cfe-127">Create a custom log listener for `My.Application.Log`.</span></span>|[<span data-ttu-id="a2cfe-128">Tutorial: Crear agentes de escucha de registro personalizados</span><span class="sxs-lookup"><span data-stu-id="a2cfe-128">Walkthrough: Creating Custom Log Listeners</span></span>](walkthrough-creating-custom-log-listeners.md)|  
|<span data-ttu-id="a2cfe-129">Filtrar el resultado de los registros `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="a2cfe-129">Filter the output of the `My.Application.Log` logs.</span></span>|[<span data-ttu-id="a2cfe-130">Tutorial: Filtrar el resultado de My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="a2cfe-130">Walkthrough: Filtering My.Application.Log Output</span></span>](walkthrough-filtering-my-application-log-output.md)|  
  
## <a name="see-also"></a><span data-ttu-id="a2cfe-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2cfe-131">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [<span data-ttu-id="a2cfe-132">Trabajar con registros de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="a2cfe-132">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="a2cfe-133">Solución de problemas: agentes de escucha de registro predeterminados</span><span class="sxs-lookup"><span data-stu-id="a2cfe-133">Troubleshooting: Log Listeners</span></span>](troubleshooting-log-listeners.md)
