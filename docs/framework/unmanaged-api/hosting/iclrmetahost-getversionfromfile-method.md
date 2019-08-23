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
ms.openlocfilehash: dd5d2e820bd1d733bb4ab968a89174124bc91357
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962934"
---
# <a name="iclrmetahostgetversionfromfile-method"></a><span data-ttu-id="28c56-102">ICLRMetaHost::GetVersionFromFile (Método)</span><span class="sxs-lookup"><span data-stu-id="28c56-102">ICLRMetaHost::GetVersionFromFile Method</span></span>
<span data-ttu-id="28c56-103">Obtiene la versión de compilación .NET Framework original de un ensamblado (almacenada en los metadatos), dada su ruta de acceso al archivo.</span><span class="sxs-lookup"><span data-stu-id="28c56-103">Gets an assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="28c56-104">Este método reemplaza a la función [GetFileVersion (](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) .</span><span class="sxs-lookup"><span data-stu-id="28c56-104">This method supersedes the [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28c56-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28c56-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28c56-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="28c56-106">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="28c56-107">de Ruta de acceso completa del archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="28c56-107">[in] The complete assembly file path.</span></span>  
  
 `pwzbuffer`  
 <span data-ttu-id="28c56-108">enuncia La versión de compilación de .NET Framework almacenada en los metadatos, en el formato "v*A*. *B* [. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="28c56-108">[out] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="28c56-109">*A*, *B*y *X* son números decimales que corresponden a la versión principal, la versión secundaria y el número de compilación.</span><span class="sxs-lookup"><span data-stu-id="28c56-109">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="28c56-110">La longitud de esta cadena se limita a MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="28c56-110">The length of this string is limited to MAX_PATH.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="28c56-111">Esta salida coincide con el nombre de directorio para la versión .NET Framework, tal y como aparece en C:\Windows\Microsoft.NET\Framework.</span><span class="sxs-lookup"><span data-stu-id="28c56-111">This output matches the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="28c56-112">Los valores de ejemplo son "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" y "v 4.0. *X*", donde *X* depende del número de compilación instalado.</span><span class="sxs-lookup"><span data-stu-id="28c56-112">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="28c56-113">Tenga en cuenta que el prefijo "v" es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="28c56-113">Note that the "v" prefix is required.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="28c56-114">[in, out] Tamaño de para `pwzbuffer` evitar las saturaciones del búfer.</span><span class="sxs-lookup"><span data-stu-id="28c56-114">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28c56-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="28c56-115">Return Value</span></span>  
 <span data-ttu-id="28c56-116">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="28c56-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="28c56-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="28c56-117">HRESULT</span></span>|<span data-ttu-id="28c56-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="28c56-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="28c56-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="28c56-119">S_OK</span></span>|<span data-ttu-id="28c56-120">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="28c56-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="28c56-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="28c56-121">E_POINTER</span></span>|<span data-ttu-id="28c56-122">`pwzbuffer` o `pcchBuffer` es null.</span><span class="sxs-lookup"><span data-stu-id="28c56-122">`pwzbuffer` or `pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="28c56-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="28c56-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="28c56-124">El búfer es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="28c56-124">The buffer is too small.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="28c56-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28c56-125">Requirements</span></span>  
 <span data-ttu-id="28c56-126">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28c56-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28c56-127">**Encabezado**: Metahost. h</span><span class="sxs-lookup"><span data-stu-id="28c56-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="28c56-128">**Biblioteca** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="28c56-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28c56-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28c56-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28c56-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="28c56-130">See also</span></span>

- [<span data-ttu-id="28c56-131">ICLRMetaHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="28c56-131">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="28c56-132">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="28c56-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
