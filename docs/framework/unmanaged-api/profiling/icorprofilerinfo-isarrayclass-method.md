---
description: 'Más información acerca de: ICorProfilerInfo:: IsArrayClass ((método)'
title: ICorProfilerInfo::IsArrayClass (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.IsArrayClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type:
- apiref
ms.openlocfilehash: 1eee0b834c63c3cfe15bd08776214ca8b2ba3f69
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687238"
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="5edb0-103">ICorProfilerInfo::IsArrayClass (Método)</span><span class="sxs-lookup"><span data-stu-id="5edb0-103">ICorProfilerInfo::IsArrayClass Method</span></span>

<span data-ttu-id="5edb0-104">Determina si la clase especificada es una clase de matriz.</span><span class="sxs-lookup"><span data-stu-id="5edb0-104">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5edb0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5edb0-105">Syntax</span></span>  
  
```cpp  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5edb0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5edb0-106">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="5edb0-107">de IDENTIFICADOR de la clase que se va a examinar.</span><span class="sxs-lookup"><span data-stu-id="5edb0-107">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="5edb0-108">enuncia Un puntero a un valor de la enumeración CorElementType que indica el tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="5edb0-108">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="5edb0-109">enuncia Puntero al identificador de clase de los elementos de la matriz, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="5edb0-109">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="5edb0-110">enuncia Un puntero a un entero que indica el rango (es decir, el número de dimensiones) de la matriz.</span><span class="sxs-lookup"><span data-stu-id="5edb0-110">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5edb0-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5edb0-111">Remarks</span></span>  

 <span data-ttu-id="5edb0-112">Si la clase especificada es una clase de matriz, el `IsArrayClass` método devuelve un S_OK HRESULT y valores para cualquier parámetro de salida que no sea NULL.</span><span class="sxs-lookup"><span data-stu-id="5edb0-112">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="5edb0-113">De lo contrario, devuelve S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="5edb0-113">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5edb0-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5edb0-114">Requirements</span></span>  

 <span data-ttu-id="5edb0-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5edb0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5edb0-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5edb0-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5edb0-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5edb0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5edb0-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5edb0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5edb0-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5edb0-119">See also</span></span>

- [<span data-ttu-id="5edb0-120">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5edb0-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
