---
description: 'Más información sobre: ICorProfilerInfo4:: Getobjectsize2 ((método)'
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
ms.openlocfilehash: 986c3d99501e21feec95dd3b6014f8d11d809704
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794530"
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a><span data-ttu-id="2749f-103">ICorProfilerInfo4::GetObjectSize2 (Método)</span><span class="sxs-lookup"><span data-stu-id="2749f-103">ICorProfilerInfo4::GetObjectSize2 Method</span></span>

<span data-ttu-id="2749f-104">Devuelve el tamaño de un objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="2749f-104">Returns the size of a specified object.</span></span> <span data-ttu-id="2749f-105">Reemplaza el método [ICorProfilerInfo:: GetObjectSize (](icorprofilerinfo-getobjectsize-method.md) por los tamaños de los objetos que son más grandes que los que se pueden expresar en `ULONG` .</span><span class="sxs-lookup"><span data-stu-id="2749f-105">Replaces the [ICorProfilerInfo::GetObjectSize](icorprofilerinfo-getobjectsize-method.md) method by reporting sizes of objects that are larger than what can be expressed in a `ULONG`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2749f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2749f-106">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2749f-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2749f-107">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="2749f-108">de IDENTIFICADOR del objeto.</span><span class="sxs-lookup"><span data-stu-id="2749f-108">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="2749f-109">enuncia Puntero al tamaño del objeto, en bytes.</span><span class="sxs-lookup"><span data-stu-id="2749f-109">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2749f-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2749f-110">Remarks</span></span>  

 <span data-ttu-id="2749f-111">A menudo, los distintos objetos de los mismos tipos tienen el mismo tamaño.</span><span class="sxs-lookup"><span data-stu-id="2749f-111">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="2749f-112">Sin embargo, algunos tipos, como matrices o cadenas, pueden tener un tamaño diferente para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="2749f-112">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2749f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2749f-113">Requirements</span></span>  

 <span data-ttu-id="2749f-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2749f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2749f-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2749f-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2749f-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2749f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2749f-117">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2749f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2749f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2749f-118">See also</span></span>

- [<span data-ttu-id="2749f-119">ICorProfilerInfo4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2749f-119">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
