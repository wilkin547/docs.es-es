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
ms.openlocfilehash: b78bff2994cefc6c35a4bd59133338392c3a1b24
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791975"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a><span data-ttu-id="b839d-102">ICorDebugRemote::DebugActiveProcessEx (Método)</span><span class="sxs-lookup"><span data-stu-id="b839d-102">ICorDebugRemote::DebugActiveProcessEx Method</span></span>
<span data-ttu-id="b839d-103">Inicia un proceso en un equipo remoto en el depurador.</span><span class="sxs-lookup"><span data-stu-id="b839d-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b839d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b839d-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b839d-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="b839d-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="b839d-106">de Puntero a una [interfaz ICorDebugRemoteTarget](icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="b839d-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="b839d-107">Este parámetro se usa para determinar el equipo en el que se está ejecutando el proceso.</span><span class="sxs-lookup"><span data-stu-id="b839d-107">This parameter is used to determine the machine on which the process is running.</span></span>  
  
 `id`  
 <span data-ttu-id="b839d-108">de IDENTIFICADOR del proceso al que se va a adjuntar el depurador.</span><span class="sxs-lookup"><span data-stu-id="b839d-108">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="b839d-109">[in] `true` si el depurador debe comportarse como el depurador de Win32 para el proceso y enviar las devoluciones de llamada no administradas; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="b839d-109">[in] `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="b839d-110">enuncia Puntero a la dirección de un objeto "ICorDebugProcess" que representa el proceso al que se ha adjuntado el depurador.</span><span class="sxs-lookup"><span data-stu-id="b839d-110">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b839d-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b839d-111">Return Value</span></span>  
 <span data-ttu-id="b839d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b839d-112">S_OK</span></span>  
 <span data-ttu-id="b839d-113">Se adjuntó correctamente al proceso en el equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="b839d-113">Successfully attached to the process on the remote machine.</span></span>  
  
 <span data-ttu-id="b839d-114">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="b839d-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="b839d-115">No se puede asociar al proceso en el equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="b839d-115">Unable to attach to the process on the remote machine.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b839d-116">Notas</span><span class="sxs-lookup"><span data-stu-id="b839d-116">Remarks</span></span>  
 <span data-ttu-id="b839d-117">En Silverlight no se admite la depuración en modo mixto.</span><span class="sxs-lookup"><span data-stu-id="b839d-117">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b839d-118">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="b839d-118">Requirements</span></span>  
 <span data-ttu-id="b839d-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b839d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b839d-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b839d-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b839d-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b839d-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b839d-122">**.NET Framework versiones:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="b839d-122">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b839d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="b839d-123">See also</span></span>

- [<span data-ttu-id="b839d-124">ICorDebugRemote (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b839d-124">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="b839d-125">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b839d-125">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="b839d-126">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b839d-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
