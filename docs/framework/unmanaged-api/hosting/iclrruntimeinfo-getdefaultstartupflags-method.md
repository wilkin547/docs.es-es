---
title: ICLRRuntimeInfo::GetDefaultStartupFlags (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aeb4c9935d5e9e4063497dd56276edfe6e62752a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765587"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a><span data-ttu-id="fd0c9-102">ICLRRuntimeInfo::GetDefaultStartupFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="fd0c9-102">ICLRRuntimeInfo::GetDefaultStartupFlags Method</span></span>
<span data-ttu-id="fd0c9-103">Obtiene las marcas de inicio y el archivo de configuración de host que se usará para iniciar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fd0c9-103">Gets the startup flags and host configuration file that will be used to start the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd0c9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd0c9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd0c9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fd0c9-105">Parameters</span></span>  
 `pdwStartupFlags`  
 <span data-ttu-id="fd0c9-106">[out] Un puntero a las marcas de inicio del host que están establecidas actualmente.</span><span class="sxs-lookup"><span data-stu-id="fd0c9-106">[out] A pointer to the host startup flags that are currently set.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="fd0c9-107">[out] Un puntero a la ruta del directorio del archivo de configuración de host actual.</span><span class="sxs-lookup"><span data-stu-id="fd0c9-107">[out] A pointer to the directory path of the current host configuration file.</span></span>  
  
 `pcchHostConfigFile`  
 <span data-ttu-id="fd0c9-108">[in, out] En la entrada, el tamaño de `pwzHostConfigFile`, para evitar saturaciones de búfer.</span><span class="sxs-lookup"><span data-stu-id="fd0c9-108">[in, out] On input, the size of `pwzHostConfigFile`, to avoid buffer overruns.</span></span> <span data-ttu-id="fd0c9-109">Si `pwzHostConfigFile` es null, el método devuelve el tamaño necesario de `pwzHostConfigFile` para la asignación previa.</span><span class="sxs-lookup"><span data-stu-id="fd0c9-109">If `pwzHostConfigFile` is null, the method returns the required size of `pwzHostConfigFile` for pre-allocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd0c9-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fd0c9-110">Return Value</span></span>  
 <span data-ttu-id="fd0c9-111">Este método devuelve los siguientes HRESULT específicos, así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="fd0c9-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fd0c9-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd0c9-112">HRESULT</span></span>|<span data-ttu-id="fd0c9-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fd0c9-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd0c9-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd0c9-114">S_OK</span></span>|<span data-ttu-id="fd0c9-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="fd0c9-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd0c9-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fd0c9-116">Remarks</span></span>  
 <span data-ttu-id="fd0c9-117">Este método devuelve los valores de marca predeterminada (`STARTUP_CONCURRENT_GC` y `NULL`), o los valores proporcionados por una llamada anterior a la [SetDefaultStartupFlags (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), o los valores establecidos por cualquiera de los `CorBind*` métodos si están enlazados a este entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fd0c9-117">This method returns the default flag values (`STARTUP_CONCURRENT_GC` and `NULL`), or the values provided by a previous call to the [ICLRRuntimeInfo::SetDefaultStartupFlags method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), or the values set by any of the `CorBind*` methods if they are bound to this runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd0c9-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd0c9-118">Requirements</span></span>  
 <span data-ttu-id="fd0c9-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd0c9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd0c9-120">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="fd0c9-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fd0c9-121">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fd0c9-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd0c9-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd0c9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd0c9-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd0c9-123">See also</span></span>

- [<span data-ttu-id="fd0c9-124">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fd0c9-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="fd0c9-125">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="fd0c9-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="fd0c9-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="fd0c9-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
