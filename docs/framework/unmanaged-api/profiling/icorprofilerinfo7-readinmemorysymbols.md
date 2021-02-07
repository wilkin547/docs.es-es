---
description: 'Más información acerca de: ICorProfilerInfo7:: ReadInMemorySymbols'
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
ms.openlocfilehash: 7f1a88d823e7cdfcc89aa140681f61cfbe3f63ec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736991"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="c639e-103">ICorProfilerInfo7:: ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="c639e-103">ICorProfilerInfo7::ReadInMemorySymbols</span></span>

<span data-ttu-id="c639e-104">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="c639e-104">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="c639e-105">Lee bytes de una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="c639e-105">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c639e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c639e-106">Syntax</span></span>  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c639e-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c639e-107">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="c639e-108">de Identificador del módulo que contiene la secuencia en memoria.</span><span class="sxs-lookup"><span data-stu-id="c639e-108">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="c639e-109">de Desplazamiento en la secuencia en memoria donde se va a empezar a leer los bytes.</span><span class="sxs-lookup"><span data-stu-id="c639e-109">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="c639e-110">enuncia Puntero al búfer en el que se copiarán los datos.</span><span class="sxs-lookup"><span data-stu-id="c639e-110">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="c639e-111">El búfer debe tener `countSymbolBytes` espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="c639e-111">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="c639e-112">de Número de bytes que se van a copiar.</span><span class="sxs-lookup"><span data-stu-id="c639e-112">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="c639e-113">enuncia Cuando el método vuelve, contiene el número real de bytes leídos.</span><span class="sxs-lookup"><span data-stu-id="c639e-113">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c639e-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c639e-114">Return Value</span></span>  

 <span data-ttu-id="c639e-115">`S_OK`es si se leyó un número distinto de cero de bytes.</span><span class="sxs-lookup"><span data-stu-id="c639e-115">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="c639e-116">`CORPROF_E_MODULE_IS_DYNAMIC`, si el módulo se ha creado con <xref:System.Reflection.Emit> .</span><span class="sxs-lookup"><span data-stu-id="c639e-116">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c639e-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c639e-117">Remarks</span></span>  

 <span data-ttu-id="c639e-118">El `ReadInMemorySymbols` método intenta leer los `countSymbolBytes` datos a partir del desplazamiento en      `symbolsReadOffset` la secuencia en memoria.</span><span class="sxs-lookup"><span data-stu-id="c639e-118">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="c639e-119">Los datos se copian en `pSymbolBytes` , lo que se espera que tenga `countSymbolBytes` espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="c639e-119">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="c639e-120">`pCountSymbolsBytesRead` contiene el número real de bytes leídos, que puede ser menor que `countSymbolBytes` si se alcanza el final de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="c639e-120">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c639e-121">La implementación actual no admite Reflection. Emit.</span><span class="sxs-lookup"><span data-stu-id="c639e-121">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="c639e-122">Si el módulo se creó con Reflection. Emit, el método devuelve `CORPROF_E_MODULE_IS_DYNAMIC` .</span><span class="sxs-lookup"><span data-stu-id="c639e-122">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c639e-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c639e-123">Requirements</span></span>  

 <span data-ttu-id="c639e-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c639e-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c639e-125">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c639e-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c639e-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c639e-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c639e-127">**.NET Framework versiones:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c639e-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c639e-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="c639e-128">See also</span></span>

- [<span data-ttu-id="c639e-129">Interfaz ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="c639e-129">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
