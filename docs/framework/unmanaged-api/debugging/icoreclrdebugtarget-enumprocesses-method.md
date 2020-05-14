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
ms.openlocfilehash: 0c1b18f24fd30b5f6d5e85633fc0c25839aba6df
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396415"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a><span data-ttu-id="4f659-102">ICoreClrDebugTarget::EnumProcesses (Método)</span><span class="sxs-lookup"><span data-stu-id="4f659-102">ICoreClrDebugTarget::EnumProcesses Method</span></span>
<span data-ttu-id="4f659-103">Enumera los procesos que se ejecutan en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="4f659-103">Enumerates the processes that are running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f659-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f659-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f659-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4f659-105">Parameters</span></span>  
 `pcProcs`  
 <span data-ttu-id="4f659-106">[out] Número de procesos que se devuelve en `ppProcs`.</span><span class="sxs-lookup"><span data-stu-id="4f659-106">[out] The number of processes returned in `ppProcs`.</span></span> <span data-ttu-id="4f659-107">Este valor puede ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="4f659-107">This value can be 0 (zero).</span></span>  
  
 `ppProcs`  
 <span data-ttu-id="4f659-108">enuncia Matriz de estructuras [coreclrdebugprocinfo (](coreclrdebugprocinfo-structure.md) que representan los procesos que se ejecutan en el equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="4f659-108">[out] An array of [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md) structures that represent the processes running on the remote computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f659-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4f659-109">Return Value</span></span>  
 <span data-ttu-id="4f659-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4f659-110">S_OK</span></span>  
 <span data-ttu-id="4f659-111">Correcto.</span><span class="sxs-lookup"><span data-stu-id="4f659-111">Success.</span></span>  
  
 <span data-ttu-id="4f659-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4f659-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="4f659-113">No se puede asignar memoria suficiente para `ppProcs`.</span><span class="sxs-lookup"><span data-stu-id="4f659-113">Unable to allocate enough memory for `ppProcs`.</span></span>  
  
 <span data-ttu-id="4f659-114">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="4f659-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="4f659-115">Otros errores.</span><span class="sxs-lookup"><span data-stu-id="4f659-115">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f659-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4f659-116">Remarks</span></span>  
 <span data-ttu-id="4f659-117">Para liberar la memoria asignada por este método, llame al método [ICoreClrDebugTarget:: FreeMemory (](icoreclrdebugtarget-freememory-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4f659-117">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f659-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f659-118">Requirements</span></span>  
 <span data-ttu-id="4f659-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f659-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f659-120">**Encabezado:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="4f659-120">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="4f659-121">**Biblioteca:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="4f659-121">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="4f659-122">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="4f659-122">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f659-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f659-123">See also</span></span>

- [<span data-ttu-id="4f659-124">ICoreClrDebugTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4f659-124">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)
