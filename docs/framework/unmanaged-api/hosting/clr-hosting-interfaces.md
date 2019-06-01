---
title: Interfaces de hospedaje de CLR
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80404e65263aa4ad245a8c8213630a4736bd7b11
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456876"
---
# <a name="clr-hosting-interfaces"></a><span data-ttu-id="ad100-102">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="ad100-102">CLR Hosting Interfaces</span></span>
<span data-ttu-id="ad100-103">Esta sección describen las interfaces que no administrada de hosts pueden usar para integrar common language runtime (CLR) en sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ad100-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span> <span data-ttu-id="ad100-104">Los datos pertenecen a la versión de .NET Framework 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="ad100-104">The information pertains to the .NET Framework version 2.0 and later versions.</span></span> <span data-ttu-id="ad100-105">Estas interfaces permiten al host controlar muchos más aspectos del tiempo de ejecución que era posible en las versiones 1.0 y 1.1 y proporcionan mucho una mayor integración entre CLR y el modelo de ejecución del host.</span><span class="sxs-lookup"><span data-stu-id="ad100-105">These interfaces enable the host to control many more aspects of the runtime than was possible in versions 1.0 and 1.1, and provide much tighter integration between the CLR and the host's execution model.</span></span>  
  
 <span data-ttu-id="ad100-106">En la versión 1.0 y 1.1 de .NET Framework, el modelo de hospedaje habilitado un host no administrado cargar CLR en un proceso, para configurar ciertas opciones de configuración y para recibir notificaciones de eventos.</span><span class="sxs-lookup"><span data-stu-id="ad100-106">In the .NET Framework version 1.0 and 1.1, the hosting model enabled an unmanaged host to load the CLR into a process, to configure certain settings, and to receive event notifications.</span></span> <span data-ttu-id="ad100-107">Sin embargo, en general, el host y el CLR se ejecutaban por separado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ad100-107">However, in general, the host and the CLR ran independently in that process.</span></span> <span data-ttu-id="ad100-108">En la versión de .NET Framework 2.0 y versiones posteriores, nuevas capas de abstracción permiten al host proporcionar muchos de los recursos proporcionados actualmente por los tipos del ensamblado de Win32 y ampliar el conjunto de funciones que puede configurar el host.</span><span class="sxs-lookup"><span data-stu-id="ad100-108">In the .NET Framework version 2.0 and later versions, new layers of abstraction let the host provide many of the resources currently provided by the types in the Win32 assembly, and extend the set of capabilities that the host can configure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ad100-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ad100-109">In This Section</span></span>  
 [<span data-ttu-id="ad100-110">IActionOnCLREvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-110">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 <span data-ttu-id="ad100-111">Proporciona un método que realiza una devolución de llamada para un evento registrado.</span><span class="sxs-lookup"><span data-stu-id="ad100-111">Provides a method that performs a callback for a registered event.</span></span>  
  
 [<span data-ttu-id="ad100-112">IApartmentCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-112">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 <span data-ttu-id="ad100-113">Proporciona métodos para hacer que las devoluciones de llamada dentro de un apartamento.</span><span class="sxs-lookup"><span data-stu-id="ad100-113">Provides methods for making callbacks within an apartment.</span></span>  
  
 [<span data-ttu-id="ad100-114">IAppDomainBinding (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-114">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 <span data-ttu-id="ad100-115">Proporciona métodos para establecer la configuración de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ad100-115">Provides methods for setting run-time configuration.</span></span>  
  
 [<span data-ttu-id="ad100-116">ICatalogServices (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-116">ICatalogServices Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 <span data-ttu-id="ad100-117">Proporciona métodos para servicios de catálogo.</span><span class="sxs-lookup"><span data-stu-id="ad100-117">Provides methods for cataloging services.</span></span> <span data-ttu-id="ad100-118">(Esta interfaz admite la infraestructura de .NET Framework y no está pensada para utilizarse directamente desde el código).</span><span class="sxs-lookup"><span data-stu-id="ad100-118">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="ad100-119">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 <span data-ttu-id="ad100-120">Proporciona métodos que admiten la comunicación entre el host y el CLR acerca de los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ad100-120">Provides methods that support communication between the host and the CLR about assemblies.</span></span>  
  
 [<span data-ttu-id="ad100-121">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 <span data-ttu-id="ad100-122">Administra una lista de los ensamblados cargados por CLR y no por el host.</span><span class="sxs-lookup"><span data-stu-id="ad100-122">Manages a list of assemblies that are loaded by the CLR and not by the host.</span></span>  
  
 [<span data-ttu-id="ad100-123">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-123">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 <span data-ttu-id="ad100-124">Proporciona métodos para el host tener acceso a y configurar varios aspectos de CLR.</span><span class="sxs-lookup"><span data-stu-id="ad100-124">Provides methods for the host to gain access to, and configure various aspects of, the CLR.</span></span>  
  
 [<span data-ttu-id="ad100-125">ICLRDebugManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 <span data-ttu-id="ad100-126">Proporciona métodos que permiten a un host asociar un conjunto de tareas con un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="ad100-126">Provides methods that enable a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
 [<span data-ttu-id="ad100-127">ICLRErrorReportingManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-127">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 <span data-ttu-id="ad100-128">Proporciona métodos que permiten al host configurar los volcados de montón personalizado para el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="ad100-128">Provides methods that enable the host to configure custom heap dumps for error reporting.</span></span>  
  
 [<span data-ttu-id="ad100-129">ICLRGCManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-129">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 <span data-ttu-id="ad100-130">Proporciona métodos que permiten a un host interactuar con el sistema de recopilación de elementos no utilizados de CLR.</span><span class="sxs-lookup"><span data-stu-id="ad100-130">Provides methods that enable a host to interact with the CLR's garbage collection system.</span></span>  
  
 [<span data-ttu-id="ad100-131">ICLRHostBindingPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-131">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 <span data-ttu-id="ad100-132">Proporciona métodos para el host evaluar y comunicar los cambios en la información de la directiva para los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ad100-132">Provides methods for the host to evaluate and communicate changes in policy information for assemblies.</span></span>  
  
 [<span data-ttu-id="ad100-133">ICLRHostProtectionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-133">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 <span data-ttu-id="ad100-134">Permite que el host bloquear clases administradas específicas, métodos, propiedades y campos se ejecuten en el código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="ad100-134">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
 [<span data-ttu-id="ad100-135">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-135">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 <span data-ttu-id="ad100-136">Implementa un método de devolución de llamada que permite al host informar a CLR del estado de las solicitudes de E/S especificados.</span><span class="sxs-lookup"><span data-stu-id="ad100-136">Implements a callback method that enables the host to notify the CLR of the status of specified I/O requests.</span></span>  
  
 [<span data-ttu-id="ad100-137">ICLRMemoryNotificationCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 <span data-ttu-id="ad100-138">Permite que el host a comunicar condiciones de presión de memoria mediante un enfoque similar de Win32 `CreateMemoryResourceNotification` función.</span><span class="sxs-lookup"><span data-stu-id="ad100-138">Enables the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
 [<span data-ttu-id="ad100-139">ICLROnEventManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-139">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 <span data-ttu-id="ad100-140">Proporciona métodos que permiten al host registrar y anular el registro de devoluciones de llamada para eventos de CLR.</span><span class="sxs-lookup"><span data-stu-id="ad100-140">Provides methods that enable the host to register and unregister callbacks for CLR events.</span></span>  
  
 [<span data-ttu-id="ad100-141">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 <span data-ttu-id="ad100-142">Proporciona métodos que permiten al host especificar acciones de directiva que se realizarán en el caso de errores y tiempos de espera.</span><span class="sxs-lookup"><span data-stu-id="ad100-142">Provides methods that enable the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
 [<span data-ttu-id="ad100-143">ICLRProbingAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 <span data-ttu-id="ad100-144">Proporciona métodos que permiten al host obtener las identidades de sondeo de un ensamblado mediante el uso de información de identidad del ensamblado que es interna de CLR, sin necesidad de crear o reconocer dicha identidad.</span><span class="sxs-lookup"><span data-stu-id="ad100-144">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the CLR, without needing to create or understand that identity.</span></span>  
  
 [<span data-ttu-id="ad100-145">ICLRReferenceAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-145">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 <span data-ttu-id="ad100-146">Proporciona métodos que permiten al host manipular el conjunto de ensamblados que se hace referencia a un archivo o secuencia utilizando los datos de identidad de ensamblado que están internas de CLR, sin necesidad de crear o entender esas identidades.</span><span class="sxs-lookup"><span data-stu-id="ad100-146">Provides methods that enable the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the CLR, without needing to create or understand those identities.</span></span>  
  
 [<span data-ttu-id="ad100-147">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-147">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 <span data-ttu-id="ad100-148">Proporciona capacidades similares a [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), con un método adicional para establecer la interfaz de control host.</span><span class="sxs-lookup"><span data-stu-id="ad100-148">Provides capabilities similar to [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), with an additional method to set the host control interface.</span></span>  
  
 [<span data-ttu-id="ad100-149">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-149">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 <span data-ttu-id="ad100-150">Proporciona métodos para el host para obtener información sobre las tareas solicitadas y detectar interbloqueos en su implementación de la sincronización.</span><span class="sxs-lookup"><span data-stu-id="ad100-150">Provides methods for the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
 [<span data-ttu-id="ad100-151">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-151">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 <span data-ttu-id="ad100-152">Proporciona métodos que permiten al host para realizar solicitudes de CLR, o para proporcionar una notificación al CLR acerca de la tarea asociada.</span><span class="sxs-lookup"><span data-stu-id="ad100-152">Provides methods that enable the host to make requests of the CLR, or to provide notification to the CLR about the associated task.</span></span>  
  
 [<span data-ttu-id="ad100-153">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-153">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 <span data-ttu-id="ad100-154">Proporciona métodos que permiten al host solicitar explícitamente que CLR crea una nueva tarea, obtener la tarea está ejecuta actualmente y establecer el idioma geográfico y la referencia cultural para la tarea.</span><span class="sxs-lookup"><span data-stu-id="ad100-154">Provides methods that enable the host to request explicitly that the CLR create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
 [<span data-ttu-id="ad100-155">ICLRValidator (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-155">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 <span data-ttu-id="ad100-156">Proporciona métodos para validar imágenes portables de ejecutable (PE) e informes de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="ad100-156">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
 [<span data-ttu-id="ad100-157">ICorConfiguration (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-157">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 <span data-ttu-id="ad100-158">Proporciona métodos para configurar el CLR.</span><span class="sxs-lookup"><span data-stu-id="ad100-158">Provides methods for configuring the CLR.</span></span>  
  
 [<span data-ttu-id="ad100-159">ICorThreadpool (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-159">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 <span data-ttu-id="ad100-160">Proporciona métodos para acceder al grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ad100-160">Provides methods for accessing the thread pool.</span></span>  
  
 [<span data-ttu-id="ad100-161">IDebuggerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-161">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 <span data-ttu-id="ad100-162">Proporciona métodos para obtener información sobre el estado de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="ad100-162">Provides methods for obtaining information about the state of the debugging services.</span></span>  
  
 [<span data-ttu-id="ad100-163">IDebuggerThreadControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-163">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 <span data-ttu-id="ad100-164">Proporciona métodos para notificar al host el bloqueo y desbloqueo de subprocesos por los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="ad100-164">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
 [<span data-ttu-id="ad100-165">IGCHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-165">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 <span data-ttu-id="ad100-166">Proporciona métodos para obtener información sobre el sistema de recopilación de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="ad100-166">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
 [<span data-ttu-id="ad100-167">IGCHost2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-167">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 <span data-ttu-id="ad100-168">Proporciona el [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) método que permite a un host establecer el tamaño del segmento de la colección de elementos no utilizados y el tamaño máximo de la generación del sistema de recopilación de elementos no utilizados de cero para los valores mayor `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="ad100-168">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method that enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation zero to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="ad100-169">IGCHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-169">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 <span data-ttu-id="ad100-170">Proporciona un método que permite al recolector de elementos no utilizados solicitar el host para cambiar los límites de memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="ad100-170">Provides a method that enables the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
 [<span data-ttu-id="ad100-171">IGCThreadControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-171">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 <span data-ttu-id="ad100-172">Proporciona métodos para participar en la programación de subprocesos que se bloquearía en caso contrario, para la recolección.</span><span class="sxs-lookup"><span data-stu-id="ad100-172">Provides methods for participating in the scheduling of threads that would otherwise be blocked for garbage collection.</span></span>  
  
 [<span data-ttu-id="ad100-173">IHostAssemblyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-173">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 <span data-ttu-id="ad100-174">Proporciona métodos que permiten a un host especificar conjuntos de ensamblados que se deben cargar CLR o el host.</span><span class="sxs-lookup"><span data-stu-id="ad100-174">Provides methods that enable a host to specify sets of assemblies that should be loaded by the CLR or by the host.</span></span>  
  
 [<span data-ttu-id="ad100-175">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-175">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 <span data-ttu-id="ad100-176">Proporciona métodos que permiten a un host cargar ensamblados y módulos con independencia de CLR.</span><span class="sxs-lookup"><span data-stu-id="ad100-176">Provides methods that enable a host to load assemblies and modules independently of the CLR.</span></span>  
  
 [<span data-ttu-id="ad100-177">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-177">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 <span data-ttu-id="ad100-178">Proporciona una representación de un evento de autorestablecimiento implementado por el host.</span><span class="sxs-lookup"><span data-stu-id="ad100-178">Provides a representation of an auto-reset event implemented by the host.</span></span>  
  
 [<span data-ttu-id="ad100-179">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-179">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 <span data-ttu-id="ad100-180">Proporciona métodos para configurar la carga de ensamblados y para determinar qué interfaces de hospedaje admite el host.</span><span class="sxs-lookup"><span data-stu-id="ad100-180">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
 [<span data-ttu-id="ad100-181">IHostCrst (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-181">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 <span data-ttu-id="ad100-182">Actúa como la representación del host de una sección crítica para el subprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="ad100-182">Serves as the host's representation of a critical section for threading.</span></span>  
  
 [<span data-ttu-id="ad100-183">IHostGCManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-183">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 <span data-ttu-id="ad100-184">Proporciona métodos que notifican al host de eventos en el mecanismo de recopilación de elementos no utilizados implementado por CLR.</span><span class="sxs-lookup"><span data-stu-id="ad100-184">Provides methods that notify the host of events in the garbage collection mechanism implemented by the CLR.</span></span>  
  
 [<span data-ttu-id="ad100-185">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-185">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 <span data-ttu-id="ad100-186">Proporciona métodos que permiten a CLR interactuar con los puertos de terminación de E/S proporcionados por el host.</span><span class="sxs-lookup"><span data-stu-id="ad100-186">Provides methods that enable the CLR to interact with I/O completion ports provided by the host.</span></span>  
  
 [<span data-ttu-id="ad100-187">IHostMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-187">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 <span data-ttu-id="ad100-188">Proporciona métodos para solicitar asignaciones concretas del montón a través del host de CLR.</span><span class="sxs-lookup"><span data-stu-id="ad100-188">Provides methods for the CLR to request fine-grained allocations from the heap through the host.</span></span>  
  
 [<span data-ttu-id="ad100-189">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-189">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 <span data-ttu-id="ad100-190">Proporciona la implementación del host de una representación de un evento de restablecimiento manual.</span><span class="sxs-lookup"><span data-stu-id="ad100-190">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
 [<span data-ttu-id="ad100-191">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-191">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 <span data-ttu-id="ad100-192">Proporciona métodos de CLR realizar solicitudes de memoria virtual a través del host, en lugar de usar las funciones de memoria virtual estándar de Win32.</span><span class="sxs-lookup"><span data-stu-id="ad100-192">Provides methods for the CLR to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
 [<span data-ttu-id="ad100-193">IHostPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-193">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 <span data-ttu-id="ad100-194">Proporciona métodos que notifican al host de las acciones que el CLR realiza en caso de anulaciones, tiempos de espera o errores.</span><span class="sxs-lookup"><span data-stu-id="ad100-194">Provides methods that notify the host of the actions the CLR performs in case of aborts, timeouts, or failures.</span></span>  
  
 [<span data-ttu-id="ad100-195">IHostSecurityContext (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-195">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 <span data-ttu-id="ad100-196">Permite que el CLR para conservar la información de contexto de seguridad implementado por el host.</span><span class="sxs-lookup"><span data-stu-id="ad100-196">Enables the CLR to maintain security context information implemented by the host.</span></span>  
  
 [<span data-ttu-id="ad100-197">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-197">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 <span data-ttu-id="ad100-198">Proporciona métodos que permiten el acceso a y controlan sobre el contexto de seguridad del subproceso en ejecución actualmente.</span><span class="sxs-lookup"><span data-stu-id="ad100-198">Provides methods that enable access to, and control over, the security context of the currently executing thread.</span></span>  
  
 [<span data-ttu-id="ad100-199">IHostSemaphore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-199">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 <span data-ttu-id="ad100-200">Proporciona una representación de un semáforo implementado por el host.</span><span class="sxs-lookup"><span data-stu-id="ad100-200">Provides a representation of a semaphore implemented by the host.</span></span>  
  
 [<span data-ttu-id="ad100-201">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-201">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 <span data-ttu-id="ad100-202">Proporciona métodos para el CLR crear a las primitivas de sincronización llamando al host, en lugar de usar las funciones de sincronización de Win32.</span><span class="sxs-lookup"><span data-stu-id="ad100-202">Provides methods for the CLR to create synchronization primitives by calling the host, instead of using the Win32 synchronization functions.</span></span>  
  
 [<span data-ttu-id="ad100-203">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-203">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 <span data-ttu-id="ad100-204">Proporciona métodos que permiten a CLR para comunicarse con el host para administrar las tareas.</span><span class="sxs-lookup"><span data-stu-id="ad100-204">Provides methods that enable the CLR to communicate with the host to manage tasks.</span></span>  
  
 [<span data-ttu-id="ad100-205">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-205">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 <span data-ttu-id="ad100-206">Proporciona métodos que permiten a CLR trabajar con tareas a través del host en lugar de usar las funciones de fibras o subprocesos de sistema operativo estándar.</span><span class="sxs-lookup"><span data-stu-id="ad100-206">Provides methods that enable the CLR to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
 [<span data-ttu-id="ad100-207">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-207">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 <span data-ttu-id="ad100-208">Proporciona métodos para configurar el grupo de subprocesos y poner en cola los elementos de trabajo al grupo de subprocesos CLR.</span><span class="sxs-lookup"><span data-stu-id="ad100-208">Provides methods for the CLR to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
 [<span data-ttu-id="ad100-209">IManagedObject (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-209">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 <span data-ttu-id="ad100-210">Proporciona métodos para controlar un objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="ad100-210">Provides methods for controlling a managed object.</span></span>  
  
 <span data-ttu-id="ad100-211">"IObjectHandle"</span><span class="sxs-lookup"><span data-stu-id="ad100-211">"IObjectHandle"</span></span>  
 <span data-ttu-id="ad100-212">Proporciona un método para desencapsular objetos de cálculo de referencias por valor desde el direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="ad100-212">Provides a method for unwrapping marshal-by-value objects from indirection.</span></span>  
  
 [<span data-ttu-id="ad100-213">ITypeName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-213">ITypeName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 <span data-ttu-id="ad100-214">Proporciona métodos para obtener información de nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="ad100-214">Provides methods for obtaining type name information.</span></span> <span data-ttu-id="ad100-215">(Esta interfaz admite la infraestructura de .NET Framework y no está pensada para utilizarse directamente desde el código).</span><span class="sxs-lookup"><span data-stu-id="ad100-215">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="ad100-216">ITypeNameBuilder (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-216">ITypeNameBuilder Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 <span data-ttu-id="ad100-217">Proporciona métodos para generar un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="ad100-217">Provides methods for building a type name.</span></span> <span data-ttu-id="ad100-218">(Esta interfaz admite la infraestructura de .NET Framework y no está pensada para utilizarse directamente desde el código).</span><span class="sxs-lookup"><span data-stu-id="ad100-218">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="ad100-219">ITypeNameFactory (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad100-219">ITypeNameFactory Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 <span data-ttu-id="ad100-220">Proporciona métodos para deconstruir un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="ad100-220">Provides methods for deconstructing a type name.</span></span> <span data-ttu-id="ad100-221">(Esta interfaz admite la infraestructura de .NET Framework y no está pensada para utilizarse directamente desde el código).</span><span class="sxs-lookup"><span data-stu-id="ad100-221">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 <span data-ttu-id="ad100-222">"IValidator"</span><span class="sxs-lookup"><span data-stu-id="ad100-222">"IValidator"</span></span>  
 <span data-ttu-id="ad100-223">Proporciona métodos para validar imágenes portables de ejecutable (PE) e informes de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="ad100-223">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ad100-224">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="ad100-224">Related Sections</span></span>  
 [<span data-ttu-id="ad100-225">Coclases e interfaces de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="ad100-225">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="ad100-226">Contiene temas que describen las interfaces de hospedaje proporcionadas en la versión 1.0 y 1.1 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ad100-226">Contains topics that describe the hosting interfaces provided in the .NET Framework version 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="ad100-227">Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5</span><span class="sxs-lookup"><span data-stu-id="ad100-227">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="ad100-228">Contiene temas que describen las interfaces de hospedaje proporcionadas en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ad100-228">Contains topics that describe the hosting interfaces provided in the .NET Framework 4.</span></span>
