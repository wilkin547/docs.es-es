---
description: 'Más información acerca de: ICorProfilerInfo2:: GetBoxClassLayout ((método)'
title: ICorProfilerInfo2::GetBoxClassLayout (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetBoxClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type:
- apiref
ms.openlocfilehash: 0bc9ccc80da8bcc89cfe73eaa240310c01e6ca8f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760525"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="45ea5-103">ICorProfilerInfo2::GetBoxClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="45ea5-103">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>

<span data-ttu-id="45ea5-104">Obtiene información sobre dónde se encuentra el tipo de valor especificado cuando se le aplica la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="45ea5-104">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45ea5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45ea5-105">Syntax</span></span>  
  
```cpp  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45ea5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="45ea5-106">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="45ea5-107">de IDENTIFICADOR de la clase que describe el tipo de valor al que se aplica la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="45ea5-107">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="45ea5-108">enuncia Entero que es el desplazamiento con respecto al puntero de identificador de objeto con conversión boxing del tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="45ea5-108">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45ea5-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="45ea5-109">Remarks</span></span>  

 <span data-ttu-id="45ea5-110">El `pBufferOffset` valor es la ubicación del tipo de valor dentro de un cuadro.</span><span class="sxs-lookup"><span data-stu-id="45ea5-110">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="45ea5-111">Una vez `pBufferOffset` que se aplica a un objeto con conversión boxing, el diseño de clase del tipo de valor se puede utilizar para interpretar el valor del objeto.</span><span class="sxs-lookup"><span data-stu-id="45ea5-111">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45ea5-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45ea5-112">Requirements</span></span>  

 <span data-ttu-id="45ea5-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45ea5-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45ea5-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="45ea5-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="45ea5-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45ea5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45ea5-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45ea5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45ea5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="45ea5-117">See also</span></span>

- [<span data-ttu-id="45ea5-118">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="45ea5-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="45ea5-119">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="45ea5-119">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
