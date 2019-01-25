---
title: ICorDebugRemote::DebugActiveProcessEx (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.DebugActiveProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::DebugActiveProcessEx
helpviewer_keywords:
- ICorDebugRemote::DebugActiveProcessEx method [.NET Framework debugging]
- DebugActiveProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: b0df5c5d-9a2e-47bf-894c-6f8a9fe24a1f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb085cc486c307a308258709f4c58619597bc202
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608393"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a><span data-ttu-id="7fc1b-102">ICorDebugRemote::DebugActiveProcessEx (Método)</span><span class="sxs-lookup"><span data-stu-id="7fc1b-102">ICorDebugRemote::DebugActiveProcessEx Method</span></span>
<span data-ttu-id="7fc1b-103">Inicia un proceso en un equipo remoto en el depurador.</span><span class="sxs-lookup"><span data-stu-id="7fc1b-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fc1b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7fc1b-104">Syntax</span></span>  
  
```  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7fc1b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7fc1b-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="7fc1b-106">[in] Puntero a un [ICorDebugRemoteTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="7fc1b-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="7fc1b-107">Este parámetro se usa para determinar la máquina donde se ejecuta el proceso.</span><span class="sxs-lookup"><span data-stu-id="7fc1b-107">This parameter is used to determine the machine on which the process is running.</span></span>  
  
 `id`  
 <span data-ttu-id="7fc1b-108">[in] El identificador del proceso al que va a adjuntar el depurador.</span><span class="sxs-lookup"><span data-stu-id="7fc1b-108">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="7fc1b-109">[in] `true` si el depurador debe comportarse como el depurador de Win32 para el proceso y enviar las devoluciones de llamada no administradas; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="7fc1b-109">[in] `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="7fc1b-110">[out] Un puntero a la dirección de un objeto "ICorDebugProcess" que representa el proceso al que se ha vinculado el depurador.</span><span class="sxs-lookup"><span data-stu-id="7fc1b-110">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7fc1b-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7fc1b-111">Return Value</span></span>  
 <span data-ttu-id="7fc1b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="7fc1b-112">S_OK</span></span>  
 <span data-ttu-id="7fc1b-113">Se conectó correctamente al proceso en el equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="7fc1b-113">Successfully attached to the process on the remote machine.</span></span>  
  
 <span data-ttu-id="7fc1b-114">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="7fc1b-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="7fc1b-115">No se puede asociar al proceso en el equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="7fc1b-115">Unable to attach to the process on the remote machine.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7fc1b-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7fc1b-116">Remarks</span></span>  
 <span data-ttu-id="7fc1b-117">No se admite la depuración en modo mixto en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="7fc1b-117">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fc1b-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7fc1b-118">Requirements</span></span>  
 <span data-ttu-id="7fc1b-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fc1b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fc1b-120">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7fc1b-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7fc1b-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7fc1b-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7fc1b-122">**Versiones de .NET framework:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="7fc1b-122">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fc1b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fc1b-123">See also</span></span>
- [<span data-ttu-id="7fc1b-124">ICorDebugRemote (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7fc1b-124">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="7fc1b-125">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7fc1b-125">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="7fc1b-126">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7fc1b-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
