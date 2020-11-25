---
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
ms.openlocfilehash: ff39a688132112e88438bc192d7c1ab61f169400
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727164"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="6901c-102">ICorProfilerInfo2::GetBoxClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="6901c-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>

<span data-ttu-id="6901c-103">Obtiene información sobre dónde se encuentra el tipo de valor especificado cuando se le aplica la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="6901c-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6901c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6901c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6901c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6901c-105">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="6901c-106">de IDENTIFICADOR de la clase que describe el tipo de valor al que se aplica la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="6901c-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="6901c-107">enuncia Entero que es el desplazamiento con respecto al puntero de identificador de objeto con conversión boxing del tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="6901c-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6901c-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6901c-108">Remarks</span></span>  

 <span data-ttu-id="6901c-109">El `pBufferOffset` valor es la ubicación del tipo de valor dentro de un cuadro.</span><span class="sxs-lookup"><span data-stu-id="6901c-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="6901c-110">Una vez `pBufferOffset` que se aplica a un objeto con conversión boxing, el diseño de clase del tipo de valor se puede utilizar para interpretar el valor del objeto.</span><span class="sxs-lookup"><span data-stu-id="6901c-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6901c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6901c-111">Requirements</span></span>  

 <span data-ttu-id="6901c-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6901c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6901c-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6901c-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6901c-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6901c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6901c-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6901c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6901c-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6901c-116">See also</span></span>

- [<span data-ttu-id="6901c-117">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6901c-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="6901c-118">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6901c-118">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
