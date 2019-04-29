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
ms.openlocfilehash: d3174cf3b4f4f4ac4b2c8e69030357eb1e46cf3c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771636"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="fbffe-102">ICLRRuntimeInfo::SetDefaultStartupFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="fbffe-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="fbffe-103">Establece las marcas de inicio y el archivo de configuración de host que se usará para iniciar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fbffe-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="fbffe-104">Este método reemplaza el uso de la `startupFlags` parámetro en el [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) y [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) funciones.</span><span class="sxs-lookup"><span data-stu-id="fbffe-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbffe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fbffe-105">Syntax</span></span>  
  
```  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbffe-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fbffe-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="fbffe-107">[in] Las marcas de inicio del host para establecer.</span><span class="sxs-lookup"><span data-stu-id="fbffe-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="fbffe-108">Use las mismas marcas como con el [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) y [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) funciones.</span><span class="sxs-lookup"><span data-stu-id="fbffe-108">Use the same flags as with the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="fbffe-109">[in] La ruta del directorio del archivo de configuración de host para establecer.</span><span class="sxs-lookup"><span data-stu-id="fbffe-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fbffe-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fbffe-110">Return Value</span></span>  
 <span data-ttu-id="fbffe-111">Este método devuelve los siguientes HRESULT específicos, así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="fbffe-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fbffe-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fbffe-112">HRESULT</span></span>|<span data-ttu-id="fbffe-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="fbffe-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fbffe-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="fbffe-114">S_OK</span></span>|<span data-ttu-id="fbffe-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="fbffe-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbffe-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fbffe-116">Remarks</span></span>  
 <span data-ttu-id="fbffe-117">Un host multiproceso debe sincronizar las llamadas a este método.</span><span class="sxs-lookup"><span data-stu-id="fbffe-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="fbffe-118">En caso contrario, podría llamar un subproceso a la `SetStartupFlags` método después de que el subproceso B completa una llamada a `SetStartupFlags` y antes de que el subproceso B inicia el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fbffe-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbffe-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fbffe-119">Requirements</span></span>  
 <span data-ttu-id="fbffe-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbffe-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbffe-121">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="fbffe-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fbffe-122">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fbffe-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fbffe-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbffe-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbffe-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbffe-124">See also</span></span>

- [<span data-ttu-id="fbffe-125">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fbffe-125">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="fbffe-126">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="fbffe-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="fbffe-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="fbffe-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
