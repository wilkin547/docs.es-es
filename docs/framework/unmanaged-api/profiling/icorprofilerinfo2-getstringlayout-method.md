---
title: ICorProfilerInfo2::GetStringLayout (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStringLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cc94c63edb602d87a7c08a9051eb2ef760834477
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200979"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="89123-102">ICorProfilerInfo2::GetStringLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="89123-102">ICorProfilerInfo2::GetStringLayout Method</span></span>
<span data-ttu-id="89123-103">Obtiene información sobre la distribución de un objeto de cadena.</span><span class="sxs-lookup"><span data-stu-id="89123-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="89123-104">Este método está en desuso en el [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]y se ha reemplazado por la [ICorProfilerInfo3:: Getstringlayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="89123-104">This method is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], and is superseded by the [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89123-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89123-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89123-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="89123-106">Parameters</span></span>  
 `pBufferLengthOffset`  
 <span data-ttu-id="89123-107">[out] Un puntero para el desplazamiento de la ubicación, relativa a la `ObjectID` puntero, que almacena la longitud de la cadena.</span><span class="sxs-lookup"><span data-stu-id="89123-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="89123-108">La longitud se almacena como un `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="89123-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89123-109">Este parámetro devuelve la longitud de la cadena, no la longitud del búfer.</span><span class="sxs-lookup"><span data-stu-id="89123-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="89123-110">La longitud del búfer ya no está disponible.</span><span class="sxs-lookup"><span data-stu-id="89123-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="89123-111">[out] Un puntero para el desplazamiento de la ubicación, relativa a la `ObjectID` puntero, que almacena la longitud de la propia cadena.</span><span class="sxs-lookup"><span data-stu-id="89123-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="89123-112">La longitud se almacena como un `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="89123-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="89123-113">[out] Un puntero al desplazamiento del búfer, relativo a la `ObjectID` puntero, que almacena la cadena de caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="89123-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89123-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="89123-114">Remarks</span></span>  
 <span data-ttu-id="89123-115">El `GetStringLayout` método obtiene los desplazamientos, relativa a la `ObjectID` puntero, de las ubicaciones donde se almacenan los siguientes:</span><span class="sxs-lookup"><span data-stu-id="89123-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
-   <span data-ttu-id="89123-116">La longitud de búfer de la cadena.</span><span class="sxs-lookup"><span data-stu-id="89123-116">The length of the string's buffer.</span></span>  
  
-   <span data-ttu-id="89123-117">La longitud de la propia cadena.</span><span class="sxs-lookup"><span data-stu-id="89123-117">The length of the string itself.</span></span>  
  
-   <span data-ttu-id="89123-118">Búfer que contiene la cadena real de caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="89123-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="89123-119">Pueden ser cadenas terminadas en null.</span><span class="sxs-lookup"><span data-stu-id="89123-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89123-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89123-120">Requirements</span></span>  
 <span data-ttu-id="89123-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89123-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89123-122">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="89123-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="89123-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89123-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89123-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89123-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89123-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="89123-125">See also</span></span>

- [<span data-ttu-id="89123-126">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="89123-126">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="89123-127">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="89123-127">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
