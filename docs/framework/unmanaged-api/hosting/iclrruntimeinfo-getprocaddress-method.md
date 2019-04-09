---
title: ICLRRuntimeInfo::GetProcAddress (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetProcAddress
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a95b6b7e20bbcd86dedf187c932f2cf74d37cdab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199185"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="c122b-102">ICLRRuntimeInfo::GetProcAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="c122b-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>
<span data-ttu-id="c122b-103">Obtiene la dirección de una función especificada que se exportó desde common language runtime (CLR) asociado a esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="c122b-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="c122b-104">Este método reemplaza el [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="c122b-104">This method supersedes the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c122b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c122b-105">Syntax</span></span>  
  
```  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c122b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c122b-106">Parameters</span></span>  
 `pszProcName`  
 <span data-ttu-id="c122b-107">[in] El nombre de la función exportada.</span><span class="sxs-lookup"><span data-stu-id="c122b-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="c122b-108">[out] La dirección de la función exportada.</span><span class="sxs-lookup"><span data-stu-id="c122b-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c122b-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c122b-109">Return Value</span></span>  
 <span data-ttu-id="c122b-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="c122b-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c122b-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c122b-111">HRESULT</span></span>|<span data-ttu-id="c122b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c122b-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c122b-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="c122b-113">S_OK</span></span>|<span data-ttu-id="c122b-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c122b-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="c122b-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="c122b-115">E_POINTER</span></span>|`pszProcName` <span data-ttu-id="c122b-116">o `ppProc` es null.</span><span class="sxs-lookup"><span data-stu-id="c122b-116">or `ppProc` is null.</span></span>|  
|<span data-ttu-id="c122b-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="c122b-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="c122b-118">La función especificada no es una función exportada.</span><span class="sxs-lookup"><span data-stu-id="c122b-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c122b-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c122b-119">Remarks</span></span>  
 <span data-ttu-id="c122b-120">Este método provoca que el CLR que se cargó, pero no inicializado.</span><span class="sxs-lookup"><span data-stu-id="c122b-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c122b-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c122b-121">Requirements</span></span>  
 <span data-ttu-id="c122b-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c122b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c122b-123">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c122b-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c122b-124">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c122b-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c122b-125">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c122b-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c122b-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="c122b-126">See also</span></span>

- [<span data-ttu-id="c122b-127">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c122b-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="c122b-128">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="c122b-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="c122b-129">Hospedaje</span><span class="sxs-lookup"><span data-stu-id="c122b-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
