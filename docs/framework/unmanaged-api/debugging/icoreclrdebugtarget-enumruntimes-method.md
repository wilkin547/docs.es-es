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
ms.openlocfilehash: fc8269d4cc22ab53569edaa48c27b4a01970dcc7
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397185"
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a><span data-ttu-id="2a520-102">ICoreClrDebugTarget::EnumRuntimes (Método)</span><span class="sxs-lookup"><span data-stu-id="2a520-102">ICoreClrDebugTarget::EnumRuntimes Method</span></span>
<span data-ttu-id="2a520-103">Enumera los Common Language Runtime(CLR) del proceso especificado que se están ejecutando en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="2a520-103">Enumerates the common language runtimes (CLRs) in the specified process that is running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a520-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a520-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a520-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a520-105">Parameters</span></span>  
 `dwInternalProcessID`  
 <span data-ttu-id="2a520-106">[in] Identificador de proceso interno del proceso para el que desea enumerar los tiempos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2a520-106">[in] The internal process ID of the process for which you want to enumerate runtimes.</span></span> <span data-ttu-id="2a520-107">Será `m_dwInternalID` de la [coreclrdebugprocinfo (](coreclrdebugprocinfo-structure.md)correspondiente.</span><span class="sxs-lookup"><span data-stu-id="2a520-107">This will be `m_dwInternalID` from the corresponding [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md).</span></span>  
  
 `pcRuntimes`  
 <span data-ttu-id="2a520-108">[out] Número de tiempos de ejecución que se devuelve en `ppRuntimes`.</span><span class="sxs-lookup"><span data-stu-id="2a520-108">[out] The number of runtimes returned in `ppRuntimes`.</span></span> <span data-ttu-id="2a520-109">Este valor puede ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="2a520-109">This value can be 0 (zero).</span></span>  
  
 `ppRuntimes`  
 <span data-ttu-id="2a520-110">enuncia Matriz de estructuras [coreclrdebugruntimeinfo (](coreclrdebugruntimeinfo-structure.md) que representan los tiempos de ejecución cargados en el proceso de destino remoto.</span><span class="sxs-lookup"><span data-stu-id="2a520-110">[out] An array of [CoreClrDebugRuntimeInfo](coreclrdebugruntimeinfo-structure.md) structures that represent the runtimes loaded in the remote target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a520-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2a520-111">Return Value</span></span>  
 <span data-ttu-id="2a520-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2a520-112">S_OK</span></span>  
 <span data-ttu-id="2a520-113">Correcto.</span><span class="sxs-lookup"><span data-stu-id="2a520-113">Success.</span></span>  
  
 <span data-ttu-id="2a520-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2a520-114">S_FALSE</span></span>  
 <span data-ttu-id="2a520-115">`dwInternalProcessID` no coincide con ningún proceso que se esté ejecutando en el equipo, probablemente porque finalizó el proceso.</span><span class="sxs-lookup"><span data-stu-id="2a520-115">`dwInternalProcessID` does not match any process that is running on the computer, probably because the process was terminated.</span></span> <span data-ttu-id="2a520-116">`pcRuntimes` y `ppRuntimes` serán nulos.</span><span class="sxs-lookup"><span data-stu-id="2a520-116">`pcRuntimes` and `ppRuntimes` will be null.</span></span>  
  
 <span data-ttu-id="2a520-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2a520-117">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="2a520-118">No se puede asignar memoria suficiente para `ppRuntimes`.</span><span class="sxs-lookup"><span data-stu-id="2a520-118">Unable to allocate enough memory for `ppRuntimes`.</span></span>  
  
 <span data-ttu-id="2a520-119">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="2a520-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="2a520-120">Otros errores.</span><span class="sxs-lookup"><span data-stu-id="2a520-120">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a520-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2a520-121">Remarks</span></span>  
 <span data-ttu-id="2a520-122">Para liberar la memoria asignada por este método, llame al método [ICoreClrDebugTarget:: FreeMemory (](icoreclrdebugtarget-freememory-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2a520-122">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a520-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a520-123">Requirements</span></span>  
 <span data-ttu-id="2a520-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a520-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a520-125">**Encabezado:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="2a520-125">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="2a520-126">**Biblioteca:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="2a520-126">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="2a520-127">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="2a520-127">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a520-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a520-128">See also</span></span>

- [<span data-ttu-id="2a520-129">ICoreClrDebugTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2a520-129">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)
