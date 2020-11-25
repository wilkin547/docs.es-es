---
title: 'ICorProfilerInfo7:: ReadInMemorySymbols'
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
ms.openlocfilehash: 6917900b7494550992dfa82f45ed0140f95e68cb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733625"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="87050-102">ICorProfilerInfo7:: ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="87050-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>

<span data-ttu-id="87050-103">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="87050-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="87050-104">Lee bytes de una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="87050-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87050-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87050-105">Syntax</span></span>  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87050-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="87050-106">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="87050-107">de Identificador del módulo que contiene la secuencia en memoria.</span><span class="sxs-lookup"><span data-stu-id="87050-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="87050-108">de Desplazamiento en la secuencia en memoria donde se va a empezar a leer los bytes.</span><span class="sxs-lookup"><span data-stu-id="87050-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="87050-109">enuncia Puntero al búfer en el que se copiarán los datos.</span><span class="sxs-lookup"><span data-stu-id="87050-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="87050-110">El búfer debe tener `countSymbolBytes` espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="87050-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="87050-111">de Número de bytes que se van a copiar.</span><span class="sxs-lookup"><span data-stu-id="87050-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="87050-112">enuncia Cuando el método vuelve, contiene el número real de bytes leídos.</span><span class="sxs-lookup"><span data-stu-id="87050-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87050-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="87050-113">Return Value</span></span>  

 <span data-ttu-id="87050-114">`S_OK`es si se leyó un número distinto de cero de bytes.</span><span class="sxs-lookup"><span data-stu-id="87050-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="87050-115">`CORPROF_E_MODULE_IS_DYNAMIC`, si el módulo se ha creado con <xref:System.Reflection.Emit> .</span><span class="sxs-lookup"><span data-stu-id="87050-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87050-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="87050-116">Remarks</span></span>  

 <span data-ttu-id="87050-117">El `ReadInMemorySymbols` método intenta leer los `countSymbolBytes` datos a partir del desplazamiento en      `symbolsReadOffset` la secuencia en memoria.</span><span class="sxs-lookup"><span data-stu-id="87050-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="87050-118">Los datos se copian en `pSymbolBytes` , lo que se espera que tenga `countSymbolBytes` espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="87050-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="87050-119">`pCountSymbolsBytesRead` contiene el número real de bytes leídos, que puede ser menor que `countSymbolBytes` si se alcanza el final de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="87050-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="87050-120">La implementación actual no admite Reflection. Emit.</span><span class="sxs-lookup"><span data-stu-id="87050-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="87050-121">Si el módulo se creó con Reflection. Emit, el método devuelve `CORPROF_E_MODULE_IS_DYNAMIC` .</span><span class="sxs-lookup"><span data-stu-id="87050-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87050-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87050-122">Requirements</span></span>  

 <span data-ttu-id="87050-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87050-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87050-124">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="87050-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="87050-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87050-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87050-126">**.NET Framework versiones:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87050-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87050-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="87050-127">See also</span></span>

- [<span data-ttu-id="87050-128">Interfaz ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="87050-128">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
