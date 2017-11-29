---
title: ICoreClrDebugTarget (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICoreClrDebugTarget
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: ICoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget interface
- Silverlight, remote debugging
ms.assetid: 7cfaee76-e284-4a66-a431-8e33f0f60038
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e13355078727a55c950bed795d3b01b6c7d52564
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="d373b-102">ICoreClrDebugTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d373b-102">ICoreClrDebugTarget Interface</span></span>
<span data-ttu-id="d373b-103">Proporciona métodos que controlan los recuentos de referencias, enumerar los procesos y liberar la memoria asociada a un depurador que se adjunta a un destino remoto de Silverlight de Macintosh.</span><span class="sxs-lookup"><span data-stu-id="d373b-103">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d373b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d373b-104">Syntax</span></span>  
  
```  
class ICoreClrDebugTarget {  
      HRESULT EnumProcesses (  
          [out] DWORD*                    pcProcs,  
          [out] CoreClrDebugProcInfo**    ppProcs  
      );  
  
      HRESULT EnumRuntimes (  
      [in]  DWORD                      dwInternalProcessID,  
      [out] DWORD*                     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**  ppRuntimes  
      );  
  
      void FreeMemory (  
      [in] void*      pMemory  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d373b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d373b-105">Methods</span></span>  
  
|<span data-ttu-id="d373b-106">Método</span><span class="sxs-lookup"><span data-stu-id="d373b-106">Method</span></span>|<span data-ttu-id="d373b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d373b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d373b-108">Icoreclrdebugtarget:: EnumProcesses (método)</span><span class="sxs-lookup"><span data-stu-id="d373b-108">ICoreClrDebugTarget::EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="d373b-109">Enumera los procesos que se ejecutan en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="d373b-109">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="d373b-110">Icoreclrdebugtarget:: Enumruntimes (método)</span><span class="sxs-lookup"><span data-stu-id="d373b-110">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="d373b-111">Enumera los common language Runtime (CLR) en el proceso especificado en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="d373b-111">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="d373b-112">Icoreclrdebugtarget (método)</span><span class="sxs-lookup"><span data-stu-id="d373b-112">ICoreClrDebugTarget::FreeMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="d373b-113">Libera la memoria que se asigna mediante los métodos de enumeración de esta clase.</span><span class="sxs-lookup"><span data-stu-id="d373b-113">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d373b-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d373b-114">Remarks</span></span>  
 <span data-ttu-id="d373b-115">Actualmente, esta funcionalidad solo se admite para la depuración de un destino de la aplicación basada en Silverlight que se ejecuta en un equipo Macintosh remoto.</span><span class="sxs-lookup"><span data-stu-id="d373b-115">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d373b-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d373b-116">Requirements</span></span>  
 <span data-ttu-id="d373b-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d373b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d373b-118">**Encabezado:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="d373b-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="d373b-119">**Biblioteca:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="d373b-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="d373b-120">**Versiones de .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="d373b-120">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d373b-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d373b-121">See Also</span></span>  
 [<span data-ttu-id="d373b-122">ICorDebugRemoteTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d373b-122">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="d373b-123">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d373b-123">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="d373b-124">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d373b-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
