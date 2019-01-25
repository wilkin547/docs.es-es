---
title: ICoreClrDebugTarget::EnumRuntimes (Método)
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumRuntimes
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumRuntimes
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget::EnumRuntimes method [Silverlight debugging]
- EnumRuntimes method, ICoreClrDebugTarget interface [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 316df866-442d-40cc-b049-45e8adcb65d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac0cee9affff03a95cd7635a8b1afd42e6edc6ef
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684336"
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a><span data-ttu-id="8fc0b-102">ICoreClrDebugTarget::EnumRuntimes (Método)</span><span class="sxs-lookup"><span data-stu-id="8fc0b-102">ICoreClrDebugTarget::EnumRuntimes Method</span></span>
<span data-ttu-id="8fc0b-103">Enumera los Common Language Runtime(CLR) del proceso especificado que se están ejecutando en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="8fc0b-103">Enumerates the common language runtimes (CLRs) in the specified process that is running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fc0b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8fc0b-104">Syntax</span></span>  
  
```  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8fc0b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8fc0b-105">Parameters</span></span>  
 `dwInternalProcessID`  
 <span data-ttu-id="8fc0b-106">[in] Identificador de proceso interno del proceso para el que desea enumerar los tiempos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8fc0b-106">[in] The internal process ID of the process for which you want to enumerate runtimes.</span></span> <span data-ttu-id="8fc0b-107">Se trata de `m_dwInternalID` de las correspondientes [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md).</span><span class="sxs-lookup"><span data-stu-id="8fc0b-107">This will be `m_dwInternalID` from the corresponding [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md).</span></span>  
  
 `pcRuntimes`  
 <span data-ttu-id="8fc0b-108">[out] Número de tiempos de ejecución que se devuelve en `ppRuntimes`.</span><span class="sxs-lookup"><span data-stu-id="8fc0b-108">[out] The number of runtimes returned in `ppRuntimes`.</span></span> <span data-ttu-id="8fc0b-109">Este valor puede ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="8fc0b-109">This value can be 0 (zero).</span></span>  
  
 `ppRuntimes`  
 <span data-ttu-id="8fc0b-110">[out] Una matriz de [CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) estructuras que representan los tiempos de ejecución cargan en el proceso de destino remoto.</span><span class="sxs-lookup"><span data-stu-id="8fc0b-110">[out] An array of [CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) structures that represent the runtimes loaded in the remote target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8fc0b-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8fc0b-111">Return Value</span></span>  
 <span data-ttu-id="8fc0b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="8fc0b-112">S_OK</span></span>  
 <span data-ttu-id="8fc0b-113">Correcto.</span><span class="sxs-lookup"><span data-stu-id="8fc0b-113">Success.</span></span>  
  
 <span data-ttu-id="8fc0b-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="8fc0b-114">S_FALSE</span></span>  
 <span data-ttu-id="8fc0b-115">`dwInternalProcessID` no coincide con ningún proceso que se esté ejecutando en el equipo, probablemente porque finalizó el proceso.</span><span class="sxs-lookup"><span data-stu-id="8fc0b-115">`dwInternalProcessID` does not match any process that is running on the computer, probably because the process was terminated.</span></span> <span data-ttu-id="8fc0b-116">`pcRuntimes` y `ppRuntimes` serán nulos.</span><span class="sxs-lookup"><span data-stu-id="8fc0b-116">`pcRuntimes` and `ppRuntimes` will be null.</span></span>  
  
 <span data-ttu-id="8fc0b-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8fc0b-117">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="8fc0b-118">No se puede asignar memoria suficiente para `ppRuntimes`.</span><span class="sxs-lookup"><span data-stu-id="8fc0b-118">Unable to allocate enough memory for `ppRuntimes`.</span></span>  
  
 <span data-ttu-id="8fc0b-119">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="8fc0b-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="8fc0b-120">Otros errores.</span><span class="sxs-lookup"><span data-stu-id="8fc0b-120">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8fc0b-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8fc0b-121">Remarks</span></span>  
 <span data-ttu-id="8fc0b-122">Para liberar la memoria asignada por este método, llame a la [Icoreclrdebugtarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="8fc0b-122">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fc0b-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8fc0b-123">Requirements</span></span>  
 <span data-ttu-id="8fc0b-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fc0b-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fc0b-125">**Encabezado**: CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="8fc0b-125">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="8fc0b-126">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="8fc0b-126">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="8fc0b-127">**Versiones de .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="8fc0b-127">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fc0b-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="8fc0b-128">See also</span></span>
- [<span data-ttu-id="8fc0b-129">ICoreClrDebugTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8fc0b-129">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
