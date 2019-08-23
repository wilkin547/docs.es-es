---
title: ICorProfilerInfo7::ReadInMemorySymbols
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type:
- COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95b463b23c230d620d746e48da49d75238ef2cb7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955372"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="d8abb-102">ICorProfilerInfo7::ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="d8abb-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="d8abb-103">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="d8abb-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="d8abb-104">Lee bytes de una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="d8abb-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8abb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8abb-105">Syntax</span></span>  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8abb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d8abb-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="d8abb-107">de Identificador del módulo que contiene la secuencia en memoria.</span><span class="sxs-lookup"><span data-stu-id="d8abb-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="d8abb-108">de Desplazamiento en la secuencia en memoria donde se va a empezar a leer los bytes.</span><span class="sxs-lookup"><span data-stu-id="d8abb-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="d8abb-109">enuncia Puntero al búfer en el que se copiarán los datos.</span><span class="sxs-lookup"><span data-stu-id="d8abb-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="d8abb-110">El búfer debe tener `countSymbolBytes` espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="d8abb-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="d8abb-111">de Número de bytes que se van a copiar.</span><span class="sxs-lookup"><span data-stu-id="d8abb-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="d8abb-112">enuncia Cuando el método vuelve, contiene el número real de bytes leídos.</span><span class="sxs-lookup"><span data-stu-id="d8abb-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8abb-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d8abb-113">Return Value</span></span>  
 <span data-ttu-id="d8abb-114">`S_OK`es si se leyó un número distinto de cero de bytes.</span><span class="sxs-lookup"><span data-stu-id="d8abb-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="d8abb-115">`CORPROF_E_MODULE_IS_DYNAMIC`, si el módulo se ha creado <xref:System.Reflection.Emit>con.</span><span class="sxs-lookup"><span data-stu-id="d8abb-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8abb-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d8abb-116">Remarks</span></span>  
 <span data-ttu-id="d8abb-117">El `ReadInMemorySymbols` método intenta leer `countSymbolBytes` los datos a partir del desplazamiento `symbolsReadOffset` en la secuencia en memoria.</span><span class="sxs-lookup"><span data-stu-id="d8abb-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="d8abb-118">Los datos se copian `pSymbolBytes`en, lo que se espera `countSymbolBytes` que tenga espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="d8abb-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="d8abb-119">`pCountSymbolsBytesRead`contiene el número real de bytes leídos, que puede ser menor `countSymbolBytes` que si se alcanza el final de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="d8abb-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d8abb-120">La implementación actual no admite Reflection. Emit.</span><span class="sxs-lookup"><span data-stu-id="d8abb-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="d8abb-121">Si el módulo se creó con Reflection. Emit, el método devuelve `CORPROF_E_MODULE_IS_DYNAMIC`.</span><span class="sxs-lookup"><span data-stu-id="d8abb-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8abb-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8abb-122">Requirements</span></span>  
 <span data-ttu-id="d8abb-123">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8abb-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8abb-124">**Encabezado**: Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="d8abb-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d8abb-125">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8abb-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8abb-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8abb-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8abb-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8abb-127">See also</span></span>

- [<span data-ttu-id="d8abb-128">ICorProfilerInfo7 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d8abb-128">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
