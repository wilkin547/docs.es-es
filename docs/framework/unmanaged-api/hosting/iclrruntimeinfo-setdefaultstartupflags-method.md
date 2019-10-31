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
ms.openlocfilehash: 36851ac4573d0d65caffaa3f82a1f6fc8440a2d0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092754"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="4dba5-102">ICLRRuntimeInfo::SetDefaultStartupFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="4dba5-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="4dba5-103">Establece las marcas de inicio y el archivo de configuración de host que se usarán para iniciar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4dba5-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="4dba5-104">Este método reemplaza el uso del parámetro `startupFlags` en las funciones [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) y [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) .</span><span class="sxs-lookup"><span data-stu-id="4dba5-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dba5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4dba5-105">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dba5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4dba5-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="4dba5-107">de Marcas de inicio del host que se van a establecer.</span><span class="sxs-lookup"><span data-stu-id="4dba5-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="4dba5-108">Utilice las mismas marcas que con las funciones [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) y [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) .</span><span class="sxs-lookup"><span data-stu-id="4dba5-108">Use the same flags as with the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="4dba5-109">de Ruta de acceso al directorio del archivo de configuración de host que se va a establecer.</span><span class="sxs-lookup"><span data-stu-id="4dba5-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4dba5-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4dba5-110">Return Value</span></span>  
 <span data-ttu-id="4dba5-111">Este método devuelve los siguientes HRESULT específicos, así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="4dba5-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4dba5-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4dba5-112">HRESULT</span></span>|<span data-ttu-id="4dba5-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="4dba5-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4dba5-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="4dba5-114">S_OK</span></span>|<span data-ttu-id="4dba5-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="4dba5-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4dba5-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4dba5-116">Remarks</span></span>  
 <span data-ttu-id="4dba5-117">Un host multiproceso debe sincronizar las llamadas a este método.</span><span class="sxs-lookup"><span data-stu-id="4dba5-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="4dba5-118">De lo contrario, el subproceso A podría llamar al método `SetStartupFlags` después de que el subproceso B complete una llamada a `SetStartupFlags` y antes de que el subproceso B inicie el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4dba5-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dba5-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4dba5-119">Requirements</span></span>  
 <span data-ttu-id="4dba5-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4dba5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dba5-121">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="4dba5-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4dba5-122">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4dba5-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4dba5-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dba5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dba5-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="4dba5-124">See also</span></span>

- [<span data-ttu-id="4dba5-125">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4dba5-125">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="4dba5-126">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="4dba5-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="4dba5-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="4dba5-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
