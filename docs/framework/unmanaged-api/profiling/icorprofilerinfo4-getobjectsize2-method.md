---
title: ICorProfilerInfo4::GetObjectSize2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetObjectSize2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetObjectSize2
helpviewer_keywords:
- GetObjectSize2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetObjectSize2 method [.NET Framework profiling]
ms.assetid: 4a3e43ed-3ee3-4395-ab14-f78b903be13e
topic_type:
- apiref
ms.openlocfilehash: b605419a291f7bee76ecad7e07be9a7a989f9fe9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496014"
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a><span data-ttu-id="ef8c1-102">ICorProfilerInfo4::GetObjectSize2 (Método)</span><span class="sxs-lookup"><span data-stu-id="ef8c1-102">ICorProfilerInfo4::GetObjectSize2 Method</span></span>
<span data-ttu-id="ef8c1-103">Devuelve el tamaño de un objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="ef8c1-103">Returns the size of a specified object.</span></span> <span data-ttu-id="ef8c1-104">Reemplaza el método [ICorProfilerInfo:: GetObjectSize (](icorprofilerinfo-getobjectsize-method.md) por los tamaños de los objetos que son más grandes que los que se pueden expresar en `ULONG` .</span><span class="sxs-lookup"><span data-stu-id="ef8c1-104">Replaces the [ICorProfilerInfo::GetObjectSize](icorprofilerinfo-getobjectsize-method.md) method by reporting sizes of objects that are larger than what can be expressed in a `ULONG`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef8c1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef8c1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef8c1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef8c1-106">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="ef8c1-107">de IDENTIFICADOR del objeto.</span><span class="sxs-lookup"><span data-stu-id="ef8c1-107">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="ef8c1-108">enuncia Puntero al tamaño del objeto, en bytes.</span><span class="sxs-lookup"><span data-stu-id="ef8c1-108">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef8c1-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ef8c1-109">Remarks</span></span>  
 <span data-ttu-id="ef8c1-110">A menudo, los distintos objetos de los mismos tipos tienen el mismo tamaño.</span><span class="sxs-lookup"><span data-stu-id="ef8c1-110">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="ef8c1-111">Sin embargo, algunos tipos, como matrices o cadenas, pueden tener un tamaño diferente para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="ef8c1-111">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef8c1-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef8c1-112">Requirements</span></span>  
 <span data-ttu-id="ef8c1-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef8c1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef8c1-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ef8c1-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ef8c1-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef8c1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef8c1-116">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef8c1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef8c1-117">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="ef8c1-117">See also</span></span>

- [<span data-ttu-id="ef8c1-118">ICorProfilerInfo4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef8c1-118">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
