---
title: "ICLRMetaHost::GetVersionFromFile (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRMetaHost.GetVersionFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 61e6cd1c83cc369e06099c72a6012eb448d6d37a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetahostgetversionfromfile-method"></a><span data-ttu-id="417dd-102">ICLRMetaHost::GetVersionFromFile (Método)</span><span class="sxs-lookup"><span data-stu-id="417dd-102">ICLRMetaHost::GetVersionFromFile Method</span></span>
<span data-ttu-id="417dd-103">Obtiene .NET Framework versión de compilación original de un ensamblado (que se almacena en los metadatos), dada su ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="417dd-103">Gets an assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="417dd-104">Este método reemplaza a la [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="417dd-104">This method supersedes the [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="417dd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="417dd-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="417dd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="417dd-106">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="417dd-107">[in] La ruta de acceso del archivo de ensamblado completo.</span><span class="sxs-lookup"><span data-stu-id="417dd-107">[in] The complete assembly file path.</span></span>  
  
 `pwzbuffer`  
 <span data-ttu-id="417dd-108">[out] La versión de compilación de .NET Framework almacenada en los metadatos, en el formato "v*A*. *B*[. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="417dd-108">[out] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="417dd-109">*A*, *B*, y *X* son números decimales que corresponden a la versión principal, la versión secundaria y el número de compilación.</span><span class="sxs-lookup"><span data-stu-id="417dd-109">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="417dd-110">La longitud de esta cadena se limita a MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="417dd-110">The length of this string is limited to MAX_PATH.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="417dd-111">Esta salida coincide con el nombre del directorio para la versión de .NET Framework, tal y como aparece bajo C:\Windows\Microsoft.NET\Framework.</span><span class="sxs-lookup"><span data-stu-id="417dd-111">This output matches the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="417dd-112">Valores de ejemplo son "v1.0.3705", "v1.1.4322", "v2.0.50727" y "v4.0. *X*", donde *X* depende del número de compilación instalado.</span><span class="sxs-lookup"><span data-stu-id="417dd-112">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="417dd-113">Tenga en cuenta que el prefijo "v" es necesario.</span><span class="sxs-lookup"><span data-stu-id="417dd-113">Note that the "v" prefix is required.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="417dd-114">[entrada, salida] El tamaño de `pwzbuffer` para evitar saturaciones del búfer.</span><span class="sxs-lookup"><span data-stu-id="417dd-114">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="417dd-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="417dd-115">Return Value</span></span>  
 <span data-ttu-id="417dd-116">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="417dd-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="417dd-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="417dd-117">HRESULT</span></span>|<span data-ttu-id="417dd-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="417dd-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="417dd-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="417dd-119">S_OK</span></span>|<span data-ttu-id="417dd-120">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="417dd-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="417dd-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="417dd-121">E_POINTER</span></span>|<span data-ttu-id="417dd-122">`pwzbuffer` o `pcchBuffer` es null.</span><span class="sxs-lookup"><span data-stu-id="417dd-122">`pwzbuffer` or `pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="417dd-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="417dd-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="417dd-124">El búfer es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="417dd-124">The buffer is too small.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="417dd-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="417dd-125">Requirements</span></span>  
 <span data-ttu-id="417dd-126">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="417dd-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="417dd-127">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="417dd-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="417dd-128">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="417dd-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="417dd-129">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="417dd-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="417dd-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="417dd-130">See Also</span></span>  
 [<span data-ttu-id="417dd-131">ICLRMetaHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="417dd-131">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="417dd-132">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="417dd-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
