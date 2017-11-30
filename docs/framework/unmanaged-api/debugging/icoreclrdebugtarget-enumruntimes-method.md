---
title: "ICoreClrDebugTarget::EnumRuntimes (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICoreClrDebugTarget.EnumRuntimes
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: ICoreClrDebugTarget::EnumRuntimes
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget::EnumRuntimes method [Silverlight debugging]
- EnumRuntimes method, ICoreClrDebugTarget interface [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 316df866-442d-40cc-b049-45e8adcb65d1
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d28e5f3f529f72607e2ddd84789e89f82dcdaba0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a><span data-ttu-id="b6767-102">ICoreClrDebugTarget::EnumRuntimes (Método)</span><span class="sxs-lookup"><span data-stu-id="b6767-102">ICoreClrDebugTarget::EnumRuntimes Method</span></span>
<span data-ttu-id="b6767-103">Enumera los Common Language Runtime(CLR) del proceso especificado que se están ejecutando en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="b6767-103">Enumerates the common language runtimes (CLRs) in the specified process that is running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6767-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6767-104">Syntax</span></span>  
  
```  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b6767-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b6767-105">Parameters</span></span>  
 `dwInternalProcessID`  
 <span data-ttu-id="b6767-106">[in] Identificador de proceso interno del proceso para el que desea enumerar los tiempos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b6767-106">[in] The internal process ID of the process for which you want to enumerate runtimes.</span></span> <span data-ttu-id="b6767-107">Se trata de `m_dwInternalID` desde correspondiente [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md).</span><span class="sxs-lookup"><span data-stu-id="b6767-107">This will be `m_dwInternalID` from the corresponding [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md).</span></span>  
  
 `pcRuntimes`  
 <span data-ttu-id="b6767-108">[out] Número de tiempos de ejecución que se devuelve en `ppRuntimes`.</span><span class="sxs-lookup"><span data-stu-id="b6767-108">[out] The number of runtimes returned in `ppRuntimes`.</span></span> <span data-ttu-id="b6767-109">Este valor puede ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="b6767-109">This value can be 0 (zero).</span></span>  
  
 `ppRuntimes`  
 <span data-ttu-id="b6767-110">[out] Una matriz de [CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) estructuras que representan los tiempos de ejecución cargan en el proceso de destino remoto.</span><span class="sxs-lookup"><span data-stu-id="b6767-110">[out] An array of [CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) structures that represent the runtimes loaded in the remote target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6767-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b6767-111">Return Value</span></span>  
 <span data-ttu-id="b6767-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b6767-112">S_OK</span></span>  
 <span data-ttu-id="b6767-113">Correcto.</span><span class="sxs-lookup"><span data-stu-id="b6767-113">Success.</span></span>  
  
 <span data-ttu-id="b6767-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b6767-114">S_FALSE</span></span>  
 <span data-ttu-id="b6767-115">`dwInternalProcessID` no coincide con ningún proceso que se esté ejecutando en el equipo, probablemente porque finalizó el proceso.</span><span class="sxs-lookup"><span data-stu-id="b6767-115">`dwInternalProcessID` does not match any process that is running on the computer, probably because the process was terminated.</span></span> <span data-ttu-id="b6767-116">`pcRuntimes` y `ppRuntimes` serán nulos.</span><span class="sxs-lookup"><span data-stu-id="b6767-116">`pcRuntimes` and `ppRuntimes` will be null.</span></span>  
  
 <span data-ttu-id="b6767-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b6767-117">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="b6767-118">No se puede asignar memoria suficiente para `ppRuntimes`.</span><span class="sxs-lookup"><span data-stu-id="b6767-118">Unable to allocate enough memory for `ppRuntimes`.</span></span>  
  
 <span data-ttu-id="b6767-119">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="b6767-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="b6767-120">Otros errores.</span><span class="sxs-lookup"><span data-stu-id="b6767-120">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6767-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b6767-121">Remarks</span></span>  
 <span data-ttu-id="b6767-122">Para liberar la memoria asignada por este método, llame a la [Icoreclrdebugtarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="b6767-122">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6767-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6767-123">Requirements</span></span>  
 <span data-ttu-id="b6767-124">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6767-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6767-125">**Encabezado:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="b6767-125">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="b6767-126">**Biblioteca:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="b6767-126">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="b6767-127">**Versiones de .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="b6767-127">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6767-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6767-128">See Also</span></span>  
 [<span data-ttu-id="b6767-129">ICoreClrDebugTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b6767-129">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
