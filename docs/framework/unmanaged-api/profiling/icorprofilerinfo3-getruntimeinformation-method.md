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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7087864d0305f0cdb0b4977f037cf5a7c4dee18d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783142"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a><span data-ttu-id="bfa13-102">ICorProfilerInfo3::GetRuntimeInformation (Método)</span><span class="sxs-lookup"><span data-stu-id="bfa13-102">ICorProfilerInfo3::GetRuntimeInformation Method</span></span>
<span data-ttu-id="bfa13-103">Proporciona información de versión de common language runtime (CLR) que se está generando el perfil.</span><span class="sxs-lookup"><span data-stu-id="bfa13-103">Provides version information about the common language runtime (CLR) that is being profiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfa13-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bfa13-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="bfa13-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bfa13-105">Parameters</span></span>  
 `pClrInstanceId`  
 <span data-ttu-id="bfa13-106">[out] Identificador representativo de una instancia en ejecución CLR en un proceso.</span><span class="sxs-lookup"><span data-stu-id="bfa13-106">[out] The representative ID of a running CLR instance in a process.</span></span> <span data-ttu-id="bfa13-107">Esto es el mismo que el `ClrInstanceID` que informa el seguimiento de eventos para eventos de inicio de Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="bfa13-107">This is the same as the `ClrInstanceID` that the event tracing for Windows (ETW) startup event reports.</span></span>  
  
 `pRuntimeType`  
 <span data-ttu-id="bfa13-108">[out] El tipo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bfa13-108">[out] The runtime type.</span></span> <span data-ttu-id="bfa13-109">Este parámetro devuelve `COR_PRF_DESKTOP_CLR` para la versión de escritorio de CLR, o `COR_PRF_CORE_CLR` para la versión básica de CLR que utiliza en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="bfa13-109">This parameter returns `COR_PRF_DESKTOP_CLR` for the desktop version of the CLR, or `COR_PRF_CORE_CLR` for the core version of the CLR used in Silverlight.</span></span>  
  
 `pMajorVersion`  
 <span data-ttu-id="bfa13-110">[out] El número de versión principal de CLR.</span><span class="sxs-lookup"><span data-stu-id="bfa13-110">[out] The major version number of the CLR.</span></span>  
  
 `pMinorVersion`  
 <span data-ttu-id="bfa13-111">[out] El número de versión secundaria de CLR.</span><span class="sxs-lookup"><span data-stu-id="bfa13-111">[out] The minor version number of the CLR.</span></span>  
  
 `pBuildVersion`  
 <span data-ttu-id="bfa13-112">[out] El número de versión de compilación de CLR.</span><span class="sxs-lookup"><span data-stu-id="bfa13-112">[out] The build version number of the CLR.</span></span>  
  
 `pQFEVersion`  
 <span data-ttu-id="bfa13-113">[out] El número de versión de CLR que está asociado con una actualización de software.</span><span class="sxs-lookup"><span data-stu-id="bfa13-113">[out] The version number of the CLR that is associated with a software update.</span></span>  
  
 `cchVersionString`  
 <span data-ttu-id="bfa13-114">[in] La longitud en caracteres, del búfer que `szVersionString` apunta a.</span><span class="sxs-lookup"><span data-stu-id="bfa13-114">[in] The length, in characters, of the buffer that `szVersionString` points to.</span></span>  
  
 `pcchVersionString`  
 <span data-ttu-id="bfa13-115">[out] La longitud en caracteres, de `szVersionString`.</span><span class="sxs-lookup"><span data-stu-id="bfa13-115">[out] The length, in characters, of `szVersionString`.</span></span>  
  
 `szVersionString`  
 <span data-ttu-id="bfa13-116">[out] La cadena de versión CLR.</span><span class="sxs-lookup"><span data-stu-id="bfa13-116">[out] The CLR version string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfa13-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bfa13-117">Remarks</span></span>  
 <span data-ttu-id="bfa13-118">Se puede pasar null para cualquier parámetro.</span><span class="sxs-lookup"><span data-stu-id="bfa13-118">You may pass null for any parameter.</span></span> <span data-ttu-id="bfa13-119">Sin embargo, `pcchVersionString` no puede ser null a menos que `szVersionString` también es null.</span><span class="sxs-lookup"><span data-stu-id="bfa13-119">However, `pcchVersionString` cannot be null unless `szVersionString` is also null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfa13-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bfa13-120">Requirements</span></span>  
 <span data-ttu-id="bfa13-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfa13-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfa13-122">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bfa13-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bfa13-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bfa13-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfa13-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfa13-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfa13-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfa13-125">See also</span></span>

- [<span data-ttu-id="bfa13-126">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bfa13-126">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="bfa13-127">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="bfa13-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="bfa13-128">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="bfa13-128">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
