---
description: 'Más información sobre: ICoreClrDebugTarget:: EnumProcesses (método)'
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
ms.openlocfilehash: 73dc8a2b00f7a57879855158e6b871117d015f3c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738044"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a><span data-ttu-id="2381e-103">ICoreClrDebugTarget::EnumProcesses (Método)</span><span class="sxs-lookup"><span data-stu-id="2381e-103">ICoreClrDebugTarget::EnumProcesses Method</span></span>

<span data-ttu-id="2381e-104">Enumera los procesos que se ejecutan en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="2381e-104">Enumerates the processes that are running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2381e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2381e-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2381e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2381e-106">Parameters</span></span>  

 `pcProcs`  
 <span data-ttu-id="2381e-107">[out] Número de procesos que se devuelve en `ppProcs`.</span><span class="sxs-lookup"><span data-stu-id="2381e-107">[out] The number of processes returned in `ppProcs`.</span></span> <span data-ttu-id="2381e-108">Este valor puede ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="2381e-108">This value can be 0 (zero).</span></span>  
  
 `ppProcs`  
 <span data-ttu-id="2381e-109">enuncia Matriz de estructuras [coreclrdebugprocinfo (](coreclrdebugprocinfo-structure.md) que representan los procesos que se ejecutan en el equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="2381e-109">[out] An array of [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md) structures that represent the processes running on the remote computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2381e-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2381e-110">Return Value</span></span>  

 <span data-ttu-id="2381e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2381e-111">S_OK</span></span>  
 <span data-ttu-id="2381e-112">Correcto.</span><span class="sxs-lookup"><span data-stu-id="2381e-112">Success.</span></span>  
  
 <span data-ttu-id="2381e-113">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2381e-113">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="2381e-114">No se puede asignar memoria suficiente para `ppProcs`.</span><span class="sxs-lookup"><span data-stu-id="2381e-114">Unable to allocate enough memory for `ppProcs`.</span></span>  
  
 <span data-ttu-id="2381e-115">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="2381e-115">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="2381e-116">Otros errores.</span><span class="sxs-lookup"><span data-stu-id="2381e-116">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2381e-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2381e-117">Remarks</span></span>  

 <span data-ttu-id="2381e-118">Para liberar la memoria asignada por este método, llame al método [ICoreClrDebugTarget:: FreeMemory (](icoreclrdebugtarget-freememory-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2381e-118">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2381e-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2381e-119">Requirements</span></span>  

 <span data-ttu-id="2381e-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2381e-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2381e-121">**Encabezado:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="2381e-121">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="2381e-122">**Biblioteca:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="2381e-122">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="2381e-123">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="2381e-123">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2381e-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="2381e-124">See also</span></span>

- [<span data-ttu-id="2381e-125">ICoreClrDebugTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2381e-125">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)
