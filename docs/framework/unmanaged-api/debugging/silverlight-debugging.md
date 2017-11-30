---
title: "Depuración en Silverlight"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bf39d2dd12207d594c7bf5bd5b249d82c3f15d3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="silverlight-debugging"></a><span data-ttu-id="56cc0-102">Depuración en Silverlight</span><span class="sxs-lookup"><span data-stu-id="56cc0-102">Silverlight Debugging</span></span>
<span data-ttu-id="56cc0-103">En los temas de esta sección describen el entorno y las interfaces que Common Language Runtime (CLR) proporciona para admitir la depuración de aplicaciones basadas en Silverlight que se ejecutan en el sistema operativo Windows, o en la plataforma Macintosh.</span><span class="sxs-lookup"><span data-stu-id="56cc0-103">The topics in this section describe the environment and interfaces that the common language runtime (CLR) provides to support debugging Silverlight-based applications that are running on the Windows operating system, or on the Macintosh platform.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="56cc0-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="56cc0-104">In This Section</span></span>  
 [<span data-ttu-id="56cc0-105">EnumerateCLRs (función)</span><span class="sxs-lookup"><span data-stu-id="56cc0-105">EnumerateCLRs Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)  
 <span data-ttu-id="56cc0-106">Proporciona un mecanismo para enumerar los CLR de un proceso.</span><span class="sxs-lookup"><span data-stu-id="56cc0-106">Provides a mechanism for enumerating the CLRs in a process.</span></span>  
  
 [<span data-ttu-id="56cc0-107">CloseCLREnumeration (función)</span><span class="sxs-lookup"><span data-stu-id="56cc0-107">CloseCLREnumeration Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/closeclrenumeration-function.md)  
 <span data-ttu-id="56cc0-108">Cierra los eventos de inicio continuo de CLR válidos ubicados en una matriz de identificadores devuelta por la [EnumerateCLRs (función)](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)y libera la memoria para las matrices de rutas de cadenas y los identificadores.</span><span class="sxs-lookup"><span data-stu-id="56cc0-108">Closes any valid CLR continue-startup events located in an array of handles returned by the [EnumerateCLRs Function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
 [<span data-ttu-id="56cc0-109">CreateCoreClrDebugTarget (función)</span><span class="sxs-lookup"><span data-stu-id="56cc0-109">CreateCoreClrDebugTarget Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createcoreclrdebugtarget-function.md)  
 <span data-ttu-id="56cc0-110">Crea una conexión a un destino remoto para la enumeración de procesos y tiempos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="56cc0-110">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="56cc0-111">CreateCordbObject (función)</span><span class="sxs-lookup"><span data-stu-id="56cc0-111">CreateCordbObject Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createcordbobject-function.md)  
 <span data-ttu-id="56cc0-112">Crea una interfaz de depurador que proporciona la funcionalidad para crear instancias de una sesión de depuración administrada en un proceso remoto.</span><span class="sxs-lookup"><span data-stu-id="56cc0-112">Creates a debugger interface that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
 [<span data-ttu-id="56cc0-113">CreateVersionStringFromModule (función)</span><span class="sxs-lookup"><span data-stu-id="56cc0-113">CreateVersionStringFromModule Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)  
 <span data-ttu-id="56cc0-114">Crea una cadena de versión a partir de una ruta de acceso de CLR en un proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="56cc0-114">Creates a version string from a CLR path in a target process.</span></span>  
  
 [<span data-ttu-id="56cc0-115">CreateDebuggingInterfaceFromVersion (función)</span><span class="sxs-lookup"><span data-stu-id="56cc0-115">CreateDebuggingInterfaceFromVersion Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createdebugginginterfacefromversion-function-for-silverlight.md)  
 <span data-ttu-id="56cc0-116">Acepta una cadena de versión CLR que se devuelve desde [CreateVersionStringFromModule (función)](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)función y devuelve una interfaz de depurador correspondiente.</span><span class="sxs-lookup"><span data-stu-id="56cc0-116">Accepts a CLR version string returned from [CreateVersionStringFromModule Function](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)function, and returns a corresponding debugger interface.</span></span>  
  
 [<span data-ttu-id="56cc0-117">CoreClrDebugProcInfo (estructura)</span><span class="sxs-lookup"><span data-stu-id="56cc0-117">CoreClrDebugProcInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md)  
 <span data-ttu-id="56cc0-118">Representa un proceso que se ejecuta en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="56cc0-118">Represents a process that is running on a remote machine.</span></span>  
  
 [<span data-ttu-id="56cc0-119">CoreClrDebugRuntimeInfo (estructura)</span><span class="sxs-lookup"><span data-stu-id="56cc0-119">CoreClrDebugRuntimeInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md)  
 <span data-ttu-id="56cc0-120">Representa una instancia de CLR que se carga en un proceso en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="56cc0-120">Represents a CLR instance that is loaded in a process on a remote machine.</span></span>  
  
 [<span data-ttu-id="56cc0-121">GetStartupNotificationEvent (función)</span><span class="sxs-lookup"><span data-stu-id="56cc0-121">GetStartupNotificationEvent Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/getstartupnotificationevent-function.md)  
 <span data-ttu-id="56cc0-122">Crea o abre un identificador de evento al que señalará cualquier Common Language Runtime (CLR) que se cargue en el proceso de destino especificado.</span><span class="sxs-lookup"><span data-stu-id="56cc0-122">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
 [<span data-ttu-id="56cc0-123">ICoreClrDebugTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="56cc0-123">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)  
 <span data-ttu-id="56cc0-124">Crea una conexión a un destino remoto para la enumeración de procesos y tiempos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="56cc0-124">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="56cc0-125">InitDbgTransportManager (función)</span><span class="sxs-lookup"><span data-stu-id="56cc0-125">InitDbgTransportManager Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/initdbgtransportmanager-function.md)  
 <span data-ttu-id="56cc0-126">Inicializa el administrador de transporte para conectarse a un destino remoto para la enumeración de proceso y tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="56cc0-126">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="56cc0-127">ShutdownDbgTransportManager (función)</span><span class="sxs-lookup"><span data-stu-id="56cc0-127">ShutdownDbgTransportManager Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/shutdowndbgtransportmanager-function.md)  
 <span data-ttu-id="56cc0-128">Cierra el administrador de transporte para una conexión a un equipo de destino remoto.</span><span class="sxs-lookup"><span data-stu-id="56cc0-128">Shuts down the transport manager for a connection to a remote target machine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56cc0-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="56cc0-129">See Also</span></span>  
 [<span data-ttu-id="56cc0-130">Coclases para la depuración</span><span class="sxs-lookup"><span data-stu-id="56cc0-130">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
 [<span data-ttu-id="56cc0-131">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="56cc0-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="56cc0-132">Funciones estáticas globales para la depuración</span><span class="sxs-lookup"><span data-stu-id="56cc0-132">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
 [<span data-ttu-id="56cc0-133">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="56cc0-133">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="56cc0-134">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="56cc0-134">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
