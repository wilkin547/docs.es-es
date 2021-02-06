---
description: 'Más información acerca de: ICLRRuntimeInfo:: Getdefaultstartupflags ((método)'
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
ms.openlocfilehash: c6afb19319fd24d499c2c216f2ce0adc2e7a886c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637185"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a><span data-ttu-id="1fd01-103">ICLRRuntimeInfo::GetDefaultStartupFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="1fd01-103">ICLRRuntimeInfo::GetDefaultStartupFlags Method</span></span>

<span data-ttu-id="1fd01-104">Obtiene las marcas de inicio y el archivo de configuración de host que se usarán para iniciar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1fd01-104">Gets the startup flags and host configuration file that will be used to start the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fd01-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1fd01-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fd01-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1fd01-106">Parameters</span></span>  

 `pdwStartupFlags`  
 <span data-ttu-id="1fd01-107">enuncia Puntero a las marcas de inicio del host que están establecidas actualmente.</span><span class="sxs-lookup"><span data-stu-id="1fd01-107">[out] A pointer to the host startup flags that are currently set.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="1fd01-108">enuncia Puntero a la ruta de acceso al directorio del archivo de configuración del host actual.</span><span class="sxs-lookup"><span data-stu-id="1fd01-108">[out] A pointer to the directory path of the current host configuration file.</span></span>  
  
 `pcchHostConfigFile`  
 <span data-ttu-id="1fd01-109">[in, out] En la entrada, el tamaño de `pwzHostConfigFile` , para evitar las saturaciones del búfer.</span><span class="sxs-lookup"><span data-stu-id="1fd01-109">[in, out] On input, the size of `pwzHostConfigFile`, to avoid buffer overruns.</span></span> <span data-ttu-id="1fd01-110">Si `pwzHostConfigFile` es null, el método devuelve el tamaño necesario de `pwzHostConfigFile` para la asignación previa.</span><span class="sxs-lookup"><span data-stu-id="1fd01-110">If `pwzHostConfigFile` is null, the method returns the required size of `pwzHostConfigFile` for pre-allocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1fd01-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1fd01-111">Return Value</span></span>  

 <span data-ttu-id="1fd01-112">Este método devuelve los siguientes HRESULT específicos, así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="1fd01-112">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1fd01-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1fd01-113">HRESULT</span></span>|<span data-ttu-id="1fd01-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="1fd01-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1fd01-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="1fd01-115">S_OK</span></span>|<span data-ttu-id="1fd01-116">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="1fd01-116">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fd01-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1fd01-117">Remarks</span></span>  

 <span data-ttu-id="1fd01-118">Este método devuelve los valores de marca predeterminados ( `STARTUP_CONCURRENT_GC` y `NULL` ), o los valores proporcionados por una llamada anterior al [método ICLRRuntimeInfo:: SetDefaultStartupFlags (](iclrruntimeinfo-setdefaultstartupflags-method.md), o los valores establecidos por cualquiera de los `CorBind*` métodos si están enlazados a este Runtime.</span><span class="sxs-lookup"><span data-stu-id="1fd01-118">This method returns the default flag values (`STARTUP_CONCURRENT_GC` and `NULL`), or the values provided by a previous call to the [ICLRRuntimeInfo::SetDefaultStartupFlags method](iclrruntimeinfo-setdefaultstartupflags-method.md), or the values set by any of the `CorBind*` methods if they are bound to this runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fd01-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1fd01-119">Requirements</span></span>  

 <span data-ttu-id="1fd01-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fd01-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fd01-121">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="1fd01-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1fd01-122">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1fd01-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1fd01-123">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fd01-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fd01-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="1fd01-124">See also</span></span>

- [<span data-ttu-id="1fd01-125">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1fd01-125">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="1fd01-126">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="1fd01-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="1fd01-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="1fd01-127">Hosting</span></span>](index.md)
