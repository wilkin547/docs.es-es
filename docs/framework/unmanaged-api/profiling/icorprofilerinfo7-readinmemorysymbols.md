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
ms.openlocfilehash: 53c01d2db44f4d0adf1ba5b9cc225ab49581aa5d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868348"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="52308-102">ICorProfilerInfo7::ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="52308-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="52308-103">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="52308-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="52308-104">Lee bytes de una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="52308-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52308-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52308-105">Syntax</span></span>  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52308-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="52308-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="52308-107">de Identificador del módulo que contiene la secuencia en memoria.</span><span class="sxs-lookup"><span data-stu-id="52308-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="52308-108">de Desplazamiento en la secuencia en memoria donde se va a empezar a leer los bytes.</span><span class="sxs-lookup"><span data-stu-id="52308-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="52308-109">enuncia Puntero al búfer en el que se copiarán los datos.</span><span class="sxs-lookup"><span data-stu-id="52308-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="52308-110">El búfer debe tener `countSymbolBytes` de espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="52308-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="52308-111">de Número de bytes que se van a copiar.</span><span class="sxs-lookup"><span data-stu-id="52308-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="52308-112">enuncia Cuando el método vuelve, contiene el número real de bytes leídos.</span><span class="sxs-lookup"><span data-stu-id="52308-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52308-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="52308-113">Return Value</span></span>  
 <span data-ttu-id="52308-114">`S_OK`, si se leyó un número distinto de cero de bytes.</span><span class="sxs-lookup"><span data-stu-id="52308-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="52308-115">`CORPROF_E_MODULE_IS_DYNAMIC`, si el módulo se creó con <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="52308-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52308-116">Notas</span><span class="sxs-lookup"><span data-stu-id="52308-116">Remarks</span></span>  
 <span data-ttu-id="52308-117">El método `ReadInMemorySymbols` intenta leer `countSymbolBytes` de datos a partir de la posición de desplazamiento `symbolsReadOffset` dentro de la secuencia en memoria.</span><span class="sxs-lookup"><span data-stu-id="52308-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="52308-118">Los datos se copian en `pSymbolBytes`, lo que se espera que tenga `countSymbolBytes` de espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="52308-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="52308-119">`pCountSymbolsBytesRead` contiene el número real de bytes leídos, que puede ser menor que `countSymbolBytes` si se alcanza el final de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="52308-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52308-120">La implementación actual no admite Reflection. Emit.</span><span class="sxs-lookup"><span data-stu-id="52308-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="52308-121">Si el módulo se creó con Reflection. Emit, el método devuelve `CORPROF_E_MODULE_IS_DYNAMIC`.</span><span class="sxs-lookup"><span data-stu-id="52308-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52308-122">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="52308-122">Requirements</span></span>  
 <span data-ttu-id="52308-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52308-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52308-124">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="52308-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="52308-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52308-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52308-126">**.NET Framework versiones:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52308-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52308-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="52308-127">See also</span></span>

- [<span data-ttu-id="52308-128">ICorProfilerInfo7 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="52308-128">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
