---
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
ms.openlocfilehash: 2f828a3720f7313ee9cb851c6adae78bd5ea4fe8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732102"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a><span data-ttu-id="11f5b-102">ICLRRuntimeInfo::GetDefaultStartupFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="11f5b-102">ICLRRuntimeInfo::GetDefaultStartupFlags Method</span></span>

<span data-ttu-id="11f5b-103">Obtiene las marcas de inicio y el archivo de configuración de host que se usarán para iniciar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="11f5b-103">Gets the startup flags and host configuration file that will be used to start the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11f5b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11f5b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11f5b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="11f5b-105">Parameters</span></span>  

 `pdwStartupFlags`  
 <span data-ttu-id="11f5b-106">enuncia Puntero a las marcas de inicio del host que están establecidas actualmente.</span><span class="sxs-lookup"><span data-stu-id="11f5b-106">[out] A pointer to the host startup flags that are currently set.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="11f5b-107">enuncia Puntero a la ruta de acceso al directorio del archivo de configuración del host actual.</span><span class="sxs-lookup"><span data-stu-id="11f5b-107">[out] A pointer to the directory path of the current host configuration file.</span></span>  
  
 `pcchHostConfigFile`  
 <span data-ttu-id="11f5b-108">[in, out] En la entrada, el tamaño de `pwzHostConfigFile` , para evitar las saturaciones del búfer.</span><span class="sxs-lookup"><span data-stu-id="11f5b-108">[in, out] On input, the size of `pwzHostConfigFile`, to avoid buffer overruns.</span></span> <span data-ttu-id="11f5b-109">Si `pwzHostConfigFile` es null, el método devuelve el tamaño necesario de `pwzHostConfigFile` para la asignación previa.</span><span class="sxs-lookup"><span data-stu-id="11f5b-109">If `pwzHostConfigFile` is null, the method returns the required size of `pwzHostConfigFile` for pre-allocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11f5b-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="11f5b-110">Return Value</span></span>  

 <span data-ttu-id="11f5b-111">Este método devuelve los siguientes HRESULT específicos, así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="11f5b-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="11f5b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="11f5b-112">HRESULT</span></span>|<span data-ttu-id="11f5b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="11f5b-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="11f5b-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="11f5b-114">S_OK</span></span>|<span data-ttu-id="11f5b-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="11f5b-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11f5b-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="11f5b-116">Remarks</span></span>  

 <span data-ttu-id="11f5b-117">Este método devuelve los valores de marca predeterminados ( `STARTUP_CONCURRENT_GC` y `NULL` ), o los valores proporcionados por una llamada anterior al [método ICLRRuntimeInfo:: SetDefaultStartupFlags (](iclrruntimeinfo-setdefaultstartupflags-method.md), o los valores establecidos por cualquiera de los `CorBind*` métodos si están enlazados a este Runtime.</span><span class="sxs-lookup"><span data-stu-id="11f5b-117">This method returns the default flag values (`STARTUP_CONCURRENT_GC` and `NULL`), or the values provided by a previous call to the [ICLRRuntimeInfo::SetDefaultStartupFlags method](iclrruntimeinfo-setdefaultstartupflags-method.md), or the values set by any of the `CorBind*` methods if they are bound to this runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11f5b-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11f5b-118">Requirements</span></span>  

 <span data-ttu-id="11f5b-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11f5b-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11f5b-120">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="11f5b-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="11f5b-121">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="11f5b-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11f5b-122">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11f5b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11f5b-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="11f5b-123">See also</span></span>

- [<span data-ttu-id="11f5b-124">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="11f5b-124">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="11f5b-125">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="11f5b-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="11f5b-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="11f5b-126">Hosting</span></span>](index.md)
