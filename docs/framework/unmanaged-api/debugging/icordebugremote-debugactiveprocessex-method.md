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
ms.openlocfilehash: 83cc4eadca7c337c06c5fbf9f0e74306c2b9cb99
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131272"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a><span data-ttu-id="0e31b-102">ICorDebugRemote::DebugActiveProcessEx (Método)</span><span class="sxs-lookup"><span data-stu-id="0e31b-102">ICorDebugRemote::DebugActiveProcessEx Method</span></span>
<span data-ttu-id="0e31b-103">Inicia un proceso en un equipo remoto en el depurador.</span><span class="sxs-lookup"><span data-stu-id="0e31b-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e31b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e31b-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e31b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0e31b-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="0e31b-106">de Puntero a una [interfaz ICorDebugRemoteTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="0e31b-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="0e31b-107">Este parámetro se usa para determinar el equipo en el que se está ejecutando el proceso.</span><span class="sxs-lookup"><span data-stu-id="0e31b-107">This parameter is used to determine the machine on which the process is running.</span></span>  
  
 `id`  
 <span data-ttu-id="0e31b-108">de IDENTIFICADOR del proceso al que se va a adjuntar el depurador.</span><span class="sxs-lookup"><span data-stu-id="0e31b-108">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="0e31b-109">[in] `true` si el depurador debe comportarse como el depurador de Win32 para el proceso y enviar las devoluciones de llamada no administradas; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="0e31b-109">[in] `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="0e31b-110">enuncia Puntero a la dirección de un objeto "ICorDebugProcess" que representa el proceso al que se ha adjuntado el depurador.</span><span class="sxs-lookup"><span data-stu-id="0e31b-110">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e31b-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0e31b-111">Return Value</span></span>  
 <span data-ttu-id="0e31b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0e31b-112">S_OK</span></span>  
 <span data-ttu-id="0e31b-113">Se adjuntó correctamente al proceso en el equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="0e31b-113">Successfully attached to the process on the remote machine.</span></span>  
  
 <span data-ttu-id="0e31b-114">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="0e31b-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="0e31b-115">No se puede asociar al proceso en el equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="0e31b-115">Unable to attach to the process on the remote machine.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e31b-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0e31b-116">Remarks</span></span>  
 <span data-ttu-id="0e31b-117">En Silverlight no se admite la depuración en modo mixto.</span><span class="sxs-lookup"><span data-stu-id="0e31b-117">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e31b-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e31b-118">Requirements</span></span>  
 <span data-ttu-id="0e31b-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e31b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e31b-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e31b-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e31b-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e31b-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e31b-122">**.NET Framework versiones:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="0e31b-122">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e31b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e31b-123">See also</span></span>

- [<span data-ttu-id="0e31b-124">ICorDebugRemote (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0e31b-124">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="0e31b-125">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0e31b-125">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="0e31b-126">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="0e31b-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
