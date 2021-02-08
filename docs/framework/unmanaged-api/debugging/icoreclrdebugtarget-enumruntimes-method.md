---
description: 'Más información sobre: ICoreClrDebugTarget:: Enumruntimes ((método)'
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
ms.openlocfilehash: 675747106b2acec2e8be3fcdf15831958bea7c7c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794629"
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a><span data-ttu-id="8f7a0-103">ICoreClrDebugTarget::EnumRuntimes (Método)</span><span class="sxs-lookup"><span data-stu-id="8f7a0-103">ICoreClrDebugTarget::EnumRuntimes Method</span></span>

<span data-ttu-id="8f7a0-104">Enumera los Common Language Runtime(CLR) del proceso especificado que se están ejecutando en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-104">Enumerates the common language runtimes (CLRs) in the specified process that is running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f7a0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f7a0-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f7a0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8f7a0-106">Parameters</span></span>  

 `dwInternalProcessID`  
 <span data-ttu-id="8f7a0-107">[in] Identificador de proceso interno del proceso para el que desea enumerar los tiempos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-107">[in] The internal process ID of the process for which you want to enumerate runtimes.</span></span> <span data-ttu-id="8f7a0-108">Será `m_dwInternalID` de la [coreclrdebugprocinfo (](coreclrdebugprocinfo-structure.md)correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-108">This will be `m_dwInternalID` from the corresponding [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md).</span></span>  
  
 `pcRuntimes`  
 <span data-ttu-id="8f7a0-109">[out] Número de tiempos de ejecución que se devuelve en `ppRuntimes`.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-109">[out] The number of runtimes returned in `ppRuntimes`.</span></span> <span data-ttu-id="8f7a0-110">Este valor puede ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="8f7a0-110">This value can be 0 (zero).</span></span>  
  
 `ppRuntimes`  
 <span data-ttu-id="8f7a0-111">enuncia Matriz de estructuras [coreclrdebugruntimeinfo (](coreclrdebugruntimeinfo-structure.md) que representan los tiempos de ejecución cargados en el proceso de destino remoto.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-111">[out] An array of [CoreClrDebugRuntimeInfo](coreclrdebugruntimeinfo-structure.md) structures that represent the runtimes loaded in the remote target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f7a0-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8f7a0-112">Return Value</span></span>  

 <span data-ttu-id="8f7a0-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="8f7a0-113">S_OK</span></span>  
 <span data-ttu-id="8f7a0-114">Correcto.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-114">Success.</span></span>  
  
 <span data-ttu-id="8f7a0-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="8f7a0-115">S_FALSE</span></span>  
 <span data-ttu-id="8f7a0-116">`dwInternalProcessID` no coincide con ningún proceso que se esté ejecutando en el equipo, probablemente porque finalizó el proceso.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-116">`dwInternalProcessID` does not match any process that is running on the computer, probably because the process was terminated.</span></span> <span data-ttu-id="8f7a0-117">`pcRuntimes` y `ppRuntimes` serán nulos.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-117">`pcRuntimes` and `ppRuntimes` will be null.</span></span>  
  
 <span data-ttu-id="8f7a0-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8f7a0-118">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="8f7a0-119">No se puede asignar memoria suficiente para `ppRuntimes`.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-119">Unable to allocate enough memory for `ppRuntimes`.</span></span>  
  
 <span data-ttu-id="8f7a0-120">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="8f7a0-120">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="8f7a0-121">Otros errores.</span><span class="sxs-lookup"><span data-stu-id="8f7a0-121">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f7a0-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8f7a0-122">Remarks</span></span>  

 <span data-ttu-id="8f7a0-123">Para liberar la memoria asignada por este método, llame al método [ICoreClrDebugTarget:: FreeMemory (](icoreclrdebugtarget-freememory-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8f7a0-123">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f7a0-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f7a0-124">Requirements</span></span>  

 <span data-ttu-id="8f7a0-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f7a0-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f7a0-126">**Encabezado:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="8f7a0-126">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="8f7a0-127">**Biblioteca:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="8f7a0-127">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="8f7a0-128">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="8f7a0-128">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f7a0-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f7a0-129">See also</span></span>

- [<span data-ttu-id="8f7a0-130">ICoreClrDebugTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8f7a0-130">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)
