---
title: "ICLRRuntimeInfo::GetVersionString (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetVersionString
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetVersionString
helpviewer_keywords:
- ICLRRuntimeInfo::GetVersionString method [.NET Framework hosting]
- GetVersionString method, ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 98b097ef-2276-4dd9-8551-b03c972e8179
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 170b144c642463f6030e033cb5f5aaaf9755d4e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfogetversionstring-method"></a><span data-ttu-id="09501-102">ICLRRuntimeInfo::GetVersionString (Método)</span><span class="sxs-lookup"><span data-stu-id="09501-102">ICLRRuntimeInfo::GetVersionString Method</span></span>
<span data-ttu-id="09501-103">Obtiene información de versión de common language runtime (CLR) asociado a una determinada [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="09501-103">Gets common language runtime (CLR) version information associated with a given [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="09501-104">Este método reemplaza las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="09501-104">This method supersedes the following functions:</span></span>  
  
-   [<span data-ttu-id="09501-105">GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="09501-105">GetRequestedRuntimeInfo</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
  
-   [<span data-ttu-id="09501-106">GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="09501-106">GetRequestedRuntimeVersion</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="09501-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09501-107">Syntax</span></span>  
  
```  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="09501-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="09501-108">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="09501-109">[out] La versión de compilación de .NET Framework en el formato "v*A*. *B*[. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="09501-109">[out] The .NET Framework compilation version in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="09501-110">*A*, *B*, y *X* son números decimales que corresponden a la versión principal, la versión secundaria y el número de compilación.</span><span class="sxs-lookup"><span data-stu-id="09501-110">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="09501-111">*X* es opcional.</span><span class="sxs-lookup"><span data-stu-id="09501-111">*X* is optional.</span></span> <span data-ttu-id="09501-112">Si *X* es no está presente, no hay ningún punto final.</span><span class="sxs-lookup"><span data-stu-id="09501-112">If *X* is not present, there is no trailing period.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09501-113">Este parámetro debe coincidir con el nombre del directorio para la versión de .NET Framework, tal y como aparece bajo C:\Windows\Microsoft.NET\Framework.</span><span class="sxs-lookup"><span data-stu-id="09501-113">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="09501-114">Valores de ejemplo son "v1.0.3705", "v1.1.4322", "v2.0.50727" y "v4.0. *x*", donde *x* depende del número de compilación instalado.</span><span class="sxs-lookup"><span data-stu-id="09501-114">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*x*", where *x* depends on the build number installed.</span></span> <span data-ttu-id="09501-115">Tenga en cuenta que el prefijo "v" es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="09501-115">Note that the "v" prefix is mandatory.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="09501-116">[entrada, salida] Especifica el tamaño de `pwzBuffer` para evitar saturaciones del búfer.</span><span class="sxs-lookup"><span data-stu-id="09501-116">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="09501-117">Si `pwzBuffer` es `null`, `pchBuffer` devuelve el tamaño necesario de `pwzBuffer` para permitir la preasignación.</span><span class="sxs-lookup"><span data-stu-id="09501-117">If `pwzBuffer` is `null`, `pchBuffer` returns the required size of `pwzBuffer` to allow preallocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09501-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="09501-118">Return Value</span></span>  
 <span data-ttu-id="09501-119">Este método devuelve los siguientes HRESULT específicos así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="09501-119">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="09501-120">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09501-120">HRESULT</span></span>|<span data-ttu-id="09501-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="09501-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09501-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="09501-122">S_OK</span></span>|<span data-ttu-id="09501-123">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="09501-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="09501-124">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="09501-124">E_POINTER</span></span>|<span data-ttu-id="09501-125">`pwzBuffer` o `pchBuffer` es null.</span><span class="sxs-lookup"><span data-stu-id="09501-125">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="09501-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09501-126">Requirements</span></span>  
 <span data-ttu-id="09501-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09501-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09501-128">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="09501-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="09501-129">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="09501-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09501-130">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09501-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09501-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="09501-131">See Also</span></span>  
 [<span data-ttu-id="09501-132">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="09501-132">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="09501-133">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="09501-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="09501-134">Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5</span><span class="sxs-lookup"><span data-stu-id="09501-134">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [<span data-ttu-id="09501-135">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="09501-135">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
