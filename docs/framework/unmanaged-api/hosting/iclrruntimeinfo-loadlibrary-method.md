---
title: "ICLRRuntimeInfo::LoadLibrary (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.LoadLibrary
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c1d943f45a4e665836f376bddf65d84329c1900e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="9ab74-102">ICLRRuntimeInfo::LoadLibrary (Método)</span><span class="sxs-lookup"><span data-stu-id="9ab74-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>
<span data-ttu-id="9ab74-103">Carga una biblioteca de .NET Framework de common language runtime (CLR) representado por un [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="9ab74-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="9ab74-104">Este método reemplaza a la [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="9ab74-104">This method supersedes the [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ab74-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ab74-105">Syntax</span></span>  
  
```  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ab74-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9ab74-106">Parameters</span></span>  
 `pwzDllName`  
 <span data-ttu-id="9ab74-107">[in] El nombre del ensamblado que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="9ab74-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="9ab74-108">[out] Un identificador para el ensamblado cargado.</span><span class="sxs-lookup"><span data-stu-id="9ab74-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ab74-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9ab74-109">Return Value</span></span>  
 <span data-ttu-id="9ab74-110">Este método devuelve los siguientes HRESULT específicos así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="9ab74-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9ab74-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9ab74-111">HRESULT</span></span>|<span data-ttu-id="9ab74-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ab74-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9ab74-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="9ab74-113">S_OK</span></span>|<span data-ttu-id="9ab74-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="9ab74-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="9ab74-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="9ab74-115">E_POINTER</span></span>|<span data-ttu-id="9ab74-116">`pwzDllName` o `phndModule` es null.</span><span class="sxs-lookup"><span data-stu-id="9ab74-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="9ab74-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9ab74-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="9ab74-118">No hay suficiente memoria disponible para atender la solicitud.</span><span class="sxs-lookup"><span data-stu-id="9ab74-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ab74-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9ab74-119">Remarks</span></span>  
 <span data-ttu-id="9ab74-120">Este método solo carga archivos DLL incluidos en el paquete redistribuible de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9ab74-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="9ab74-121">No se pueden cargar ensamblados generados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="9ab74-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ab74-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ab74-122">Requirements</span></span>  
 <span data-ttu-id="9ab74-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ab74-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ab74-124">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9ab74-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9ab74-125">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9ab74-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ab74-126">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ab74-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ab74-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ab74-127">See Also</span></span>  
 [<span data-ttu-id="9ab74-128">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9ab74-128">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="9ab74-129">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="9ab74-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="9ab74-130">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="9ab74-130">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
