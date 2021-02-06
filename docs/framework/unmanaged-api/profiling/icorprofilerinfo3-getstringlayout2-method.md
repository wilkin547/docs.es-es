---
description: 'Más información sobre: ICorProfilerInfo3:: Getstringlayout2 ((método)'
title: ICorProfilerInfo3::GetStringLayout2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetStringLayout2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetStringLayout2
helpviewer_keywords:
- ICorProfilerInfo3::GetStringLayout2 method [.NET Framework profiling]
- GetStringLayout2 method [.NET Framework profiling]
ms.assetid: 1a268496-ee51-4d84-8700-ee56fd0c499d
topic_type:
- apiref
ms.openlocfilehash: 398d06dc62245e6a2201feacb62ebbb1e4839ccb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646678"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="559f1-103">ICorProfilerInfo3::GetStringLayout2 (Método)</span><span class="sxs-lookup"><span data-stu-id="559f1-103">ICorProfilerInfo3::GetStringLayout2 Method</span></span>

<span data-ttu-id="559f1-104">Obtiene información sobre la distribución de un objeto de cadena.</span><span class="sxs-lookup"><span data-stu-id="559f1-104">Gets information about the layout of a string object.</span></span> <span data-ttu-id="559f1-105">Este método reemplaza al método [ICorProfilerInfo2:: GetStringLayout (](icorprofilerinfo2-getstringlayout-method.md) .</span><span class="sxs-lookup"><span data-stu-id="559f1-105">This method supersedes the [ICorProfilerInfo2::GetStringLayout](icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="559f1-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="559f1-106">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="559f1-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="559f1-107">Parameters</span></span>  

 `pStringLengthOffset`  
 <span data-ttu-id="559f1-108">enuncia Puntero al desplazamiento de la ubicación, en relación con el `ObjectID` puntero, que almacena la longitud de la propia cadena.</span><span class="sxs-lookup"><span data-stu-id="559f1-108">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="559f1-109">La longitud se almacena como un `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="559f1-109">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="559f1-110">enuncia Puntero al desplazamiento del búfer, en relación con el `ObjectID` puntero, que almacena la cadena de caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="559f1-110">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="559f1-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="559f1-111">Remarks</span></span>  

 <span data-ttu-id="559f1-112">Las cadenas pueden o no terminar en NULL.</span><span class="sxs-lookup"><span data-stu-id="559f1-112">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="559f1-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="559f1-113">Requirements</span></span>  

 <span data-ttu-id="559f1-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="559f1-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="559f1-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="559f1-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="559f1-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="559f1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="559f1-117">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="559f1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="559f1-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="559f1-118">See also</span></span>

- [<span data-ttu-id="559f1-119">ICorProfilerInfo3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="559f1-119">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="559f1-120">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="559f1-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
