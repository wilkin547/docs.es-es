---
title: ICorProfilerInfo7::ReadInMemorySymbols
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type: COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9ada9f629c3a3c3d8b7c32ebc180c4788b6f6d3f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="7e235-102">ICorProfilerInfo7::ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="7e235-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="7e235-103">[compatible con la versión [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] y posteriores]</span><span class="sxs-lookup"><span data-stu-id="7e235-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="7e235-104">Lee los bytes de una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="7e235-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e235-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e235-105">Syntax</span></span>  
  
```  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e235-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7e235-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="7e235-107">[in] El identificador del módulo que contiene la secuencia en memoria.</span><span class="sxs-lookup"><span data-stu-id="7e235-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="7e235-108">[in] El desplazamiento dentro de la secuencia en memoria en el que se va a comenzar la lectura de bytes.</span><span class="sxs-lookup"><span data-stu-id="7e235-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="7e235-109">[out] Un puntero al búfer al que se copiarán los datos.</span><span class="sxs-lookup"><span data-stu-id="7e235-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="7e235-110">Debe tener el búfer `countSymbolBytes` de espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="7e235-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="7e235-111">[in] El número de bytes que se va a copiar.</span><span class="sxs-lookup"><span data-stu-id="7e235-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="7e235-112">[out] Cuando el método vuelve, contiene el número real de bytes leídos.</span><span class="sxs-lookup"><span data-stu-id="7e235-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e235-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7e235-113">Return Value</span></span>  
 <span data-ttu-id="7e235-114">`S_OK`, si un número distinto de cero de bytes leído.</span><span class="sxs-lookup"><span data-stu-id="7e235-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="7e235-115">`CORPROF_E_MODULE_IS_DYNAMIC`, si se creó el módulo mediante <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="7e235-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e235-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7e235-116">Remarks</span></span>  
 <span data-ttu-id="7e235-117">El `ReadInMemorySymbols` método intenta leer `countSymbolBytes` de datos a partir del desplazamiento `symbolsReadOffset` dentro de la secuencia en memoria.</span><span class="sxs-lookup"><span data-stu-id="7e235-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="7e235-118">Los datos se copian en `pSymbolBytes`, lo que se esperaba que `countSymbolBytes` de espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="7e235-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="7e235-119">`pCountSymbolsBytesRead`contiene el número real de bytes leídos, lo que puede ser menor que `countSymbolBytes` si se alcanza el final de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="7e235-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e235-120">La implementación actual no admite Reflection.Emit.</span><span class="sxs-lookup"><span data-stu-id="7e235-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="7e235-121">Si se creó el módulo mediante Reflection.Emit, el método devuelve `CORPROF_E_MODULE_IS_DYNAMIC`.</span><span class="sxs-lookup"><span data-stu-id="7e235-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e235-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e235-122">Requirements</span></span>  
 <span data-ttu-id="7e235-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e235-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e235-124">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7e235-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7e235-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e235-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e235-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e235-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e235-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e235-127">See Also</span></span>  
 [<span data-ttu-id="7e235-128">Interfaz ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="7e235-128">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
