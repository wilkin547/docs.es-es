---
title: ICorProfilerInfo::GetAppDomainInfo (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetAppDomainInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetAppDomainInfo
helpviewer_keywords:
- ICorProfilerInfo::GetAppDomainInfo method [.NET Framework profiling]
- GetAppDomainInfo method [.NET Framework profiling]
ms.assetid: a6bf5a04-e03e-44f0-917a-96f6a6d3cc96
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 83468e13e1e028b031c31791910c4dd2d792f232
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168771"
---
# <a name="icorprofilerinfogetappdomaininfo-method"></a><span data-ttu-id="4f7d3-102">ICorProfilerInfo::GetAppDomainInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="4f7d3-102">ICorProfilerInfo::GetAppDomainInfo Method</span></span>
<span data-ttu-id="4f7d3-103">Acepta un identificador de dominio de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f7d3-103">Accepts an application domain ID.</span></span> <span data-ttu-id="4f7d3-104">Devuelve un nombre de dominio de una aplicación y el identificador del proceso que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="4f7d3-104">Returns an application domain name and the ID of the process that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f7d3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f7d3-105">Syntax</span></span>  
  
```  
HRESULT GetAppDomainInfo(  
    [in]  AppDomainID appDomainId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] ProcessID   *pProcessId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f7d3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4f7d3-106">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="4f7d3-107">[in] Identificador de dominio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f7d3-107">[in] The ID of the application domain.</span></span>  
  
 `cchName`  
 <span data-ttu-id="4f7d3-108">[in] Longitud, en caracteres, del búfer de retorno `szName`.</span><span class="sxs-lookup"><span data-stu-id="4f7d3-108">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="4f7d3-109">[out] Puntero a la longitud total de caracteres del nombre de dominio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f7d3-109">[out] A pointer to the total character length of the application domain name.</span></span>  
  
 `szName`  
 <span data-ttu-id="4f7d3-110">[out] Búfer de caracteres anchos proporcionado por el llamador.</span><span class="sxs-lookup"><span data-stu-id="4f7d3-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="4f7d3-111">Con la devolución del método, `szName` contendrá el nombre total o parcial del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f7d3-111">When the method returns, `szName` will contain the full or partial application domain name.</span></span>  
  
 `pProcessId`  
 <span data-ttu-id="4f7d3-112">[out] Puntero al identificador del proceso que contiene el dominio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f7d3-112">[out] A pointer to the ID of the process that contains the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f7d3-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4f7d3-113">Remarks</span></span>  
 <span data-ttu-id="4f7d3-114">Tras la devolución de este método, debe comprobar que el búfer `szName` era lo suficientemente grande como para contener el nombre completo del dominio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f7d3-114">After this method returns, you must verify that the `szName` buffer was large enough to contain the full name of the application domain.</span></span> <span data-ttu-id="4f7d3-115">Para ello, compare el valor al que `pcchName` apunta con el valor del parámetro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="4f7d3-115">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="4f7d3-116">Si `pcchName` apunta un valor mayor que `cchName`, asigne un búfer `szName` mayor, actualice `cchName` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetAppDomainInfo`.</span><span class="sxs-lookup"><span data-stu-id="4f7d3-116">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetAppDomainInfo` again.</span></span>  
  
 <span data-ttu-id="4f7d3-117">También tiene la opción de llamar primero a `GetAppDomainInfo` con un búfer `szName` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="4f7d3-117">Alternatively, you can first call `GetAppDomainInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="4f7d3-118">Después, puede establecer el tamaño del búfer en el valor devuelto en `pcchName` y volver a llamar a `GetAppDomainInfo`.</span><span class="sxs-lookup"><span data-stu-id="4f7d3-118">You can then set the buffer size to the value returned in `pcchName` and call `GetAppDomainInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f7d3-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f7d3-119">Requirements</span></span>  
 <span data-ttu-id="4f7d3-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f7d3-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f7d3-121">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4f7d3-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4f7d3-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f7d3-122">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4f7d3-123">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4f7d3-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4f7d3-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f7d3-124">See also</span></span>

- [<span data-ttu-id="4f7d3-125">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4f7d3-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="4f7d3-126">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="4f7d3-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="4f7d3-127">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="4f7d3-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
