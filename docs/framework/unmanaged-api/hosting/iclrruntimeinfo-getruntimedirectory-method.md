---
title: "ICLRRuntimeInfo::GetRuntimeDirectory (Método)"
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
- ICLRRuntimeInfo.GetRuntimeDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f185ed474234a33988e1946b2f69da373096e19b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="eb8e1-102">ICLRRuntimeInfo::GetRuntimeDirectory (Método)</span><span class="sxs-lookup"><span data-stu-id="eb8e1-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="eb8e1-103">Obtiene el directorio de instalación de common language runtime (CLR) asociado a esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="eb8e1-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="eb8e1-104">Este método reemplaza a la [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) función incluida en las versiones de .NET Framework 2.0, 3.0 y 3.5.</span><span class="sxs-lookup"><span data-stu-id="eb8e1-104">This method supersedes the [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb8e1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb8e1-105">Syntax</span></span>  
  
```  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eb8e1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eb8e1-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="eb8e1-107">[out] Devuelve el directorio de instalación de CLR.</span><span class="sxs-lookup"><span data-stu-id="eb8e1-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="eb8e1-108">La ruta de acceso de instalación está completa; Por ejemplo, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span><span class="sxs-lookup"><span data-stu-id="eb8e1-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="eb8e1-109">[entrada, salida] Especifica el tamaño de `pwzBuffer` para evitar saturaciones del búfer.</span><span class="sxs-lookup"><span data-stu-id="eb8e1-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="eb8e1-110">Si `pwzBuffer` es null, `pchBuffer` devuelve el tamaño necesario de `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="eb8e1-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb8e1-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="eb8e1-111">Return Value</span></span>  
 <span data-ttu-id="eb8e1-112">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="eb8e1-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="eb8e1-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eb8e1-113">HRESULT</span></span>|<span data-ttu-id="eb8e1-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb8e1-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eb8e1-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="eb8e1-115">S_OK</span></span>|<span data-ttu-id="eb8e1-116">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="eb8e1-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="eb8e1-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="eb8e1-117">E_POINTER</span></span>|<span data-ttu-id="eb8e1-118">`pwzBuffer` o `pchBuffer` es null.</span><span class="sxs-lookup"><span data-stu-id="eb8e1-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb8e1-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eb8e1-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb8e1-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eb8e1-120">Requirements</span></span>  
 <span data-ttu-id="eb8e1-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb8e1-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb8e1-122">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="eb8e1-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="eb8e1-123">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eb8e1-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eb8e1-124">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb8e1-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb8e1-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb8e1-125">See Also</span></span>  
 [<span data-ttu-id="eb8e1-126">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="eb8e1-126">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="eb8e1-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="eb8e1-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
