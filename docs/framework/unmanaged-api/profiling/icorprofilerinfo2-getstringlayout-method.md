---
title: "ICorProfilerInfo2::GetStringLayout (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetStringLayout
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 52a1b9218feb76f7653f747aa52c44284293221f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="6d6ad-102">ICorProfilerInfo2::GetStringLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="6d6ad-102">ICorProfilerInfo2::GetStringLayout Method</span></span>
<span data-ttu-id="6d6ad-103">Obtiene información sobre la distribución de un objeto de cadena.</span><span class="sxs-lookup"><span data-stu-id="6d6ad-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="6d6ad-104">Este método está en desuso en el [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]y se ha sustituido por la [ICorProfilerInfo3:: Getstringlayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="6d6ad-104">This method is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], and is superseded by the [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d6ad-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d6ad-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d6ad-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6d6ad-106">Parameters</span></span>  
 `pBufferLengthOffset`  
 <span data-ttu-id="6d6ad-107">[out] Un puntero al desplazamiento de la ubicación, relativa a la `ObjectID` puntero, que almacena la longitud de la cadena.</span><span class="sxs-lookup"><span data-stu-id="6d6ad-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="6d6ad-108">La longitud se almacena como un `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="6d6ad-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d6ad-109">Este parámetro devuelve la longitud de la cadena, no la longitud del búfer.</span><span class="sxs-lookup"><span data-stu-id="6d6ad-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="6d6ad-110">La longitud del búfer ya no está disponible.</span><span class="sxs-lookup"><span data-stu-id="6d6ad-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="6d6ad-111">[out] Un puntero al desplazamiento de la ubicación, relativa a la `ObjectID` puntero, que almacena la longitud de la propia cadena.</span><span class="sxs-lookup"><span data-stu-id="6d6ad-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="6d6ad-112">La longitud se almacena como un `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="6d6ad-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="6d6ad-113">[out] Un puntero para el desplazamiento del búfer, relativo a la `ObjectID` puntero, que almacena la cadena de caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="6d6ad-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d6ad-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6d6ad-114">Remarks</span></span>  
 <span data-ttu-id="6d6ad-115">El `GetStringLayout` método obtiene los desplazamientos, relativo a la `ObjectID` puntero, de las ubicaciones en que se almacenan los siguientes:</span><span class="sxs-lookup"><span data-stu-id="6d6ad-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
-   <span data-ttu-id="6d6ad-116">La longitud de búfer de la cadena.</span><span class="sxs-lookup"><span data-stu-id="6d6ad-116">The length of the string's buffer.</span></span>  
  
-   <span data-ttu-id="6d6ad-117">La longitud de la propia cadena.</span><span class="sxs-lookup"><span data-stu-id="6d6ad-117">The length of the string itself.</span></span>  
  
-   <span data-ttu-id="6d6ad-118">Búfer que contiene la cadena real de caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="6d6ad-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="6d6ad-119">Pueden ser cadenas terminadas en null.</span><span class="sxs-lookup"><span data-stu-id="6d6ad-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d6ad-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d6ad-120">Requirements</span></span>  
 <span data-ttu-id="6d6ad-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d6ad-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d6ad-122">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6d6ad-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6d6ad-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d6ad-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d6ad-124">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d6ad-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d6ad-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d6ad-125">See Also</span></span>  
 [<span data-ttu-id="6d6ad-126">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d6ad-126">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="6d6ad-127">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d6ad-127">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
