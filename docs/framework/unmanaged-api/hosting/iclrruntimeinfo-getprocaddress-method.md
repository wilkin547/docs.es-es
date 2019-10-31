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
ms.openlocfilehash: cedda39aeebc62c6bf43f42ae2daf6f6f515fd27
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120271"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="04301-102">ICLRRuntimeInfo::GetProcAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="04301-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>
<span data-ttu-id="04301-103">Obtiene la dirección de una función especificada que se exportó desde el Common Language Runtime (CLR) asociado a esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="04301-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="04301-104">Este método reemplaza a la función [GetRealProcAddress (](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) .</span><span class="sxs-lookup"><span data-stu-id="04301-104">This method supersedes the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04301-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04301-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04301-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="04301-106">Parameters</span></span>  
 `pszProcName`  
 <span data-ttu-id="04301-107">de Nombre de la función exportada.</span><span class="sxs-lookup"><span data-stu-id="04301-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="04301-108">enuncia Dirección de la función exportada.</span><span class="sxs-lookup"><span data-stu-id="04301-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04301-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="04301-109">Return Value</span></span>  
 <span data-ttu-id="04301-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="04301-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="04301-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="04301-111">HRESULT</span></span>|<span data-ttu-id="04301-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="04301-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="04301-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="04301-113">S_OK</span></span>|<span data-ttu-id="04301-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="04301-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="04301-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="04301-115">E_POINTER</span></span>|<span data-ttu-id="04301-116">`pszProcName` o `ppProc` es null.</span><span class="sxs-lookup"><span data-stu-id="04301-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="04301-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="04301-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="04301-118">La función especificada no es una función exportada.</span><span class="sxs-lookup"><span data-stu-id="04301-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04301-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="04301-119">Remarks</span></span>  
 <span data-ttu-id="04301-120">Este método hace que el CLR se cargue pero no se inicialice.</span><span class="sxs-lookup"><span data-stu-id="04301-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04301-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04301-121">Requirements</span></span>  
 <span data-ttu-id="04301-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04301-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04301-123">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="04301-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="04301-124">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="04301-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04301-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04301-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04301-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="04301-126">See also</span></span>

- [<span data-ttu-id="04301-127">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="04301-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="04301-128">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="04301-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="04301-129">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="04301-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
