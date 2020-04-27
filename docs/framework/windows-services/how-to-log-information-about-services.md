---
title: Procedimiento para registrar información sobre servicios
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutoLog property
- services, logging information
- Windows Service applications, logging information about
- event logs, service applications
- application event logs, service applications
- logs, service applications
ms.assetid: c0d8140f-c055-4d8e-a2e0-37358a550116
author: ghogen
ms.openlocfilehash: 3c974d5a98f8056e45899b109878e5a28ab2938e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053609"
---
# <a name="how-to-log-information-about-services"></a><span data-ttu-id="e1908-102">Procedimiento para registrar información sobre servicios</span><span class="sxs-lookup"><span data-stu-id="e1908-102">How to: Log Information About Services</span></span>
<span data-ttu-id="e1908-103">De forma predeterminada, todos los proyectos de servicio de Windows tienen la capacidad de interactuar con el registro de eventos de la aplicación y escriben información y excepciones en él.</span><span class="sxs-lookup"><span data-stu-id="e1908-103">By default, all Windows Service projects have the ability to interact with the Application event log and write information and exceptions to it.</span></span> <span data-ttu-id="e1908-104">Utilice la propiedad <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> para indicar si quiere esta funcionalidad en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e1908-104">You use the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property to indicate whether you want this functionality in your application.</span></span> <span data-ttu-id="e1908-105">De forma predeterminada, el registro está activado para cualquier servicio que se cree con la plantilla de proyecto de servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="e1908-105">By default, logging is turned on for any service you create with the Windows Service project template.</span></span> <span data-ttu-id="e1908-106">Puede utilizar una forma estática de la clase <xref:System.Diagnostics.EventLog> para escribir información de servicio en un registro sin tener que crear una instancia de un componente <xref:System.Diagnostics.EventLog> ni registrar manualmente un origen.</span><span class="sxs-lookup"><span data-stu-id="e1908-106">You can use a static form of the <xref:System.Diagnostics.EventLog> class to write service information to a log without having to create an instance of an <xref:System.Diagnostics.EventLog> component or manually register a source.</span></span>  
  
 <span data-ttu-id="e1908-107">El instalador del servicio registra automáticamente cada uno de los servicios del proyecto como un origen de eventos válido con el registro de aplicaciones en el equipo donde está instalado el servicio, cuando el registro está activado.</span><span class="sxs-lookup"><span data-stu-id="e1908-107">The installer for your service automatically registers each service in your project as a valid source of events with the Application log on the computer where the service is installed, when logging is turned on.</span></span> <span data-ttu-id="e1908-108">El servicio registra información cada vez que el servicio se inicia, se detiene, se pone en pausa, se reanuda, se instala o se desinstala.</span><span class="sxs-lookup"><span data-stu-id="e1908-108">The service logs information each time the service is started, stopped, paused, resumed, installed, or uninstalled.</span></span> <span data-ttu-id="e1908-109">También registra los errores que se producen.</span><span class="sxs-lookup"><span data-stu-id="e1908-109">It also logs any failures that occur.</span></span> <span data-ttu-id="e1908-110">No es necesario escribir nada de código para escribir entradas en el registro cuando se utiliza el comportamiento predeterminado; el servicio se encarga de ello automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e1908-110">You do not need to write any code to write entries to the log when using the default behavior; the service handles this for you automatically.</span></span>  
  
 <span data-ttu-id="e1908-111">Si quiere escribir en un registro de eventos distinto del registro de aplicaciones, debe establecer la propiedad <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> en `false`, crear su propio registro de eventos personalizado dentro del código de servicios y registrar el servicio como un origen válido de entradas para este registro.</span><span class="sxs-lookup"><span data-stu-id="e1908-111">If you want to write to an event log other than the Application log, you must set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property to `false`, create your own custom event log within your services code, and register your service as a valid source of entries for that log.</span></span> <span data-ttu-id="e1908-112">Después, debe escribir código para registrar las entradas en el registro cada vez que se produzca una acción que le interese.</span><span class="sxs-lookup"><span data-stu-id="e1908-112">You must then write code to record entries to the log whenever an action you're interested in occurs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1908-113">Si utiliza un registro de eventos personalizado y configura la aplicación de servicio para escribir en él, no debe intentar acceder al registro de eventos antes de establecer la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> del servicio en el código.</span><span class="sxs-lookup"><span data-stu-id="e1908-113">If you use a custom event log and configure your service application to write to it, you must not attempt to access the event log before setting the service's <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property in your code.</span></span> <span data-ttu-id="e1908-114">El registro de eventos necesita el valor de esta propiedad para registrar el servicio como un origen válido de eventos.</span><span class="sxs-lookup"><span data-stu-id="e1908-114">The event log needs this property's value to register your service as a valid source of events.</span></span>  
  
### <a name="to-enable-default-event-logging-for-your-service"></a><span data-ttu-id="e1908-115">Para habilitar el registro de eventos predeterminado para el servicio</span><span class="sxs-lookup"><span data-stu-id="e1908-115">To enable default event logging for your service</span></span>  
  
- <span data-ttu-id="e1908-116">Establezca la propiedad <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> del componente a `true`.</span><span class="sxs-lookup"><span data-stu-id="e1908-116">Set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property for your component to `true`.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e1908-117">De manera predeterminada, esta propiedad está establecida en `true`.</span><span class="sxs-lookup"><span data-stu-id="e1908-117">By default, this property is set to `true`.</span></span> <span data-ttu-id="e1908-118">No necesitará establecerla explícitamente a menos que esté creando procesamientos más complejos, tales como la evaluación de una condición y el posterior establecimiento de la propiedad <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> según el resultado de esa condición.</span><span class="sxs-lookup"><span data-stu-id="e1908-118">You do not need to set this explicitly unless you are building more complex processing, such as evaluating a condition and then setting the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property based on the result of that condition.</span></span>  
  
### <a name="to-disable-event-logging-for-your-service"></a><span data-ttu-id="e1908-119">Para deshabilitar el registro de eventos para el servicio</span><span class="sxs-lookup"><span data-stu-id="e1908-119">To disable event logging for your service</span></span>  
  
- <span data-ttu-id="e1908-120">Establezca la propiedad <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> del componente a `false`.</span><span class="sxs-lookup"><span data-stu-id="e1908-120">Set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property for your component to `false`.</span></span>  
  
     [!code-csharp[VbRadconService#17](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#17)]
     [!code-vb[VbRadconService#17](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#17)]  
  
### <a name="to-set-up-logging-to-a-custom-log"></a><span data-ttu-id="e1908-121">Para configurar el registro en un registro personalizado</span><span class="sxs-lookup"><span data-stu-id="e1908-121">To set up logging to a custom log</span></span>  
  
1. <span data-ttu-id="e1908-122">Establezca la propiedad <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="e1908-122">Set the <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> property to `false`.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e1908-123">Debe establecer el valor de <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> en false para poder utilizar un registro personalizado.</span><span class="sxs-lookup"><span data-stu-id="e1908-123">You must set <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> to false in order to use a custom log.</span></span>  
  
2. <span data-ttu-id="e1908-124">Configure una instancia de un componente <xref:System.Diagnostics.EventLog> en la aplicación de servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="e1908-124">Set up an instance of an <xref:System.Diagnostics.EventLog> component in your Windows Service application.</span></span>  
  
3. <span data-ttu-id="e1908-125">Cree un registro personalizado mediante una llamada al método <xref:System.Diagnostics.EventLog.CreateEventSource%2A> y especifique la cadena de origen y el nombre del archivo de registro que quiere crear.</span><span class="sxs-lookup"><span data-stu-id="e1908-125">Create a custom log by calling the <xref:System.Diagnostics.EventLog.CreateEventSource%2A> method and specifying the source string and the name of the log file you want to create.</span></span>  
  
4. <span data-ttu-id="e1908-126">Establezca la propiedad <xref:System.Diagnostics.EventLog.Source%2A> de la instancia de componente <xref:System.Diagnostics.EventLog> en la cadena de origen que creó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="e1908-126">Set the <xref:System.Diagnostics.EventLog.Source%2A> property on the <xref:System.Diagnostics.EventLog> component instance to the source string you created in step 3.</span></span>  
  
5. <span data-ttu-id="e1908-127">Escriba las entradas mediante el acceso al método <xref:System.Diagnostics.EventLog.WriteEntry%2A> en la instancia de componente <xref:System.Diagnostics.EventLog> .</span><span class="sxs-lookup"><span data-stu-id="e1908-127">Write your entries by accessing the <xref:System.Diagnostics.EventLog.WriteEntry%2A> method on the <xref:System.Diagnostics.EventLog> component instance.</span></span>  
  
     <span data-ttu-id="e1908-128">El código siguiente muestra cómo configurar el registro en un registro personalizado.</span><span class="sxs-lookup"><span data-stu-id="e1908-128">The following code shows how to set up logging to a custom log.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e1908-129">En este ejemplo de código, una instancia de un componente <xref:System.Diagnostics.EventLog> se denomina `eventLog1` (`EventLog1` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="e1908-129">In this code example, an instance of an <xref:System.Diagnostics.EventLog> component is named `eventLog1` (`EventLog1` in Visual Basic).</span></span> <span data-ttu-id="e1908-130">Si ha creado una instancia con otro nombre en el paso 2, cambie el código de forma acorde.</span><span class="sxs-lookup"><span data-stu-id="e1908-130">If you created an instance with another name in step 2, change the code accordingly.</span></span>  
  
     [!code-csharp[VbRadconService#14](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#14)]
     [!code-vb[VbRadconService#14](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#14)]  
    [!code-csharp[VbRadconService#15](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#15)]
    [!code-vb[VbRadconService#15](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="e1908-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1908-131">See also</span></span>

- [<span data-ttu-id="e1908-132">Introducción a las aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="e1908-132">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
