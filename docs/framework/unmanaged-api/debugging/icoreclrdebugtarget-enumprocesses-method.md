---
title: ICoreClrDebugTarget::EnumProcesses (Método)
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumProcesses
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumProcesses
helpviewer_keywords:
- remote debugging API [Silverlight]
- EnumProcesses method, ICorClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::EnumProcesses method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: e00fd477-4f49-43d3-bd0e-3094824b1136
topic_type:
- apiref
ms.openlocfilehash: 6484832e8e737b9a0d0b3eaf3ede4078729f7a4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178436"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a><span data-ttu-id="2a3a8-102">ICoreClrDebugTarget::EnumProcesses (Método)</span><span class="sxs-lookup"><span data-stu-id="2a3a8-102">ICoreClrDebugTarget::EnumProcesses Method</span></span>
<span data-ttu-id="2a3a8-103">Enumera los procesos que se ejecutan en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="2a3a8-103">Enumerates the processes that are running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a3a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a3a8-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a3a8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a3a8-105">Parameters</span></span>  
 `pcProcs`  
 <span data-ttu-id="2a3a8-106">[out] Número de procesos que se devuelve en `ppProcs`.</span><span class="sxs-lookup"><span data-stu-id="2a3a8-106">[out] The number of processes returned in `ppProcs`.</span></span> <span data-ttu-id="2a3a8-107">Este valor puede ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="2a3a8-107">This value can be 0 (zero).</span></span>  
  
 `ppProcs`  
 <span data-ttu-id="2a3a8-108">[fuera] Matriz de [estructuras CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md) que representan los procesos que se ejecutan en el equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="2a3a8-108">[out] An array of [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md) structures that represent the processes running on the remote computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a3a8-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2a3a8-109">Return Value</span></span>  
 <span data-ttu-id="2a3a8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2a3a8-110">S_OK</span></span>  
 <span data-ttu-id="2a3a8-111">Correcto.</span><span class="sxs-lookup"><span data-stu-id="2a3a8-111">Success.</span></span>  
  
 <span data-ttu-id="2a3a8-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2a3a8-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="2a3a8-113">No se puede asignar memoria suficiente para `ppProcs`.</span><span class="sxs-lookup"><span data-stu-id="2a3a8-113">Unable to allocate enough memory for `ppProcs`.</span></span>  
  
 <span data-ttu-id="2a3a8-114">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="2a3a8-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="2a3a8-115">Otros errores.</span><span class="sxs-lookup"><span data-stu-id="2a3a8-115">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a3a8-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2a3a8-116">Remarks</span></span>  
 <span data-ttu-id="2a3a8-117">Para liberar la memoria asignada por este método, llame a la [ICoreClrDebugTarget::FreeMemory](icoreclrdebugtarget-freememory-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="2a3a8-117">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a3a8-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a3a8-118">Requirements</span></span>  
 <span data-ttu-id="2a3a8-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a3a8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a3a8-120">**Encabezado:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="2a3a8-120">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="2a3a8-121">**Biblioteca:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="2a3a8-121">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="2a3a8-122">**Versiones de .NET Framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="2a3a8-122">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a3a8-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2a3a8-123">See also</span></span>

- [<span data-ttu-id="2a3a8-124">ICoreClrDebugTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2a3a8-124">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)
