---
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
ms.openlocfilehash: 43738b2d654435532a98654cbc40af134d43f02c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410028"
---
# <a name="logging-information-from-the-application-visual-basic"></a><span data-ttu-id="ce939-102">Registrar información de la aplicación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce939-102">Logging Information from the Application (Visual Basic)</span></span>

<span data-ttu-id="ce939-103">Esta sección contiene temas que explican cómo registrar información sobre su aplicación usando el objeto `My.Application.Log` o `My.Log` y cómo ampliar las capacidades de registro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ce939-103">This section contains topics that cover how to log information from your application using the `My.Application.Log` or `My.Log` object, and how to extend the application's logging capabilities.</span></span>  
  
 <span data-ttu-id="ce939-104">El objeto `Log` proporciona métodos para escribir información en los agentes de escucha de registro de la aplicación y la propiedad avanzada `Log` del objeto `TraceSource` proporciona información de configuración detallada.</span><span class="sxs-lookup"><span data-stu-id="ce939-104">The `Log` object provides methods for writing information to the application's log listeners, and the `Log` object's advanced `TraceSource` property provides detailed configuration information.</span></span> <span data-ttu-id="ce939-105">El archivo de configuración de la aplicación configura el objeto `Log`.</span><span class="sxs-lookup"><span data-stu-id="ce939-105">The `Log` object is configured by the application's configuration file.</span></span>  
  
 <span data-ttu-id="ce939-106">El objeto `My.Log` solo está disponible para las aplicaciones ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ce939-106">The `My.Log` object is available only for ASP.NET applications.</span></span> <span data-ttu-id="ce939-107">Para las aplicaciones cliente, use `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="ce939-107">For client applications, use `My.Application.Log`.</span></span> <span data-ttu-id="ce939-108">Para obtener más información, vea <xref:Microsoft.VisualBasic.Logging.Log>.</span><span class="sxs-lookup"><span data-stu-id="ce939-108">For more information, see <xref:Microsoft.VisualBasic.Logging.Log>.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="ce939-109">Tareas</span><span class="sxs-lookup"><span data-stu-id="ce939-109">Tasks</span></span>  
  
|<span data-ttu-id="ce939-110">En</span><span class="sxs-lookup"><span data-stu-id="ce939-110">To</span></span>|<span data-ttu-id="ce939-111">Vea</span><span class="sxs-lookup"><span data-stu-id="ce939-111">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="ce939-112">Escribir información de eventos en los registros de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ce939-112">Write event information to the application's logs.</span></span>|[<span data-ttu-id="ce939-113">Cómo: Escribir mensajes de registro</span><span class="sxs-lookup"><span data-stu-id="ce939-113">How to: Write Log Messages</span></span>](how-to-write-log-messages.md)|  
|<span data-ttu-id="ce939-114">Escribir información de excepciones en los registros de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ce939-114">Write exception information to the application's logs.</span></span>|[<span data-ttu-id="ce939-115">Cómo: Registrar excepciones</span><span class="sxs-lookup"><span data-stu-id="ce939-115">How to: Log Exceptions</span></span>](how-to-log-exceptions.md)|  
|<span data-ttu-id="ce939-116">Escribir información de seguimiento en los registros de la aplicación cuando se inicia y se cierra la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ce939-116">Write trace information to the application's logs when the application starts and shuts down.</span></span>|[<span data-ttu-id="ce939-117">Cómo: Registrar mensajes cuando se inicia o se cierra la aplicación</span><span class="sxs-lookup"><span data-stu-id="ce939-117">How to: Log Messages When the Application Starts or Shuts Down</span></span>](how-to-log-messages-when-the-application-starts-or-shuts-down.md)|  
|<span data-ttu-id="ce939-118">Configurar `My.Application.Log` para que escriba información en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="ce939-118">Configure `My.Application.Log` to write information to a text file.</span></span>|[<span data-ttu-id="ce939-119">Cómo: Escribir información de eventos en un archivo de texto</span><span class="sxs-lookup"><span data-stu-id="ce939-119">How to: Write Event Information to a Text File</span></span>](how-to-write-event-information-to-a-text-file.md)|  
|<span data-ttu-id="ce939-120">Configurar `My.Application.Log` para escribir información en un registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="ce939-120">Configure `My.Application.Log` to write information to an event log.</span></span>|[<span data-ttu-id="ce939-121">Cómo: Escribir el registro de eventos de una aplicación</span><span class="sxs-lookup"><span data-stu-id="ce939-121">How to: Write to an Application Event Log</span></span>](how-to-write-to-an-application-event-log.md)|  
|<span data-ttu-id="ce939-122">Cambiar la ubicación dónde `My.Application.Log` escribe información.</span><span class="sxs-lookup"><span data-stu-id="ce939-122">Change where `My.Application.Log` writes information.</span></span>|[<span data-ttu-id="ce939-123">Tutorial: Cambiar el lugar en el que My.Application.Log escribe la información</span><span class="sxs-lookup"><span data-stu-id="ce939-123">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](walkthrough-changing-where-my-application-log-writes-information.md)|  
|<span data-ttu-id="ce939-124">Determinar dónde `My.Application.Log` escribe información.</span><span class="sxs-lookup"><span data-stu-id="ce939-124">Determine where `My.Application.Log` writes information.</span></span>|[<span data-ttu-id="ce939-125">Tutorial: Determinar el lugar en el que My.Application.Log escribe la información</span><span class="sxs-lookup"><span data-stu-id="ce939-125">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](walkthrough-determining-where-my-application-log-writes-information.md)|  
|<span data-ttu-id="ce939-126">Crear un agente de escucha de registro personalizado para `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="ce939-126">Create a custom log listener for `My.Application.Log`.</span></span>|[<span data-ttu-id="ce939-127">Tutorial: Crear agentes de escucha de registro personalizados</span><span class="sxs-lookup"><span data-stu-id="ce939-127">Walkthrough: Creating Custom Log Listeners</span></span>](walkthrough-creating-custom-log-listeners.md)|  
|<span data-ttu-id="ce939-128">Filtrar el resultado de los registros `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="ce939-128">Filter the output of the `My.Application.Log` logs.</span></span>|[<span data-ttu-id="ce939-129">Tutorial: Filtrar el resultado de My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="ce939-129">Walkthrough: Filtering My.Application.Log Output</span></span>](walkthrough-filtering-my-application-log-output.md)|  
  
## <a name="see-also"></a><span data-ttu-id="ce939-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce939-130">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [<span data-ttu-id="ce939-131">Trabajar con registros de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ce939-131">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="ce939-132">Solución de problemas: agentes de escucha de registro predeterminados</span><span class="sxs-lookup"><span data-stu-id="ce939-132">Troubleshooting: Log Listeners</span></span>](troubleshooting-log-listeners.md)
