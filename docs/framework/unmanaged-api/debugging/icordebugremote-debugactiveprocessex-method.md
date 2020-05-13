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
ms.openlocfilehash: b95e9f3a0d584511a2bcf156ed2c50a98f96d071
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379062"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a><span data-ttu-id="37239-102">ICorDebugRemote::DebugActiveProcessEx (Método)</span><span class="sxs-lookup"><span data-stu-id="37239-102">ICorDebugRemote::DebugActiveProcessEx Method</span></span>
<span data-ttu-id="37239-103">Inicia un proceso en un equipo remoto en el depurador.</span><span class="sxs-lookup"><span data-stu-id="37239-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37239-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37239-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37239-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="37239-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="37239-106">de Puntero a una [interfaz ICorDebugRemoteTarget](icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="37239-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="37239-107">Este parámetro se usa para determinar el equipo en el que se está ejecutando el proceso.</span><span class="sxs-lookup"><span data-stu-id="37239-107">This parameter is used to determine the machine on which the process is running.</span></span>  
  
 `id`  
 <span data-ttu-id="37239-108">de IDENTIFICADOR del proceso al que se va a adjuntar el depurador.</span><span class="sxs-lookup"><span data-stu-id="37239-108">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="37239-109">[in] `true` Si el depurador debe comportarse como el depurador de Win32 para el proceso y enviar las devoluciones de llamada no administradas; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="37239-109">[in] `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="37239-110">enuncia Puntero a la dirección de un objeto "ICorDebugProcess" que representa el proceso al que se ha adjuntado el depurador.</span><span class="sxs-lookup"><span data-stu-id="37239-110">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37239-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="37239-111">Return Value</span></span>  
 <span data-ttu-id="37239-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="37239-112">S_OK</span></span>  
 <span data-ttu-id="37239-113">Se adjuntó correctamente al proceso en el equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="37239-113">Successfully attached to the process on the remote machine.</span></span>  
  
 <span data-ttu-id="37239-114">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="37239-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="37239-115">No se puede asociar al proceso en el equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="37239-115">Unable to attach to the process on the remote machine.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37239-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="37239-116">Remarks</span></span>  
 <span data-ttu-id="37239-117">En Silverlight no se admite la depuración en modo mixto.</span><span class="sxs-lookup"><span data-stu-id="37239-117">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37239-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="37239-118">Requirements</span></span>  
 <span data-ttu-id="37239-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37239-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37239-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="37239-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37239-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37239-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37239-122">**.NET Framework versiones:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="37239-122">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37239-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="37239-123">See also</span></span>

- [<span data-ttu-id="37239-124">ICorDebugRemote (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="37239-124">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="37239-125">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="37239-125">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="37239-126">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="37239-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
