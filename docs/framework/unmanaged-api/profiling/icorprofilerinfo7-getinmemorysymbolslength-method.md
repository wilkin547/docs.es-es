---
description: 'Más información sobre: ICorProfilerInfo7:: GetInMemorySymbolsLength (método)'
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
ms.openlocfilehash: 5d96b17e8abbd023f2d050eff3f121a871a94754
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737121"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="0c267-103">ICorProfilerInfo7:: GetInMemorySymbolsLength (método)</span><span class="sxs-lookup"><span data-stu-id="0c267-103">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>

<span data-ttu-id="0c267-104">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="0c267-104">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="0c267-105">Devuelve la longitud de una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="0c267-105">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c267-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c267-106">Syntax</span></span>  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c267-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0c267-107">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="0c267-108">de Identificador del módulo que contiene la secuencia en memoria.</span><span class="sxs-lookup"><span data-stu-id="0c267-108">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="0c267-109">pCountSymbolBytes</span><span class="sxs-lookup"><span data-stu-id="0c267-109">pCountSymbolBytes</span></span>  
 <span data-ttu-id="0c267-110">enuncia Un puntero a un `DWORD` valor que, cuando el método vuelve, contiene la longitud de la secuencia en bytes.</span><span class="sxs-lookup"><span data-stu-id="0c267-110">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c267-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0c267-111">Return Value</span></span>  

 <span data-ttu-id="0c267-112">El método devuelve `S_OK` si se puede determinar la longitud de la secuencia de memoria, incluso si es cero (0).</span><span class="sxs-lookup"><span data-stu-id="0c267-112">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="0c267-113">El método devuelve `CORPROF_E_MODULE_IS_DYNAMIC` si el método se ha creado mediante <xref:System.Reflection.Emit?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="0c267-113">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c267-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0c267-114">Remarks</span></span>  

 <span data-ttu-id="0c267-115">Si el módulo tiene símbolos en memoria, la longitud de la secuencia se coloca en `pCountSymbolBytes` .</span><span class="sxs-lookup"><span data-stu-id="0c267-115">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="0c267-116">Si el módulo no tiene símbolos en memoria, `*pCountSymbolBytes = 0` .</span><span class="sxs-lookup"><span data-stu-id="0c267-116">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c267-117">La implementación actual no admite Reflection. Emit.</span><span class="sxs-lookup"><span data-stu-id="0c267-117">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="0c267-118">Si el módulo se creó con Reflection. Emit, el método devuelve `CORPROF_E_MODULE_IS_DYNAMIC` .</span><span class="sxs-lookup"><span data-stu-id="0c267-118">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c267-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c267-119">Requirements</span></span>  

 <span data-ttu-id="0c267-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c267-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c267-121">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0c267-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0c267-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c267-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c267-123">**.NET Framework versiones:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c267-123">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c267-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c267-124">See also</span></span>

- [<span data-ttu-id="0c267-125">Interfaz ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="0c267-125">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
