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
ms.openlocfilehash: 71e2bc1d60e050d817429db5bc6926b3b16c637c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431409"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="d440b-102">ICorProfilerInfo2::GetStringLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="d440b-102">ICorProfilerInfo2::GetStringLayout Method</span></span>
<span data-ttu-id="d440b-103">Obtiene información sobre la distribución de un objeto de cadena.</span><span class="sxs-lookup"><span data-stu-id="d440b-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="d440b-104">Este método está en desuso en el .NET Framework 4 y se ha sustituido por el método [ICorProfilerInfo3:: GetStringLayout2 (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d440b-104">This method is deprecated in the .NET Framework 4, and is superseded by the [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d440b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d440b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d440b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d440b-106">Parameters</span></span>  
 `pBufferLengthOffset`  
 <span data-ttu-id="d440b-107">enuncia Puntero al desplazamiento de la ubicación, en relación con el puntero de `ObjectID`, que almacena la longitud de la cadena.</span><span class="sxs-lookup"><span data-stu-id="d440b-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="d440b-108">La longitud se almacena como `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="d440b-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d440b-109">Este parámetro devuelve la longitud de la cadena en sí, no la longitud del búfer.</span><span class="sxs-lookup"><span data-stu-id="d440b-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="d440b-110">La longitud del búfer ya no está disponible.</span><span class="sxs-lookup"><span data-stu-id="d440b-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="d440b-111">enuncia Puntero al desplazamiento de la ubicación, en relación con el puntero de `ObjectID`, que almacena la longitud de la propia cadena.</span><span class="sxs-lookup"><span data-stu-id="d440b-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="d440b-112">La longitud se almacena como `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="d440b-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="d440b-113">enuncia Puntero al desplazamiento del búfer, relativo al puntero de `ObjectID`, que almacena la cadena de caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="d440b-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d440b-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d440b-114">Remarks</span></span>  
 <span data-ttu-id="d440b-115">El método `GetStringLayout` obtiene los desplazamientos, con relación al puntero `ObjectID`, de las ubicaciones en las que se almacenan los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d440b-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
- <span data-ttu-id="d440b-116">Longitud del búfer de la cadena.</span><span class="sxs-lookup"><span data-stu-id="d440b-116">The length of the string's buffer.</span></span>  
  
- <span data-ttu-id="d440b-117">La longitud de la propia cadena.</span><span class="sxs-lookup"><span data-stu-id="d440b-117">The length of the string itself.</span></span>  
  
- <span data-ttu-id="d440b-118">Búfer que contiene la cadena real de caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="d440b-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="d440b-119">Las cadenas pueden terminar en NULL.</span><span class="sxs-lookup"><span data-stu-id="d440b-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d440b-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d440b-120">Requirements</span></span>  
 <span data-ttu-id="d440b-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d440b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d440b-122">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d440b-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d440b-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d440b-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d440b-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d440b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d440b-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="d440b-125">See also</span></span>

- [<span data-ttu-id="d440b-126">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d440b-126">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="d440b-127">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d440b-127">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
