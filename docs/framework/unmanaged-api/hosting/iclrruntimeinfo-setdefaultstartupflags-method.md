---
title: ICLRRuntimeInfo::SetDefaultStartupFlags (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.SetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b0871636f816d62c1f65c74d22014d74fb1fb97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433284"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="6060a-102">ICLRRuntimeInfo::SetDefaultStartupFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="6060a-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="6060a-103">Establece las marcas de inicio y el archivo de configuración de host que se usarán para iniciar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6060a-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="6060a-104">Este método reemplaza el uso de la `startupFlags` parámetro en el [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) y [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) funciones.</span><span class="sxs-lookup"><span data-stu-id="6060a-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6060a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6060a-105">Syntax</span></span>  
  
```  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6060a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6060a-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="6060a-107">[in] Las marcas de inicio de host para establecer.</span><span class="sxs-lookup"><span data-stu-id="6060a-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="6060a-108">Use las mismas marcas como con la [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) y [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) funciones.</span><span class="sxs-lookup"><span data-stu-id="6060a-108">Use the same flags as with the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="6060a-109">[in] La ruta del directorio del archivo de configuración de host para establecer.</span><span class="sxs-lookup"><span data-stu-id="6060a-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6060a-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6060a-110">Return Value</span></span>  
 <span data-ttu-id="6060a-111">Este método devuelve los siguientes HRESULT específicos, así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="6060a-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6060a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6060a-112">HRESULT</span></span>|<span data-ttu-id="6060a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="6060a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6060a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="6060a-114">S_OK</span></span>|<span data-ttu-id="6060a-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="6060a-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6060a-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6060a-116">Remarks</span></span>  
 <span data-ttu-id="6060a-117">Un host multiproceso debería sincronizar las llamadas a este método.</span><span class="sxs-lookup"><span data-stu-id="6060a-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="6060a-118">En caso contrario, un subproceso puede llamar a la `SetStartupFlags` método después de que el subproceso B finaliza una llamada a `SetStartupFlags` y antes de que el subproceso B inicia el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6060a-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6060a-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6060a-119">Requirements</span></span>  
 <span data-ttu-id="6060a-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6060a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6060a-121">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6060a-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6060a-122">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6060a-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6060a-123">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6060a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6060a-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="6060a-124">See Also</span></span>  
 [<span data-ttu-id="6060a-125">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6060a-125">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="6060a-126">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="6060a-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="6060a-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="6060a-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
