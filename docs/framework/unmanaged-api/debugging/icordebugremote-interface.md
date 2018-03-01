---
title: ICorDebugRemote (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugRemote
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemote
helpviewer_keywords:
- ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: 53d073c6-fa02-40d2-82e1-b9452bb6abaa
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cc34c3a1049a24a27fae4d13288efbd5a98a4dc9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="30a71-102">ICorDebugRemote (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="30a71-102">ICorDebugRemote Interface</span></span>
<span data-ttu-id="30a71-103">Proporciona la capacidad de iniciar o de adjuntar un depurador administrado a un proceso remoto de destino.</span><span class="sxs-lookup"><span data-stu-id="30a71-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30a71-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30a71-104">Syntax</span></span>  
  
```  
interface ICorDebugRemote : IUnknown  
{  
    HRESULT CreateProcessEx  
      (  
      [in] ICorDebugRemoteTarget *     pRemoteTarget,  
      [in] LPCWSTR                     lpApplicationName,  
      [in] LPWSTR                      lpCommandLine,  
      [in] LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
      [in] LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
      [in] BOOL                        bInheritHandles,  
      [in] DWORD                       dwCreationFlags,  
      [in] PVOID                       lpEnvironment,  
      [in] LPCWSTR                     lpCurrentDirectory,  
      [in] LPSTARTUPINFOW              lpStartupInfo,  
      [in] LPPROCESS_INFORMATION       lpProcessInformation,  
      [in] CorDebugCreateProcessFlags  debuggingFlags,  
      [out] ICorDebugProcess **        ppProcess  
      );  
  
    HRESULT DebugActiveProcessEx  
      (  
      [in] ICorDebugRemoteTarget *   pRemoteTarget,  
      [in] DWORD                     dwProcessId,  
      [in] BOOL                      fWin32Attach,  
      [out] ICorDebugProcess **      ppProcess  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="30a71-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="30a71-105">Methods</span></span>  
  
|<span data-ttu-id="30a71-106">Método</span><span class="sxs-lookup"><span data-stu-id="30a71-106">Method</span></span>|<span data-ttu-id="30a71-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="30a71-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="30a71-108">ICorDebugRemote::CreateProcessEx (método)</span><span class="sxs-lookup"><span data-stu-id="30a71-108">ICorDebugRemote::CreateProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-createprocessex-method.md)|<span data-ttu-id="30a71-109">Crea un proceso en un equipo remoto para la depuración administrada.</span><span class="sxs-lookup"><span data-stu-id="30a71-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="30a71-110">ICorDebugRemote::DebugActiveProcessEx (método)</span><span class="sxs-lookup"><span data-stu-id="30a71-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="30a71-111">Inicia un proceso en un equipo remoto en el depurador.</span><span class="sxs-lookup"><span data-stu-id="30a71-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30a71-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="30a71-112">Remarks</span></span>  
 <span data-ttu-id="30a71-113">Actualmente, esta funcionalidad solo se admite para la depuración de un destino de la aplicación basada en Silverlight que se ejecuta en un equipo Macintosh remoto.</span><span class="sxs-lookup"><span data-stu-id="30a71-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30a71-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30a71-114">Requirements</span></span>  
 <span data-ttu-id="30a71-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30a71-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30a71-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30a71-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30a71-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30a71-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30a71-118">**Versiones de .NET framework:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="30a71-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30a71-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="30a71-119">See Also</span></span>  
 [<span data-ttu-id="30a71-120">ICorDebugRemoteTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="30a71-120">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="30a71-121">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="30a71-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="30a71-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="30a71-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
