---
description: 'Más información sobre: ICorProfilerInfo3:: GetRuntimeInformation ((método)'
title: ICorProfilerInfo3::GetRuntimeInformation (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetRuntimeInformation Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type:
- apiref
ms.openlocfilehash: f615cc54e12b6f2f6eaa7335353f2f5f6a8ecfce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646717"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a><span data-ttu-id="14004-103">ICorProfilerInfo3::GetRuntimeInformation (Método)</span><span class="sxs-lookup"><span data-stu-id="14004-103">ICorProfilerInfo3::GetRuntimeInformation Method</span></span>

<span data-ttu-id="14004-104">Proporciona información de versión sobre el Common Language Runtime (CLR) del que se está generando el archivo.</span><span class="sxs-lookup"><span data-stu-id="14004-104">Provides version information about the common language runtime (CLR) that is being profiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14004-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14004-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntimeInformation(  
       [out] USHORT *pClrInstanceId,  
       [out] COR_PRF_RUNTIME_TYPE *pRuntimeType,  
       [out] USHORT *pMajorVersion,  
       [out] USHORT *pMinorVersion,  
       [out] USHORT *pBuildNumber,  
       [out] USHORT *pQFEVersion,  
       [in]  ULONG  cchVersionString,  
       [out] ULONG  *pcchVersionString,  
       [out, size_is(cchVersionString), length_is(*pcchVersionString)]  
                   WCHAR  szVersionString[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14004-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="14004-106">Parameters</span></span>  

 `pClrInstanceId`  
 <span data-ttu-id="14004-107">enuncia IDENTIFICADOR representativo de una instancia de CLR en ejecución en un proceso.</span><span class="sxs-lookup"><span data-stu-id="14004-107">[out] The representative ID of a running CLR instance in a process.</span></span> <span data-ttu-id="14004-108">Es lo mismo `ClrInstanceID` que los informes de eventos de inicio de seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="14004-108">This is the same as the `ClrInstanceID` that the event tracing for Windows (ETW) startup event reports.</span></span>  
  
 `pRuntimeType`  
 <span data-ttu-id="14004-109">enuncia El tipo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="14004-109">[out] The runtime type.</span></span> <span data-ttu-id="14004-110">Este parámetro devuelve `COR_PRF_DESKTOP_CLR` para la versión de escritorio de CLR, o `COR_PRF_CORE_CLR` para la versión principal de CLR que se usa en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="14004-110">This parameter returns `COR_PRF_DESKTOP_CLR` for the desktop version of the CLR, or `COR_PRF_CORE_CLR` for the core version of the CLR used in Silverlight.</span></span>  
  
 `pMajorVersion`  
 <span data-ttu-id="14004-111">enuncia Número de versión principal de CLR.</span><span class="sxs-lookup"><span data-stu-id="14004-111">[out] The major version number of the CLR.</span></span>  
  
 `pMinorVersion`  
 <span data-ttu-id="14004-112">enuncia Número de versión secundaria de CLR.</span><span class="sxs-lookup"><span data-stu-id="14004-112">[out] The minor version number of the CLR.</span></span>  
  
 `pBuildVersion`  
 <span data-ttu-id="14004-113">enuncia Número de versión de compilación de CLR.</span><span class="sxs-lookup"><span data-stu-id="14004-113">[out] The build version number of the CLR.</span></span>  
  
 `pQFEVersion`  
 <span data-ttu-id="14004-114">enuncia El número de versión de CLR que está asociado a una actualización de software.</span><span class="sxs-lookup"><span data-stu-id="14004-114">[out] The version number of the CLR that is associated with a software update.</span></span>  
  
 `cchVersionString`  
 <span data-ttu-id="14004-115">de La longitud, en caracteres, del búfer al que `szVersionString` apunta.</span><span class="sxs-lookup"><span data-stu-id="14004-115">[in] The length, in characters, of the buffer that `szVersionString` points to.</span></span>  
  
 `pcchVersionString`  
 <span data-ttu-id="14004-116">enuncia La longitud, en caracteres, de `szVersionString` .</span><span class="sxs-lookup"><span data-stu-id="14004-116">[out] The length, in characters, of `szVersionString`.</span></span>  
  
 `szVersionString`  
 <span data-ttu-id="14004-117">enuncia Cadena de versión de CLR.</span><span class="sxs-lookup"><span data-stu-id="14004-117">[out] The CLR version string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14004-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="14004-118">Remarks</span></span>  

 <span data-ttu-id="14004-119">Puede pasar null para cualquier parámetro.</span><span class="sxs-lookup"><span data-stu-id="14004-119">You may pass null for any parameter.</span></span> <span data-ttu-id="14004-120">Sin embargo, `pcchVersionString` no puede ser null a menos que `szVersionString` también sea NULL.</span><span class="sxs-lookup"><span data-stu-id="14004-120">However, `pcchVersionString` cannot be null unless `szVersionString` is also null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14004-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14004-121">Requirements</span></span>  

 <span data-ttu-id="14004-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14004-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14004-123">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="14004-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="14004-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14004-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14004-125">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14004-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14004-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="14004-126">See also</span></span>

- [<span data-ttu-id="14004-127">ICorProfilerInfo3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="14004-127">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="14004-128">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="14004-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="14004-129">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="14004-129">Profiling</span></span>](index.md)
