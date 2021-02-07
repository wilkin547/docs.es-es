---
description: 'Más información acerca de: ICorProfilerInfo2:: GetStringLayout ((método)'
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
ms.openlocfilehash: 145d748d756fd30ef0522d1c516f8f63ca604545
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716385"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="ee9bf-103">ICorProfilerInfo2::GetStringLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="ee9bf-103">ICorProfilerInfo2::GetStringLayout Method</span></span>

<span data-ttu-id="ee9bf-104">Obtiene información sobre la distribución de un objeto de cadena.</span><span class="sxs-lookup"><span data-stu-id="ee9bf-104">Gets information about the layout of a string object.</span></span> <span data-ttu-id="ee9bf-105">Este método está en desuso en el .NET Framework 4 y se ha sustituido por el método [ICorProfilerInfo3:: GetStringLayout2 (](icorprofilerinfo3-getstringlayout2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ee9bf-105">This method is deprecated in the .NET Framework 4, and is superseded by the [ICorProfilerInfo3::GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee9bf-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ee9bf-106">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee9bf-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ee9bf-107">Parameters</span></span>  

 `pBufferLengthOffset`  
 <span data-ttu-id="ee9bf-108">enuncia Puntero al desplazamiento de la ubicación, en relación con el `ObjectID` puntero, que almacena la longitud de la cadena.</span><span class="sxs-lookup"><span data-stu-id="ee9bf-108">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="ee9bf-109">La longitud se almacena como un `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="ee9bf-109">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee9bf-110">Este parámetro devuelve la longitud de la cadena en sí, no la longitud del búfer.</span><span class="sxs-lookup"><span data-stu-id="ee9bf-110">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="ee9bf-111">La longitud del búfer ya no está disponible.</span><span class="sxs-lookup"><span data-stu-id="ee9bf-111">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="ee9bf-112">enuncia Puntero al desplazamiento de la ubicación, en relación con el `ObjectID` puntero, que almacena la longitud de la propia cadena.</span><span class="sxs-lookup"><span data-stu-id="ee9bf-112">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="ee9bf-113">La longitud se almacena como un `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="ee9bf-113">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="ee9bf-114">enuncia Puntero al desplazamiento del búfer, relativo al `ObjectID` puntero, que almacena la cadena de caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="ee9bf-114">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee9bf-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ee9bf-115">Remarks</span></span>  

 <span data-ttu-id="ee9bf-116">El `GetStringLayout` método obtiene los desplazamientos, con relación al `ObjectID` puntero, de las ubicaciones en las que se almacenan los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ee9bf-116">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
- <span data-ttu-id="ee9bf-117">Longitud del búfer de la cadena.</span><span class="sxs-lookup"><span data-stu-id="ee9bf-117">The length of the string's buffer.</span></span>  
  
- <span data-ttu-id="ee9bf-118">La longitud de la propia cadena.</span><span class="sxs-lookup"><span data-stu-id="ee9bf-118">The length of the string itself.</span></span>  
  
- <span data-ttu-id="ee9bf-119">Búfer que contiene la cadena real de caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="ee9bf-119">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="ee9bf-120">Las cadenas pueden terminar en NULL.</span><span class="sxs-lookup"><span data-stu-id="ee9bf-120">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee9bf-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee9bf-121">Requirements</span></span>  

 <span data-ttu-id="ee9bf-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee9bf-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee9bf-123">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ee9bf-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ee9bf-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee9bf-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee9bf-125">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee9bf-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee9bf-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee9bf-126">See also</span></span>

- [<span data-ttu-id="ee9bf-127">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ee9bf-127">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="ee9bf-128">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ee9bf-128">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
