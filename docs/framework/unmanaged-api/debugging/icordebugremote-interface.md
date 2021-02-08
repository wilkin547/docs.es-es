---
description: 'Más información acerca de: interfaz ICorDebugRemote'
title: ICorDebugRemote (Interfaz)
ms.date: 03/30/2017
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
ms.openlocfilehash: 4c9d92800c68155216a077180ea0b613c67423dd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790677"
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="34947-103">ICorDebugRemote (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="34947-103">ICorDebugRemote Interface</span></span>

<span data-ttu-id="34947-104">Proporciona la capacidad de iniciar o de adjuntar un depurador administrado a un proceso remoto de destino.</span><span class="sxs-lookup"><span data-stu-id="34947-104">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34947-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="34947-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="methods"></a><span data-ttu-id="34947-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="34947-106">Methods</span></span>  
  
|<span data-ttu-id="34947-107">Método</span><span class="sxs-lookup"><span data-stu-id="34947-107">Method</span></span>|<span data-ttu-id="34947-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="34947-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="34947-109">ICorDebugRemote::CreateProcessEx (Método)</span><span class="sxs-lookup"><span data-stu-id="34947-109">ICorDebugRemote::CreateProcessEx Method</span></span>](icordebugremote-createprocessex-method.md)|<span data-ttu-id="34947-110">Crea un proceso en un equipo remoto para la depuración administrada.</span><span class="sxs-lookup"><span data-stu-id="34947-110">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="34947-111">ICorDebugRemote::DebugActiveProcessEx (Método)</span><span class="sxs-lookup"><span data-stu-id="34947-111">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="34947-112">Inicia un proceso en un equipo remoto en el depurador.</span><span class="sxs-lookup"><span data-stu-id="34947-112">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34947-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="34947-113">Remarks</span></span>  

 <span data-ttu-id="34947-114">Actualmente, esta funcionalidad solo se admite para depurar un destino de aplicación basado en Silverlight que se ejecute en un equipo remoto de Macintosh.</span><span class="sxs-lookup"><span data-stu-id="34947-114">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34947-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="34947-115">Requirements</span></span>  

 <span data-ttu-id="34947-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34947-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34947-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34947-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34947-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34947-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34947-119">**.NET Framework versiones:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="34947-119">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34947-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="34947-120">See also</span></span>

- [<span data-ttu-id="34947-121">ICorDebugRemoteTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="34947-121">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="34947-122">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="34947-122">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="34947-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="34947-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
