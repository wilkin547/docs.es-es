---
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
ms.openlocfilehash: 20556d85655a0a1bbe069a94b99c19c774a13ce6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449684"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a><span data-ttu-id="39148-102">ICorProfilerInfo3::GetRuntimeInformation (Método)</span><span class="sxs-lookup"><span data-stu-id="39148-102">ICorProfilerInfo3::GetRuntimeInformation Method</span></span>
<span data-ttu-id="39148-103">Proporciona información de versión sobre el Common Language Runtime (CLR) del que se está generando el archivo.</span><span class="sxs-lookup"><span data-stu-id="39148-103">Provides version information about the common language runtime (CLR) that is being profiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39148-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39148-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="39148-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39148-105">Parameters</span></span>  
 `pClrInstanceId`  
 <span data-ttu-id="39148-106">enuncia IDENTIFICADOR representativo de una instancia de CLR en ejecución en un proceso.</span><span class="sxs-lookup"><span data-stu-id="39148-106">[out] The representative ID of a running CLR instance in a process.</span></span> <span data-ttu-id="39148-107">Esto es lo mismo que el `ClrInstanceID` que los informes de eventos de inicio de seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="39148-107">This is the same as the `ClrInstanceID` that the event tracing for Windows (ETW) startup event reports.</span></span>  
  
 `pRuntimeType`  
 <span data-ttu-id="39148-108">enuncia El tipo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="39148-108">[out] The runtime type.</span></span> <span data-ttu-id="39148-109">Este parámetro devuelve `COR_PRF_DESKTOP_CLR` para la versión de escritorio de CLR o `COR_PRF_CORE_CLR` para la versión básica de CLR que se usa en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="39148-109">This parameter returns `COR_PRF_DESKTOP_CLR` for the desktop version of the CLR, or `COR_PRF_CORE_CLR` for the core version of the CLR used in Silverlight.</span></span>  
  
 `pMajorVersion`  
 <span data-ttu-id="39148-110">enuncia Número de versión principal de CLR.</span><span class="sxs-lookup"><span data-stu-id="39148-110">[out] The major version number of the CLR.</span></span>  
  
 `pMinorVersion`  
 <span data-ttu-id="39148-111">enuncia Número de versión secundaria de CLR.</span><span class="sxs-lookup"><span data-stu-id="39148-111">[out] The minor version number of the CLR.</span></span>  
  
 `pBuildVersion`  
 <span data-ttu-id="39148-112">enuncia Número de versión de compilación de CLR.</span><span class="sxs-lookup"><span data-stu-id="39148-112">[out] The build version number of the CLR.</span></span>  
  
 `pQFEVersion`  
 <span data-ttu-id="39148-113">enuncia El número de versión de CLR que está asociado a una actualización de software.</span><span class="sxs-lookup"><span data-stu-id="39148-113">[out] The version number of the CLR that is associated with a software update.</span></span>  
  
 `cchVersionString`  
 <span data-ttu-id="39148-114">de La longitud, en caracteres, del búfer al que apunta `szVersionString`.</span><span class="sxs-lookup"><span data-stu-id="39148-114">[in] The length, in characters, of the buffer that `szVersionString` points to.</span></span>  
  
 `pcchVersionString`  
 <span data-ttu-id="39148-115">enuncia La longitud, en caracteres, de `szVersionString`.</span><span class="sxs-lookup"><span data-stu-id="39148-115">[out] The length, in characters, of `szVersionString`.</span></span>  
  
 `szVersionString`  
 <span data-ttu-id="39148-116">enuncia Cadena de versión de CLR.</span><span class="sxs-lookup"><span data-stu-id="39148-116">[out] The CLR version string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39148-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="39148-117">Remarks</span></span>  
 <span data-ttu-id="39148-118">Puede pasar null para cualquier parámetro.</span><span class="sxs-lookup"><span data-stu-id="39148-118">You may pass null for any parameter.</span></span> <span data-ttu-id="39148-119">Sin embargo, `pcchVersionString` no puede ser null a menos que `szVersionString` también sea NULL.</span><span class="sxs-lookup"><span data-stu-id="39148-119">However, `pcchVersionString` cannot be null unless `szVersionString` is also null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39148-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39148-120">Requirements</span></span>  
 <span data-ttu-id="39148-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39148-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39148-122">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="39148-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="39148-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39148-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39148-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39148-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39148-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="39148-125">See also</span></span>

- [<span data-ttu-id="39148-126">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="39148-126">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="39148-127">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="39148-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="39148-128">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="39148-128">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
