---
title: ICLRRuntimeInfo::LoadLibrary (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadLibrary
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3fe1f93c621fd567471b9a49e4aa75cb90e6e0e7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59161166"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="784ce-102">ICLRRuntimeInfo::LoadLibrary (Método)</span><span class="sxs-lookup"><span data-stu-id="784ce-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>
<span data-ttu-id="784ce-103">Carga una biblioteca de .NET Framework de common language runtime (CLR) representado por un [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="784ce-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="784ce-104">Este método reemplaza el [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="784ce-104">This method supersedes the [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="784ce-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="784ce-105">Syntax</span></span>  
  
```  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="784ce-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="784ce-106">Parameters</span></span>  
 `pwzDllName`  
 <span data-ttu-id="784ce-107">[in] El nombre del ensamblado que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="784ce-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="784ce-108">[out] Un identificador para el ensamblado cargado.</span><span class="sxs-lookup"><span data-stu-id="784ce-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="784ce-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="784ce-109">Return Value</span></span>  
 <span data-ttu-id="784ce-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="784ce-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="784ce-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="784ce-111">HRESULT</span></span>|<span data-ttu-id="784ce-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="784ce-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="784ce-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="784ce-113">S_OK</span></span>|<span data-ttu-id="784ce-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="784ce-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="784ce-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="784ce-115">E_POINTER</span></span>|`pwzDllName` <span data-ttu-id="784ce-116">o `phndModule` es null.</span><span class="sxs-lookup"><span data-stu-id="784ce-116">or `phndModule` is null.</span></span>|  
|<span data-ttu-id="784ce-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="784ce-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="784ce-118">No hay suficiente memoria disponible para atender la solicitud.</span><span class="sxs-lookup"><span data-stu-id="784ce-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="784ce-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="784ce-119">Remarks</span></span>  
 <span data-ttu-id="784ce-120">Este método solo carga los archivos DLL incluidos en el paquete redistribuible de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="784ce-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="784ce-121">No se puede cargar los ensamblados generados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="784ce-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="784ce-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="784ce-122">Requirements</span></span>  
 <span data-ttu-id="784ce-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="784ce-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="784ce-124">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="784ce-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="784ce-125">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="784ce-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="784ce-126">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="784ce-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="784ce-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="784ce-127">See also</span></span>

- [<span data-ttu-id="784ce-128">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="784ce-128">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="784ce-129">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="784ce-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="784ce-130">Hospedaje</span><span class="sxs-lookup"><span data-stu-id="784ce-130">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
