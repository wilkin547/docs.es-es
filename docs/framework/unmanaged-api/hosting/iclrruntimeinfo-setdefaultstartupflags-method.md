---
description: 'Más información acerca de: ICLRRuntimeInfo:: SetDefaultStartupFlags ((método)'
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
ms.openlocfilehash: eb839b2ff71836adc1b3858092f7caf5787275b1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785047"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="f29b3-103">ICLRRuntimeInfo::SetDefaultStartupFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="f29b3-103">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>

<span data-ttu-id="f29b3-104">Establece las marcas de inicio y el archivo de configuración de host que se usarán para iniciar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f29b3-104">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="f29b3-105">Este método reemplaza el uso del `startupFlags` parámetro en las funciones [CorBindToRuntimeEx](corbindtoruntimeex-function.md) y [CorBindToRuntimeHost](corbindtoruntimehost-function.md) .</span><span class="sxs-lookup"><span data-stu-id="f29b3-105">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f29b3-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f29b3-106">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f29b3-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f29b3-107">Parameters</span></span>  

 `dwStartupFlags`  
 <span data-ttu-id="f29b3-108">de Marcas de inicio del host que se van a establecer.</span><span class="sxs-lookup"><span data-stu-id="f29b3-108">[in] The host startup flags to set.</span></span> <span data-ttu-id="f29b3-109">Utilice las mismas marcas que con las funciones [CorBindToRuntimeEx](corbindtoruntimeex-function.md) y [CorBindToRuntimeHost](corbindtoruntimehost-function.md) .</span><span class="sxs-lookup"><span data-stu-id="f29b3-109">Use the same flags as with the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="f29b3-110">de Ruta de acceso al directorio del archivo de configuración de host que se va a establecer.</span><span class="sxs-lookup"><span data-stu-id="f29b3-110">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f29b3-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f29b3-111">Return Value</span></span>  

 <span data-ttu-id="f29b3-112">Este método devuelve los siguientes HRESULT específicos, así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="f29b3-112">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f29b3-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f29b3-113">HRESULT</span></span>|<span data-ttu-id="f29b3-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="f29b3-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f29b3-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="f29b3-115">S_OK</span></span>|<span data-ttu-id="f29b3-116">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="f29b3-116">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f29b3-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f29b3-117">Remarks</span></span>  

 <span data-ttu-id="f29b3-118">Un host multiproceso debe sincronizar las llamadas a este método.</span><span class="sxs-lookup"><span data-stu-id="f29b3-118">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="f29b3-119">De lo contrario, el subproceso A podría llamar al método después de que el `SetStartupFlags` subproceso b complete una llamada a `SetStartupFlags` y antes de que el subproceso b inicie el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f29b3-119">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f29b3-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f29b3-120">Requirements</span></span>  

 <span data-ttu-id="f29b3-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f29b3-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f29b3-122">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="f29b3-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f29b3-123">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f29b3-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f29b3-124">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f29b3-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f29b3-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="f29b3-125">See also</span></span>

- [<span data-ttu-id="f29b3-126">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f29b3-126">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="f29b3-127">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="f29b3-127">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="f29b3-128">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="f29b3-128">Hosting</span></span>](index.md)
