---
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
ms.openlocfilehash: 1e3dc4735af68da7f76fc6fce84d2dd4ac3f576e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449653"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="f4c85-102">ICorProfilerInfo3::GetStringLayout2 (Método)</span><span class="sxs-lookup"><span data-stu-id="f4c85-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>
<span data-ttu-id="f4c85-103">Obtiene información sobre la distribución de un objeto de cadena.</span><span class="sxs-lookup"><span data-stu-id="f4c85-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="f4c85-104">Este método reemplaza al método [ICorProfilerInfo2:: GetStringLayout (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f4c85-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4c85-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4c85-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4c85-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4c85-106">Parameters</span></span>  
 `pStringLengthOffset`  
 <span data-ttu-id="f4c85-107">enuncia Puntero al desplazamiento de la ubicación, en relación con el puntero de `ObjectID`, que almacena la longitud de la propia cadena.</span><span class="sxs-lookup"><span data-stu-id="f4c85-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="f4c85-108">La longitud se almacena como `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="f4c85-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="f4c85-109">enuncia Puntero al desplazamiento del búfer, relativo al puntero de `ObjectID`, que almacena la cadena de caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="f4c85-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4c85-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f4c85-110">Remarks</span></span>  
 <span data-ttu-id="f4c85-111">Las cadenas pueden o no terminar en NULL.</span><span class="sxs-lookup"><span data-stu-id="f4c85-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4c85-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4c85-112">Requirements</span></span>  
 <span data-ttu-id="f4c85-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4c85-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4c85-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f4c85-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f4c85-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4c85-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4c85-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4c85-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4c85-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4c85-117">See also</span></span>

- [<span data-ttu-id="f4c85-118">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4c85-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="f4c85-119">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f4c85-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
