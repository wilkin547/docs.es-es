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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 57a21a3e4c1324e15a8418dacb8cfe7c5163f334
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454421"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="4b2e3-102">ICorProfilerInfo3::GetStringLayout2 (Método)</span><span class="sxs-lookup"><span data-stu-id="4b2e3-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>
<span data-ttu-id="4b2e3-103">Obtiene información sobre la distribución de un objeto de cadena.</span><span class="sxs-lookup"><span data-stu-id="4b2e3-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="4b2e3-104">Este método reemplaza a la [ICorProfilerInfo2:: GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="4b2e3-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b2e3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b2e3-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b2e3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4b2e3-106">Parameters</span></span>  
 `pStringLengthOffset`  
 <span data-ttu-id="4b2e3-107">[out] Un puntero al desplazamiento de la ubicación, relativa a la `ObjectID` puntero, que almacena la longitud de la propia cadena.</span><span class="sxs-lookup"><span data-stu-id="4b2e3-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="4b2e3-108">La longitud se almacena como un `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="4b2e3-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="4b2e3-109">[out] Un puntero para el desplazamiento del búfer, relativo a la `ObjectID` puntero, que almacena la cadena de caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="4b2e3-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b2e3-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4b2e3-110">Remarks</span></span>  
 <span data-ttu-id="4b2e3-111">Las cadenas pueden o no pueden ser terminada en null.</span><span class="sxs-lookup"><span data-stu-id="4b2e3-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b2e3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4b2e3-112">Requirements</span></span>  
 <span data-ttu-id="4b2e3-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b2e3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b2e3-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4b2e3-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4b2e3-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b2e3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b2e3-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b2e3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b2e3-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b2e3-117">See Also</span></span>  
 [<span data-ttu-id="4b2e3-118">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4b2e3-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="4b2e3-119">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="4b2e3-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
