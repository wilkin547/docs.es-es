---
title: Interfaces de hospedaje de CLR
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
ms.openlocfilehash: 77f2ba64d9bdbe9793d56e88dae46fd506119ab8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719052"
---
# <a name="clr-hosting-interfaces"></a><span data-ttu-id="20ecb-102">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="20ecb-102">CLR Hosting Interfaces</span></span>

<span data-ttu-id="20ecb-103">En esta sección se describen las interfaces que los hosts no administrados pueden utilizar para integrar el Common Language Runtime (CLR) en sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="20ecb-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span> <span data-ttu-id="20ecb-104">La información pertenece a la .NET Framework versión 2,0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="20ecb-104">The information pertains to the .NET Framework version 2.0 and later versions.</span></span> <span data-ttu-id="20ecb-105">Estas interfaces permiten al host controlar muchos más aspectos del tiempo de ejecución que los que era posible en las versiones 1,0 y 1,1, y proporcionan una mayor integración entre CLR y el modelo de ejecución del host.</span><span class="sxs-lookup"><span data-stu-id="20ecb-105">These interfaces enable the host to control many more aspects of the runtime than was possible in versions 1.0 and 1.1, and provide much tighter integration between the CLR and the host's execution model.</span></span>  
  
 <span data-ttu-id="20ecb-106">En la .NET Framework versión 1,0 y 1,1, el modelo de hospedaje habilitaba un host no administrado para cargar CLR en un proceso, para configurar determinadas opciones y para recibir notificaciones de eventos.</span><span class="sxs-lookup"><span data-stu-id="20ecb-106">In the .NET Framework version 1.0 and 1.1, the hosting model enabled an unmanaged host to load the CLR into a process, to configure certain settings, and to receive event notifications.</span></span> <span data-ttu-id="20ecb-107">Sin embargo, en general, el host y el CLR se ejecutaban de forma independiente en ese proceso.</span><span class="sxs-lookup"><span data-stu-id="20ecb-107">However, in general, the host and the CLR ran independently in that process.</span></span> <span data-ttu-id="20ecb-108">En la .NET Framework versión 2,0 y versiones posteriores, las nuevas capas de abstracción permiten que el host proporcione muchos de los recursos que proporcionan actualmente los tipos del ensamblado Win32 y que amplían el conjunto de capacidades que el host puede configurar.</span><span class="sxs-lookup"><span data-stu-id="20ecb-108">In the .NET Framework version 2.0 and later versions, new layers of abstraction let the host provide many of the resources currently provided by the types in the Win32 assembly, and extend the set of capabilities that the host can configure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20ecb-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="20ecb-109">In This Section</span></span>  

 [<span data-ttu-id="20ecb-110">IActionOnCLREvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-110">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)  
 <span data-ttu-id="20ecb-111">Proporciona un método que realiza una devolución de llamada para un evento registrado.</span><span class="sxs-lookup"><span data-stu-id="20ecb-111">Provides a method that performs a callback for a registered event.</span></span>  
  
 [<span data-ttu-id="20ecb-112">IApartmentCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-112">IApartmentCallback Interface</span></span>](iapartmentcallback-interface.md)  
 <span data-ttu-id="20ecb-113">Proporciona métodos para crear devoluciones de llamada dentro de un contenedor.</span><span class="sxs-lookup"><span data-stu-id="20ecb-113">Provides methods for making callbacks within an apartment.</span></span>  
  
 [<span data-ttu-id="20ecb-114">IAppDomainBinding (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-114">IAppDomainBinding Interface</span></span>](iappdomainbinding-interface.md)  
 <span data-ttu-id="20ecb-115">Proporciona métodos para establecer la configuración de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="20ecb-115">Provides methods for setting run-time configuration.</span></span>  
  
 [<span data-ttu-id="20ecb-116">ICatalogServices (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-116">ICatalogServices Interface</span></span>](icatalogservices-interface.md)  
 <span data-ttu-id="20ecb-117">Proporciona métodos para catalogar servicios.</span><span class="sxs-lookup"><span data-stu-id="20ecb-117">Provides methods for cataloging services.</span></span> <span data-ttu-id="20ecb-118">(Esta interfaz es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código).</span><span class="sxs-lookup"><span data-stu-id="20ecb-118">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="20ecb-119">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-119">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)  
 <span data-ttu-id="20ecb-120">Proporciona métodos que admiten la comunicación entre el host y el CLR acerca de los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="20ecb-120">Provides methods that support communication between the host and the CLR about assemblies.</span></span>  
  
 [<span data-ttu-id="20ecb-121">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-121">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)  
 <span data-ttu-id="20ecb-122">Administra una lista de ensamblados cargados por el CLR y no por el host.</span><span class="sxs-lookup"><span data-stu-id="20ecb-122">Manages a list of assemblies that are loaded by the CLR and not by the host.</span></span>  
  
 [<span data-ttu-id="20ecb-123">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-123">ICLRControl Interface</span></span>](iclrcontrol-interface.md)  
 <span data-ttu-id="20ecb-124">Proporciona métodos para que el host obtenga acceso y configure varios aspectos de CLR.</span><span class="sxs-lookup"><span data-stu-id="20ecb-124">Provides methods for the host to gain access to, and configure various aspects of, the CLR.</span></span>  
  
 [<span data-ttu-id="20ecb-125">ICLRDebugManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-125">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)  
 <span data-ttu-id="20ecb-126">Proporciona métodos que permiten a un host asociar un conjunto de tareas con un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="20ecb-126">Provides methods that enable a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
 [<span data-ttu-id="20ecb-127">ICLRErrorReportingManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-127">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)  
 <span data-ttu-id="20ecb-128">Proporciona métodos que permiten al host configurar volcados de montón personalizados para el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="20ecb-128">Provides methods that enable the host to configure custom heap dumps for error reporting.</span></span>  
  
 [<span data-ttu-id="20ecb-129">ICLRGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-129">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)  
 <span data-ttu-id="20ecb-130">Proporciona métodos que permiten a un host interactuar con el sistema de recolección de elementos no utilizados de CLR.</span><span class="sxs-lookup"><span data-stu-id="20ecb-130">Provides methods that enable a host to interact with the CLR's garbage collection system.</span></span>  
  
 [<span data-ttu-id="20ecb-131">ICLRHostBindingPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-131">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)  
 <span data-ttu-id="20ecb-132">Proporciona métodos para que el host evalúe y comunique los cambios en la información de la Directiva para los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="20ecb-132">Provides methods for the host to evaluate and communicate changes in policy information for assemblies.</span></span>  
  
 [<span data-ttu-id="20ecb-133">ICLRHostProtectionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-133">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)  
 <span data-ttu-id="20ecb-134">Permite al host bloquear la ejecución de clases, métodos, propiedades y campos administrados específicos en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="20ecb-134">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
 [<span data-ttu-id="20ecb-135">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-135">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)  
 <span data-ttu-id="20ecb-136">Implementa un método de devolución de llamada que permite al host notificar a CLR el estado de las solicitudes de e/s especificadas.</span><span class="sxs-lookup"><span data-stu-id="20ecb-136">Implements a callback method that enables the host to notify the CLR of the status of specified I/O requests.</span></span>  
  
 [<span data-ttu-id="20ecb-137">ICLRMemoryNotificationCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-137">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)  
 <span data-ttu-id="20ecb-138">Permite al host notificar las condiciones de presión de memoria mediante un enfoque similar al de la función de Win32 `CreateMemoryResourceNotification` .</span><span class="sxs-lookup"><span data-stu-id="20ecb-138">Enables the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
 [<span data-ttu-id="20ecb-139">ICLROnEventManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-139">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)  
 <span data-ttu-id="20ecb-140">Proporciona métodos que permiten al host registrar y anular el registro de las devoluciones de llamada para los eventos CLR.</span><span class="sxs-lookup"><span data-stu-id="20ecb-140">Provides methods that enable the host to register and unregister callbacks for CLR events.</span></span>  
  
 [<span data-ttu-id="20ecb-141">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-141">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)  
 <span data-ttu-id="20ecb-142">Proporciona métodos que permiten al host especificar las acciones de directiva que deben realizarse en caso de que se produzcan errores y tiempos de espera.</span><span class="sxs-lookup"><span data-stu-id="20ecb-142">Provides methods that enable the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
 [<span data-ttu-id="20ecb-143">ICLRProbingAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-143">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)  
 <span data-ttu-id="20ecb-144">Proporciona métodos que permiten al host obtener las identidades de sondeo de un ensamblado mediante la información de identidad del ensamblado que es interna del CLR, sin necesidad de crear o comprender esa identidad.</span><span class="sxs-lookup"><span data-stu-id="20ecb-144">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the CLR, without needing to create or understand that identity.</span></span>  
  
 [<span data-ttu-id="20ecb-145">ICLRReferenceAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-145">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)  
 <span data-ttu-id="20ecb-146">Proporciona métodos que permiten al host manipular el conjunto de ensamblados a los que hace referencia un archivo o una secuencia mediante datos de identidad de ensamblado internos a CLR, sin necesidad de crear o comprender esas identidades.</span><span class="sxs-lookup"><span data-stu-id="20ecb-146">Provides methods that enable the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the CLR, without needing to create or understand those identities.</span></span>  
  
 [<span data-ttu-id="20ecb-147">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-147">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)  
 <span data-ttu-id="20ecb-148">Proporciona funciones similares a [ICorRuntimeHost](icorruntimehost-interface.md), con un método adicional para establecer la interfaz de control host.</span><span class="sxs-lookup"><span data-stu-id="20ecb-148">Provides capabilities similar to [ICorRuntimeHost](icorruntimehost-interface.md), with an additional method to set the host control interface.</span></span>  
  
 [<span data-ttu-id="20ecb-149">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-149">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)  
 <span data-ttu-id="20ecb-150">Proporciona métodos para que el host obtenga información sobre las tareas solicitadas y para detectar interbloqueos en su implementación de sincronización.</span><span class="sxs-lookup"><span data-stu-id="20ecb-150">Provides methods for the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
 [<span data-ttu-id="20ecb-151">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-151">ICLRTask Interface</span></span>](iclrtask-interface.md)  
 <span data-ttu-id="20ecb-152">Proporciona métodos que permiten al host realizar solicitudes de CLR o proporcionar una notificación al CLR sobre la tarea asociada.</span><span class="sxs-lookup"><span data-stu-id="20ecb-152">Provides methods that enable the host to make requests of the CLR, or to provide notification to the CLR about the associated task.</span></span>  
  
 [<span data-ttu-id="20ecb-153">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-153">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)  
 <span data-ttu-id="20ecb-154">Proporciona métodos que permiten al host solicitar explícitamente que CLR cree una nueva tarea, obtener la tarea que se está ejecutando actualmente y establecer el idioma geográfico y la referencia cultural de la tarea.</span><span class="sxs-lookup"><span data-stu-id="20ecb-154">Provides methods that enable the host to request explicitly that the CLR create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
 [<span data-ttu-id="20ecb-155">ICLRValidator (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-155">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)  
 <span data-ttu-id="20ecb-156">Proporciona métodos para validar imágenes ejecutables portables (PE) y notificar errores de validación.</span><span class="sxs-lookup"><span data-stu-id="20ecb-156">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
 [<span data-ttu-id="20ecb-157">ICorConfiguration (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-157">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)  
 <span data-ttu-id="20ecb-158">Proporciona métodos para configurar CLR.</span><span class="sxs-lookup"><span data-stu-id="20ecb-158">Provides methods for configuring the CLR.</span></span>  
  
 [<span data-ttu-id="20ecb-159">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-159">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)  
 <span data-ttu-id="20ecb-160">Proporciona métodos para tener acceso al grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="20ecb-160">Provides methods for accessing the thread pool.</span></span>  
  
 [<span data-ttu-id="20ecb-161">IDebuggerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-161">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)  
 <span data-ttu-id="20ecb-162">Proporciona métodos para obtener información sobre el estado de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="20ecb-162">Provides methods for obtaining information about the state of the debugging services.</span></span>  
  
 [<span data-ttu-id="20ecb-163">IDebuggerThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-163">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)  
 <span data-ttu-id="20ecb-164">Proporciona métodos para notificar al host el bloqueo y desbloqueo de subprocesos por parte de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="20ecb-164">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
 [<span data-ttu-id="20ecb-165">IGCHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-165">IGCHost Interface</span></span>](igchost-interface.md)  
 <span data-ttu-id="20ecb-166">Proporciona métodos para obtener información sobre el sistema de recolección de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="20ecb-166">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
 [<span data-ttu-id="20ecb-167">IGCHost2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-167">IGCHost2 Interface</span></span>](igchost2-interface.md)  
 <span data-ttu-id="20ecb-168">Proporciona el método [setgcstartuplimitsex (](igchost2-setgcstartuplimitsex-method.md) que permite a un host establecer el tamaño del segmento de recolección de elementos no utilizados y el tamaño máximo de la generación cero del sistema de recolección de elementos no utilizados en valores mayores que `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="20ecb-168">Provides the [SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) method that enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation zero to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="20ecb-169">IGCHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-169">IGCHostControl Interface</span></span>](igchostcontrol-interface.md)  
 <span data-ttu-id="20ecb-170">Proporciona un método que permite al recolector de elementos no utilizados solicitar al host que cambie los límites de la memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="20ecb-170">Provides a method that enables the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
 [<span data-ttu-id="20ecb-171">IGCThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-171">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)  
 <span data-ttu-id="20ecb-172">Proporciona métodos para participar en la programación de subprocesos que de otro modo se bloquearían para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="20ecb-172">Provides methods for participating in the scheduling of threads that would otherwise be blocked for garbage collection.</span></span>  
  
 [<span data-ttu-id="20ecb-173">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-173">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)  
 <span data-ttu-id="20ecb-174">Proporciona métodos que permiten a un host especificar conjuntos de ensamblados que deben ser cargados por CLR o por el host.</span><span class="sxs-lookup"><span data-stu-id="20ecb-174">Provides methods that enable a host to specify sets of assemblies that should be loaded by the CLR or by the host.</span></span>  
  
 [<span data-ttu-id="20ecb-175">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-175">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)  
 <span data-ttu-id="20ecb-176">Proporciona métodos que permiten a un host cargar ensamblados y módulos independientemente de CLR.</span><span class="sxs-lookup"><span data-stu-id="20ecb-176">Provides methods that enable a host to load assemblies and modules independently of the CLR.</span></span>  
  
 [<span data-ttu-id="20ecb-177">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-177">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)  
 <span data-ttu-id="20ecb-178">Proporciona una representación de un evento de restablecimiento automático implementado por el host.</span><span class="sxs-lookup"><span data-stu-id="20ecb-178">Provides a representation of an auto-reset event implemented by the host.</span></span>  
  
 [<span data-ttu-id="20ecb-179">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-179">IHostControl Interface</span></span>](ihostcontrol-interface.md)  
 <span data-ttu-id="20ecb-180">Proporciona métodos para configurar la carga de ensamblados y para determinar qué interfaces de hospedaje admite el host.</span><span class="sxs-lookup"><span data-stu-id="20ecb-180">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
 [<span data-ttu-id="20ecb-181">IHostCrst (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-181">IHostCrst Interface</span></span>](ihostcrst-interface.md)  
 <span data-ttu-id="20ecb-182">Actúa como la representación del host de una sección crítica para el subprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="20ecb-182">Serves as the host's representation of a critical section for threading.</span></span>  
  
 [<span data-ttu-id="20ecb-183">IHostGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-183">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)  
 <span data-ttu-id="20ecb-184">Proporciona métodos que notifican al host de eventos en el mecanismo de recolección de elementos no utilizados implementado por CLR.</span><span class="sxs-lookup"><span data-stu-id="20ecb-184">Provides methods that notify the host of events in the garbage collection mechanism implemented by the CLR.</span></span>  
  
 [<span data-ttu-id="20ecb-185">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-185">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)  
 <span data-ttu-id="20ecb-186">Proporciona métodos que permiten a CLR interactuar con los puertos de finalización de e/s proporcionados por el host.</span><span class="sxs-lookup"><span data-stu-id="20ecb-186">Provides methods that enable the CLR to interact with I/O completion ports provided by the host.</span></span>  
  
 [<span data-ttu-id="20ecb-187">IHostMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-187">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)  
 <span data-ttu-id="20ecb-188">Proporciona métodos para que CLR solicite asignaciones específicas desde el montón a través del host.</span><span class="sxs-lookup"><span data-stu-id="20ecb-188">Provides methods for the CLR to request fine-grained allocations from the heap through the host.</span></span>  
  
 [<span data-ttu-id="20ecb-189">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-189">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)  
 <span data-ttu-id="20ecb-190">Proporciona la implementación del host de una representación de un evento de restablecimiento manual.</span><span class="sxs-lookup"><span data-stu-id="20ecb-190">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
 [<span data-ttu-id="20ecb-191">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-191">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)  
 <span data-ttu-id="20ecb-192">Proporciona métodos para que CLR realice solicitudes de memoria virtual a través del host, en lugar de usar las funciones estándar de memoria virtual de Win32.</span><span class="sxs-lookup"><span data-stu-id="20ecb-192">Provides methods for the CLR to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
 [<span data-ttu-id="20ecb-193">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-193">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)  
 <span data-ttu-id="20ecb-194">Proporciona métodos que notifican al host las acciones que CLR realiza en caso de anulaciones, tiempos de espera o errores.</span><span class="sxs-lookup"><span data-stu-id="20ecb-194">Provides methods that notify the host of the actions the CLR performs in case of aborts, timeouts, or failures.</span></span>  
  
 [<span data-ttu-id="20ecb-195">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-195">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)  
 <span data-ttu-id="20ecb-196">Permite que CLR mantenga la información de contexto de seguridad implementada por el host.</span><span class="sxs-lookup"><span data-stu-id="20ecb-196">Enables the CLR to maintain security context information implemented by the host.</span></span>  
  
 [<span data-ttu-id="20ecb-197">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-197">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)  
 <span data-ttu-id="20ecb-198">Proporciona métodos que permiten el acceso y el control sobre el contexto de seguridad del subproceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="20ecb-198">Provides methods that enable access to, and control over, the security context of the currently executing thread.</span></span>  
  
 [<span data-ttu-id="20ecb-199">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-199">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)  
 <span data-ttu-id="20ecb-200">Proporciona una representación de un semáforo implementado por el host.</span><span class="sxs-lookup"><span data-stu-id="20ecb-200">Provides a representation of a semaphore implemented by the host.</span></span>  
  
 [<span data-ttu-id="20ecb-201">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-201">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)  
 <span data-ttu-id="20ecb-202">Proporciona métodos para que CLR cree primitivas de sincronización llamando al host, en lugar de usar las funciones de sincronización de Win32.</span><span class="sxs-lookup"><span data-stu-id="20ecb-202">Provides methods for the CLR to create synchronization primitives by calling the host, instead of using the Win32 synchronization functions.</span></span>  
  
 [<span data-ttu-id="20ecb-203">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-203">IHostTask Interface</span></span>](ihosttask-interface.md)  
 <span data-ttu-id="20ecb-204">Proporciona métodos que permiten a CLR comunicarse con el host para administrar tareas.</span><span class="sxs-lookup"><span data-stu-id="20ecb-204">Provides methods that enable the CLR to communicate with the host to manage tasks.</span></span>  
  
 [<span data-ttu-id="20ecb-205">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-205">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)  
 <span data-ttu-id="20ecb-206">Proporciona métodos que permiten a CLR trabajar con tareas a través del host en lugar de usar las funciones de fibra o de subprocesos estándar del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="20ecb-206">Provides methods that enable the CLR to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
 [<span data-ttu-id="20ecb-207">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-207">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)  
 <span data-ttu-id="20ecb-208">Proporciona métodos para que CLR configure el grupo de subprocesos y pone en cola los elementos de trabajo en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="20ecb-208">Provides methods for the CLR to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
 [<span data-ttu-id="20ecb-209">IManagedObject (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-209">IManagedObject Interface</span></span>](imanagedobject-interface.md)  
 <span data-ttu-id="20ecb-210">Proporciona métodos para controlar un objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="20ecb-210">Provides methods for controlling a managed object.</span></span>  
  
 <span data-ttu-id="20ecb-211">IObjectHandle (</span><span class="sxs-lookup"><span data-stu-id="20ecb-211">"IObjectHandle"</span></span>  
 <span data-ttu-id="20ecb-212">Proporciona un método para desempaquetar objetos de cálculo de referencias por valor desde el direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="20ecb-212">Provides a method for unwrapping marshal-by-value objects from indirection.</span></span>  
  
 [<span data-ttu-id="20ecb-213">ITypeName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-213">ITypeName Interface</span></span>](itypename-interface.md)  
 <span data-ttu-id="20ecb-214">Proporciona métodos para obtener información sobre el nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="20ecb-214">Provides methods for obtaining type name information.</span></span> <span data-ttu-id="20ecb-215">(Esta interfaz es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código).</span><span class="sxs-lookup"><span data-stu-id="20ecb-215">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="20ecb-216">ITypeNameBuilder (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-216">ITypeNameBuilder Interface</span></span>](itypenamebuilder-interface.md)  
 <span data-ttu-id="20ecb-217">Proporciona métodos para generar un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="20ecb-217">Provides methods for building a type name.</span></span> <span data-ttu-id="20ecb-218">(Esta interfaz es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código).</span><span class="sxs-lookup"><span data-stu-id="20ecb-218">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="20ecb-219">ITypeNameFactory (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20ecb-219">ITypeNameFactory Interface</span></span>](itypenamefactory-interface.md)  
 <span data-ttu-id="20ecb-220">Proporciona métodos para deconstruir un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="20ecb-220">Provides methods for deconstructing a type name.</span></span> <span data-ttu-id="20ecb-221">(Esta interfaz es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código).</span><span class="sxs-lookup"><span data-stu-id="20ecb-221">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 <span data-ttu-id="20ecb-222">IValidator</span><span class="sxs-lookup"><span data-stu-id="20ecb-222">"IValidator"</span></span>  
 <span data-ttu-id="20ecb-223">Proporciona métodos para validar imágenes ejecutables portables (PE) y notificar errores de validación.</span><span class="sxs-lookup"><span data-stu-id="20ecb-223">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="20ecb-224">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="20ecb-224">Related Sections</span></span>  

 [<span data-ttu-id="20ecb-225">Coclases e interfaces de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="20ecb-225">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="20ecb-226">Contiene temas que describen las interfaces de hospedaje proporcionadas en la .NET Framework versión 1,0 y 1,1.</span><span class="sxs-lookup"><span data-stu-id="20ecb-226">Contains topics that describe the hosting interfaces provided in the .NET Framework version 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="20ecb-227">Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5</span><span class="sxs-lookup"><span data-stu-id="20ecb-227">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="20ecb-228">Contiene temas que describen las interfaces de hospedaje proporcionadas en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="20ecb-228">Contains topics that describe the hosting interfaces provided in the .NET Framework 4.</span></span>
