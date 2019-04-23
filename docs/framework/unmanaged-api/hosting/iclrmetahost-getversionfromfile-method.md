---
title: ICLRMetaHost::GetVersionFromFile (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a6c7fd48269a3e8291a548b3e13efe5c8e70652
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150818"
---
# <a name="iclrmetahostgetversionfromfile-method"></a><span data-ttu-id="7287c-102">ICLRMetaHost::GetVersionFromFile (Método)</span><span class="sxs-lookup"><span data-stu-id="7287c-102">ICLRMetaHost::GetVersionFromFile Method</span></span>
<span data-ttu-id="7287c-103">Obtiene .NET Framework versión de compilación original un ensamblado (almacenada en los metadatos), dada su ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="7287c-103">Gets an assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="7287c-104">Este método reemplaza el [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="7287c-104">This method supersedes the [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7287c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7287c-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7287c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7287c-106">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="7287c-107">[in] La ruta de acceso completa del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7287c-107">[in] The complete assembly file path.</span></span>  
  
 `pwzbuffer`  
 <span data-ttu-id="7287c-108">[out] La versión de compilación de .NET Framework almacenada en los metadatos, en el formato "v*A*. *B*[. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="7287c-108">[out] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="7287c-109">*Un*, *B*, y *X* son números decimales que corresponden a la versión principal, la versión secundaria y el número de compilación.</span><span class="sxs-lookup"><span data-stu-id="7287c-109">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="7287c-110">La longitud de esta cadena está limitada a MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="7287c-110">The length of this string is limited to MAX_PATH.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7287c-111">Esta salida coincide con el nombre del directorio para la versión de .NET Framework, tal y como aparece bajo C:\Windows\Microsoft.NET\Framework.</span><span class="sxs-lookup"><span data-stu-id="7287c-111">This output matches the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="7287c-112">Los valores de ejemplo son "v1.0.3705", "v1.1.4322", "v2.0.50727" y "v4.0. *X*", donde *X* depende del número de compilación instalado.</span><span class="sxs-lookup"><span data-stu-id="7287c-112">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="7287c-113">Tenga en cuenta que el prefijo "v" es necesario.</span><span class="sxs-lookup"><span data-stu-id="7287c-113">Note that the "v" prefix is required.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="7287c-114">[in, out] El tamaño de `pwzbuffer` para evitar saturaciones de búfer.</span><span class="sxs-lookup"><span data-stu-id="7287c-114">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7287c-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7287c-115">Return Value</span></span>  
 <span data-ttu-id="7287c-116">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="7287c-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7287c-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7287c-117">HRESULT</span></span>|<span data-ttu-id="7287c-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="7287c-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7287c-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="7287c-119">S_OK</span></span>|<span data-ttu-id="7287c-120">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="7287c-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="7287c-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="7287c-121">E_POINTER</span></span>|<span data-ttu-id="7287c-122">`pwzbuffer` o `pcchBuffer` es null.</span><span class="sxs-lookup"><span data-stu-id="7287c-122">`pwzbuffer` or `pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="7287c-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="7287c-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="7287c-124">El búfer es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="7287c-124">The buffer is too small.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7287c-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7287c-125">Requirements</span></span>  
 <span data-ttu-id="7287c-126">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7287c-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7287c-127">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7287c-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7287c-128">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7287c-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7287c-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7287c-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7287c-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="7287c-130">See also</span></span>

- [<span data-ttu-id="7287c-131">ICLRMetaHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7287c-131">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="7287c-132">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="7287c-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
