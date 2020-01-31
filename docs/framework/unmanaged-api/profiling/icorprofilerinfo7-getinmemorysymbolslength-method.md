---
title: 'ICorProfilerInfo7:: GetInMemorySymbolsLength (método)'
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
ms.openlocfilehash: a675cc301d2dd32f87e3864a3123e2044761ef91
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868361"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="ad58d-102">ICorProfilerInfo7:: GetInMemorySymbolsLength (método)</span><span class="sxs-lookup"><span data-stu-id="ad58d-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>
<span data-ttu-id="ad58d-103">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="ad58d-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="ad58d-104">Devuelve la longitud de una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="ad58d-104">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad58d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad58d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad58d-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="ad58d-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="ad58d-107">de Identificador del módulo que contiene la secuencia en memoria.</span><span class="sxs-lookup"><span data-stu-id="ad58d-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="ad58d-108">pCountSymbolBytes</span><span class="sxs-lookup"><span data-stu-id="ad58d-108">pCountSymbolBytes</span></span>  
 <span data-ttu-id="ad58d-109">enuncia Un puntero a un valor de `DWORD` que, cuando el método vuelve, contiene la longitud de la secuencia en bytes.</span><span class="sxs-lookup"><span data-stu-id="ad58d-109">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad58d-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ad58d-110">Return Value</span></span>  
 <span data-ttu-id="ad58d-111">El método devuelve `S_OK` si se puede determinar la longitud de la secuencia de memoria, incluso si es cero (0).</span><span class="sxs-lookup"><span data-stu-id="ad58d-111">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="ad58d-112">El método devuelve `CORPROF_E_MODULE_IS_DYNAMIC` si el método se creó utilizando <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ad58d-112">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad58d-113">Notas</span><span class="sxs-lookup"><span data-stu-id="ad58d-113">Remarks</span></span>  
 <span data-ttu-id="ad58d-114">Si el módulo tiene símbolos en memoria, la longitud de la secuencia se coloca en `pCountSymbolBytes`.</span><span class="sxs-lookup"><span data-stu-id="ad58d-114">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="ad58d-115">Si el módulo no tiene símbolos en memoria, `*pCountSymbolBytes = 0`.</span><span class="sxs-lookup"><span data-stu-id="ad58d-115">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ad58d-116">La implementación actual no admite Reflection. Emit.</span><span class="sxs-lookup"><span data-stu-id="ad58d-116">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="ad58d-117">Si el módulo se creó con Reflection. Emit, el método devuelve `CORPROF_E_MODULE_IS_DYNAMIC`.</span><span class="sxs-lookup"><span data-stu-id="ad58d-117">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad58d-118">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="ad58d-118">Requirements</span></span>  
 <span data-ttu-id="ad58d-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad58d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad58d-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ad58d-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ad58d-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad58d-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad58d-122">**.NET Framework versiones:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad58d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad58d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad58d-123">See also</span></span>

- [<span data-ttu-id="ad58d-124">ICorProfilerInfo7 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad58d-124">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
