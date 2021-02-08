---
description: 'Más información acerca de: interfaces de hospedaje de CLR'
title: Interfaces de hospedaje de CLR
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
ms.openlocfilehash: f42a74698607ffbed4a981f061d13ea4e9d634d8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799907"
---
# <a name="clr-hosting-interfaces"></a><span data-ttu-id="512ad-103">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="512ad-103">CLR Hosting Interfaces</span></span>

<span data-ttu-id="512ad-104">En esta sección se describen las interfaces que los hosts no administrados pueden utilizar para integrar el Common Language Runtime (CLR) en sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="512ad-104">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span> <span data-ttu-id="512ad-105">La información pertenece a la .NET Framework versión 2,0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="512ad-105">The information pertains to the .NET Framework version 2.0 and later versions.</span></span> <span data-ttu-id="512ad-106">Estas interfaces permiten al host controlar muchos más aspectos del tiempo de ejecución que los que era posible en las versiones 1,0 y 1,1, y proporcionan una mayor integración entre CLR y el modelo de ejecución del host.</span><span class="sxs-lookup"><span data-stu-id="512ad-106">These interfaces enable the host to control many more aspects of the runtime than was possible in versions 1.0 and 1.1, and provide much tighter integration between the CLR and the host's execution model.</span></span>  
  
 <span data-ttu-id="512ad-107">En la .NET Framework versión 1,0 y 1,1, el modelo de hospedaje habilitaba un host no administrado para cargar CLR en un proceso, para configurar determinadas opciones y para recibir notificaciones de eventos.</span><span class="sxs-lookup"><span data-stu-id="512ad-107">In the .NET Framework version 1.0 and 1.1, the hosting model enabled an unmanaged host to load the CLR into a process, to configure certain settings, and to receive event notifications.</span></span> <span data-ttu-id="512ad-108">Sin embargo, en general, el host y el CLR se ejecutaban de forma independiente en ese proceso.</span><span class="sxs-lookup"><span data-stu-id="512ad-108">However, in general, the host and the CLR ran independently in that process.</span></span> <span data-ttu-id="512ad-109">En la .NET Framework versión 2,0 y versiones posteriores, las nuevas capas de abstracción permiten que el host proporcione muchos de los recursos que proporcionan actualmente los tipos del ensamblado Win32 y que amplían el conjunto de capacidades que el host puede configurar.</span><span class="sxs-lookup"><span data-stu-id="512ad-109">In the .NET Framework version 2.0 and later versions, new layers of abstraction let the host provide many of the resources currently provided by the types in the Win32 assembly, and extend the set of capabilities that the host can configure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="512ad-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="512ad-110">In This Section</span></span>  

 [<span data-ttu-id="512ad-111">IActionOnCLREvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-111">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)  
 <span data-ttu-id="512ad-112">Proporciona un método que realiza una devolución de llamada para un evento registrado.</span><span class="sxs-lookup"><span data-stu-id="512ad-112">Provides a method that performs a callback for a registered event.</span></span>  
  
 [<span data-ttu-id="512ad-113">IApartmentCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-113">IApartmentCallback Interface</span></span>](iapartmentcallback-interface.md)  
 <span data-ttu-id="512ad-114">Proporciona métodos para crear devoluciones de llamada dentro de un contenedor.</span><span class="sxs-lookup"><span data-stu-id="512ad-114">Provides methods for making callbacks within an apartment.</span></span>  
  
 [<span data-ttu-id="512ad-115">IAppDomainBinding (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-115">IAppDomainBinding Interface</span></span>](iappdomainbinding-interface.md)  
 <span data-ttu-id="512ad-116">Proporciona métodos para establecer la configuración de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="512ad-116">Provides methods for setting run-time configuration.</span></span>  
  
 [<span data-ttu-id="512ad-117">ICatalogServices (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-117">ICatalogServices Interface</span></span>](icatalogservices-interface.md)  
 <span data-ttu-id="512ad-118">Proporciona métodos para catalogar servicios.</span><span class="sxs-lookup"><span data-stu-id="512ad-118">Provides methods for cataloging services.</span></span> <span data-ttu-id="512ad-119">(Esta interfaz es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código).</span><span class="sxs-lookup"><span data-stu-id="512ad-119">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="512ad-120">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-120">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)  
 <span data-ttu-id="512ad-121">Proporciona métodos que admiten la comunicación entre el host y el CLR acerca de los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="512ad-121">Provides methods that support communication between the host and the CLR about assemblies.</span></span>  
  
 [<span data-ttu-id="512ad-122">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-122">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)  
 <span data-ttu-id="512ad-123">Administra una lista de ensamblados cargados por el CLR y no por el host.</span><span class="sxs-lookup"><span data-stu-id="512ad-123">Manages a list of assemblies that are loaded by the CLR and not by the host.</span></span>  
  
 [<span data-ttu-id="512ad-124">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-124">ICLRControl Interface</span></span>](iclrcontrol-interface.md)  
 <span data-ttu-id="512ad-125">Proporciona métodos para que el host obtenga acceso y configure varios aspectos de CLR.</span><span class="sxs-lookup"><span data-stu-id="512ad-125">Provides methods for the host to gain access to, and configure various aspects of, the CLR.</span></span>  
  
 [<span data-ttu-id="512ad-126">ICLRDebugManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-126">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)  
 <span data-ttu-id="512ad-127">Proporciona métodos que permiten a un host asociar un conjunto de tareas con un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="512ad-127">Provides methods that enable a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
 [<span data-ttu-id="512ad-128">ICLRErrorReportingManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-128">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)  
 <span data-ttu-id="512ad-129">Proporciona métodos que permiten al host configurar volcados de montón personalizados para el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="512ad-129">Provides methods that enable the host to configure custom heap dumps for error reporting.</span></span>  
  
 [<span data-ttu-id="512ad-130">ICLRGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-130">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)  
 <span data-ttu-id="512ad-131">Proporciona métodos que permiten a un host interactuar con el sistema de recolección de elementos no utilizados de CLR.</span><span class="sxs-lookup"><span data-stu-id="512ad-131">Provides methods that enable a host to interact with the CLR's garbage collection system.</span></span>  
  
 [<span data-ttu-id="512ad-132">ICLRHostBindingPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-132">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)  
 <span data-ttu-id="512ad-133">Proporciona métodos para que el host evalúe y comunique los cambios en la información de la Directiva para los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="512ad-133">Provides methods for the host to evaluate and communicate changes in policy information for assemblies.</span></span>  
  
 [<span data-ttu-id="512ad-134">ICLRHostProtectionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-134">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)  
 <span data-ttu-id="512ad-135">Permite al host bloquear la ejecución de clases, métodos, propiedades y campos administrados específicos en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="512ad-135">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
 [<span data-ttu-id="512ad-136">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)  
 <span data-ttu-id="512ad-137">Implementa un método de devolución de llamada que permite al host notificar a CLR el estado de las solicitudes de e/s especificadas.</span><span class="sxs-lookup"><span data-stu-id="512ad-137">Implements a callback method that enables the host to notify the CLR of the status of specified I/O requests.</span></span>  
  
 [<span data-ttu-id="512ad-138">ICLRMemoryNotificationCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-138">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)  
 <span data-ttu-id="512ad-139">Permite al host notificar las condiciones de presión de memoria mediante un enfoque similar al de la función de Win32 `CreateMemoryResourceNotification` .</span><span class="sxs-lookup"><span data-stu-id="512ad-139">Enables the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
 [<span data-ttu-id="512ad-140">ICLROnEventManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-140">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)  
 <span data-ttu-id="512ad-141">Proporciona métodos que permiten al host registrar y anular el registro de las devoluciones de llamada para los eventos CLR.</span><span class="sxs-lookup"><span data-stu-id="512ad-141">Provides methods that enable the host to register and unregister callbacks for CLR events.</span></span>  
  
 [<span data-ttu-id="512ad-142">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-142">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)  
 <span data-ttu-id="512ad-143">Proporciona métodos que permiten al host especificar las acciones de directiva que deben realizarse en caso de que se produzcan errores y tiempos de espera.</span><span class="sxs-lookup"><span data-stu-id="512ad-143">Provides methods that enable the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
 [<span data-ttu-id="512ad-144">ICLRProbingAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-144">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)  
 <span data-ttu-id="512ad-145">Proporciona métodos que permiten al host obtener las identidades de sondeo de un ensamblado mediante la información de identidad del ensamblado que es interna del CLR, sin necesidad de crear o comprender esa identidad.</span><span class="sxs-lookup"><span data-stu-id="512ad-145">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the CLR, without needing to create or understand that identity.</span></span>  
  
 [<span data-ttu-id="512ad-146">ICLRReferenceAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-146">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)  
 <span data-ttu-id="512ad-147">Proporciona métodos que permiten al host manipular el conjunto de ensamblados a los que hace referencia un archivo o una secuencia mediante datos de identidad de ensamblado internos a CLR, sin necesidad de crear o comprender esas identidades.</span><span class="sxs-lookup"><span data-stu-id="512ad-147">Provides methods that enable the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the CLR, without needing to create or understand those identities.</span></span>  
  
 [<span data-ttu-id="512ad-148">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-148">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)  
 <span data-ttu-id="512ad-149">Proporciona funciones similares a [ICorRuntimeHost](icorruntimehost-interface.md), con un método adicional para establecer la interfaz de control host.</span><span class="sxs-lookup"><span data-stu-id="512ad-149">Provides capabilities similar to [ICorRuntimeHost](icorruntimehost-interface.md), with an additional method to set the host control interface.</span></span>  
  
 [<span data-ttu-id="512ad-150">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-150">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)  
 <span data-ttu-id="512ad-151">Proporciona métodos para que el host obtenga información sobre las tareas solicitadas y para detectar interbloqueos en su implementación de sincronización.</span><span class="sxs-lookup"><span data-stu-id="512ad-151">Provides methods for the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
 [<span data-ttu-id="512ad-152">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-152">ICLRTask Interface</span></span>](iclrtask-interface.md)  
 <span data-ttu-id="512ad-153">Proporciona métodos que permiten al host realizar solicitudes de CLR o proporcionar una notificación al CLR sobre la tarea asociada.</span><span class="sxs-lookup"><span data-stu-id="512ad-153">Provides methods that enable the host to make requests of the CLR, or to provide notification to the CLR about the associated task.</span></span>  
  
 [<span data-ttu-id="512ad-154">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-154">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)  
 <span data-ttu-id="512ad-155">Proporciona métodos que permiten al host solicitar explícitamente que CLR cree una nueva tarea, obtener la tarea que se está ejecutando actualmente y establecer el idioma geográfico y la referencia cultural de la tarea.</span><span class="sxs-lookup"><span data-stu-id="512ad-155">Provides methods that enable the host to request explicitly that the CLR create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
 [<span data-ttu-id="512ad-156">ICLRValidator (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-156">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)  
 <span data-ttu-id="512ad-157">Proporciona métodos para validar imágenes ejecutables portables (PE) y notificar errores de validación.</span><span class="sxs-lookup"><span data-stu-id="512ad-157">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
 [<span data-ttu-id="512ad-158">ICorConfiguration (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-158">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)  
 <span data-ttu-id="512ad-159">Proporciona métodos para configurar CLR.</span><span class="sxs-lookup"><span data-stu-id="512ad-159">Provides methods for configuring the CLR.</span></span>  
  
 [<span data-ttu-id="512ad-160">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-160">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)  
 <span data-ttu-id="512ad-161">Proporciona métodos para tener acceso al grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="512ad-161">Provides methods for accessing the thread pool.</span></span>  
  
 [<span data-ttu-id="512ad-162">IDebuggerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-162">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)  
 <span data-ttu-id="512ad-163">Proporciona métodos para obtener información sobre el estado de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="512ad-163">Provides methods for obtaining information about the state of the debugging services.</span></span>  
  
 [<span data-ttu-id="512ad-164">IDebuggerThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-164">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)  
 <span data-ttu-id="512ad-165">Proporciona métodos para notificar al host el bloqueo y desbloqueo de subprocesos por parte de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="512ad-165">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
 [<span data-ttu-id="512ad-166">IGCHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-166">IGCHost Interface</span></span>](igchost-interface.md)  
 <span data-ttu-id="512ad-167">Proporciona métodos para obtener información sobre el sistema de recolección de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="512ad-167">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
 [<span data-ttu-id="512ad-168">IGCHost2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-168">IGCHost2 Interface</span></span>](igchost2-interface.md)  
 <span data-ttu-id="512ad-169">Proporciona el método [setgcstartuplimitsex (](igchost2-setgcstartuplimitsex-method.md) que permite a un host establecer el tamaño del segmento de recolección de elementos no utilizados y el tamaño máximo de la generación cero del sistema de recolección de elementos no utilizados en valores mayores que `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="512ad-169">Provides the [SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) method that enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation zero to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="512ad-170">IGCHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-170">IGCHostControl Interface</span></span>](igchostcontrol-interface.md)  
 <span data-ttu-id="512ad-171">Proporciona un método que permite al recolector de elementos no utilizados solicitar al host que cambie los límites de la memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="512ad-171">Provides a method that enables the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
 [<span data-ttu-id="512ad-172">IGCThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-172">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)  
 <span data-ttu-id="512ad-173">Proporciona métodos para participar en la programación de subprocesos que de otro modo se bloquearían para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="512ad-173">Provides methods for participating in the scheduling of threads that would otherwise be blocked for garbage collection.</span></span>  
  
 [<span data-ttu-id="512ad-174">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-174">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)  
 <span data-ttu-id="512ad-175">Proporciona métodos que permiten a un host especificar conjuntos de ensamblados que deben ser cargados por CLR o por el host.</span><span class="sxs-lookup"><span data-stu-id="512ad-175">Provides methods that enable a host to specify sets of assemblies that should be loaded by the CLR or by the host.</span></span>  
  
 [<span data-ttu-id="512ad-176">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-176">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)  
 <span data-ttu-id="512ad-177">Proporciona métodos que permiten a un host cargar ensamblados y módulos independientemente de CLR.</span><span class="sxs-lookup"><span data-stu-id="512ad-177">Provides methods that enable a host to load assemblies and modules independently of the CLR.</span></span>  
  
 [<span data-ttu-id="512ad-178">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-178">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)  
 <span data-ttu-id="512ad-179">Proporciona una representación de un evento de restablecimiento automático implementado por el host.</span><span class="sxs-lookup"><span data-stu-id="512ad-179">Provides a representation of an auto-reset event implemented by the host.</span></span>  
  
 [<span data-ttu-id="512ad-180">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-180">IHostControl Interface</span></span>](ihostcontrol-interface.md)  
 <span data-ttu-id="512ad-181">Proporciona métodos para configurar la carga de ensamblados y para determinar qué interfaces de hospedaje admite el host.</span><span class="sxs-lookup"><span data-stu-id="512ad-181">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
 [<span data-ttu-id="512ad-182">IHostCrst (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-182">IHostCrst Interface</span></span>](ihostcrst-interface.md)  
 <span data-ttu-id="512ad-183">Actúa como la representación del host de una sección crítica para el subprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="512ad-183">Serves as the host's representation of a critical section for threading.</span></span>  
  
 [<span data-ttu-id="512ad-184">IHostGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-184">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)  
 <span data-ttu-id="512ad-185">Proporciona métodos que notifican al host de eventos en el mecanismo de recolección de elementos no utilizados implementado por CLR.</span><span class="sxs-lookup"><span data-stu-id="512ad-185">Provides methods that notify the host of events in the garbage collection mechanism implemented by the CLR.</span></span>  
  
 [<span data-ttu-id="512ad-186">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-186">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)  
 <span data-ttu-id="512ad-187">Proporciona métodos que permiten a CLR interactuar con los puertos de finalización de e/s proporcionados por el host.</span><span class="sxs-lookup"><span data-stu-id="512ad-187">Provides methods that enable the CLR to interact with I/O completion ports provided by the host.</span></span>  
  
 [<span data-ttu-id="512ad-188">IHostMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-188">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)  
 <span data-ttu-id="512ad-189">Proporciona métodos para que CLR solicite asignaciones específicas desde el montón a través del host.</span><span class="sxs-lookup"><span data-stu-id="512ad-189">Provides methods for the CLR to request fine-grained allocations from the heap through the host.</span></span>  
  
 [<span data-ttu-id="512ad-190">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-190">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)  
 <span data-ttu-id="512ad-191">Proporciona la implementación del host de una representación de un evento de restablecimiento manual.</span><span class="sxs-lookup"><span data-stu-id="512ad-191">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
 [<span data-ttu-id="512ad-192">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-192">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)  
 <span data-ttu-id="512ad-193">Proporciona métodos para que CLR realice solicitudes de memoria virtual a través del host, en lugar de usar las funciones estándar de memoria virtual de Win32.</span><span class="sxs-lookup"><span data-stu-id="512ad-193">Provides methods for the CLR to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
 [<span data-ttu-id="512ad-194">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-194">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)  
 <span data-ttu-id="512ad-195">Proporciona métodos que notifican al host las acciones que CLR realiza en caso de anulaciones, tiempos de espera o errores.</span><span class="sxs-lookup"><span data-stu-id="512ad-195">Provides methods that notify the host of the actions the CLR performs in case of aborts, timeouts, or failures.</span></span>  
  
 [<span data-ttu-id="512ad-196">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-196">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)  
 <span data-ttu-id="512ad-197">Permite que CLR mantenga la información de contexto de seguridad implementada por el host.</span><span class="sxs-lookup"><span data-stu-id="512ad-197">Enables the CLR to maintain security context information implemented by the host.</span></span>  
  
 [<span data-ttu-id="512ad-198">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-198">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)  
 <span data-ttu-id="512ad-199">Proporciona métodos que permiten el acceso y el control sobre el contexto de seguridad del subproceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="512ad-199">Provides methods that enable access to, and control over, the security context of the currently executing thread.</span></span>  
  
 [<span data-ttu-id="512ad-200">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-200">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)  
 <span data-ttu-id="512ad-201">Proporciona una representación de un semáforo implementado por el host.</span><span class="sxs-lookup"><span data-stu-id="512ad-201">Provides a representation of a semaphore implemented by the host.</span></span>  
  
 [<span data-ttu-id="512ad-202">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-202">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)  
 <span data-ttu-id="512ad-203">Proporciona métodos para que CLR cree primitivas de sincronización llamando al host, en lugar de usar las funciones de sincronización de Win32.</span><span class="sxs-lookup"><span data-stu-id="512ad-203">Provides methods for the CLR to create synchronization primitives by calling the host, instead of using the Win32 synchronization functions.</span></span>  
  
 [<span data-ttu-id="512ad-204">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-204">IHostTask Interface</span></span>](ihosttask-interface.md)  
 <span data-ttu-id="512ad-205">Proporciona métodos que permiten a CLR comunicarse con el host para administrar tareas.</span><span class="sxs-lookup"><span data-stu-id="512ad-205">Provides methods that enable the CLR to communicate with the host to manage tasks.</span></span>  
  
 [<span data-ttu-id="512ad-206">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-206">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)  
 <span data-ttu-id="512ad-207">Proporciona métodos que permiten a CLR trabajar con tareas a través del host en lugar de usar las funciones de fibra o de subprocesos estándar del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="512ad-207">Provides methods that enable the CLR to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
 [<span data-ttu-id="512ad-208">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-208">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)  
 <span data-ttu-id="512ad-209">Proporciona métodos para que CLR configure el grupo de subprocesos y pone en cola los elementos de trabajo en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="512ad-209">Provides methods for the CLR to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
 [<span data-ttu-id="512ad-210">IManagedObject (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-210">IManagedObject Interface</span></span>](imanagedobject-interface.md)  
 <span data-ttu-id="512ad-211">Proporciona métodos para controlar un objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="512ad-211">Provides methods for controlling a managed object.</span></span>  
  
 <span data-ttu-id="512ad-212">IObjectHandle (</span><span class="sxs-lookup"><span data-stu-id="512ad-212">"IObjectHandle"</span></span>  
 <span data-ttu-id="512ad-213">Proporciona un método para desempaquetar objetos de cálculo de referencias por valor desde el direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="512ad-213">Provides a method for unwrapping marshal-by-value objects from indirection.</span></span>  
  
 [<span data-ttu-id="512ad-214">ITypeName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-214">ITypeName Interface</span></span>](itypename-interface.md)  
 <span data-ttu-id="512ad-215">Proporciona métodos para obtener información sobre el nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="512ad-215">Provides methods for obtaining type name information.</span></span> <span data-ttu-id="512ad-216">(Esta interfaz es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código).</span><span class="sxs-lookup"><span data-stu-id="512ad-216">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="512ad-217">ITypeNameBuilder (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-217">ITypeNameBuilder Interface</span></span>](itypenamebuilder-interface.md)  
 <span data-ttu-id="512ad-218">Proporciona métodos para generar un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="512ad-218">Provides methods for building a type name.</span></span> <span data-ttu-id="512ad-219">(Esta interfaz es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código).</span><span class="sxs-lookup"><span data-stu-id="512ad-219">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="512ad-220">ITypeNameFactory (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="512ad-220">ITypeNameFactory Interface</span></span>](itypenamefactory-interface.md)  
 <span data-ttu-id="512ad-221">Proporciona métodos para deconstruir un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="512ad-221">Provides methods for deconstructing a type name.</span></span> <span data-ttu-id="512ad-222">(Esta interfaz es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código).</span><span class="sxs-lookup"><span data-stu-id="512ad-222">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 <span data-ttu-id="512ad-223">IValidator</span><span class="sxs-lookup"><span data-stu-id="512ad-223">"IValidator"</span></span>  
 <span data-ttu-id="512ad-224">Proporciona métodos para validar imágenes ejecutables portables (PE) y notificar errores de validación.</span><span class="sxs-lookup"><span data-stu-id="512ad-224">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="512ad-225">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="512ad-225">Related Sections</span></span>  

 [<span data-ttu-id="512ad-226">Coclases e interfaces de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="512ad-226">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="512ad-227">Contiene temas que describen las interfaces de hospedaje proporcionadas en la .NET Framework versión 1,0 y 1,1.</span><span class="sxs-lookup"><span data-stu-id="512ad-227">Contains topics that describe the hosting interfaces provided in the .NET Framework version 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="512ad-228">Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5</span><span class="sxs-lookup"><span data-stu-id="512ad-228">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="512ad-229">Contiene temas que describen las interfaces de hospedaje proporcionadas en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="512ad-229">Contains topics that describe the hosting interfaces provided in the .NET Framework 4.</span></span>
