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
ms.openlocfilehash: aa45c814568188a5fe93e3acd2514cb54bb0f984
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688619"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="daec9-102">ICLRRuntimeInfo::LoadLibrary (Método)</span><span class="sxs-lookup"><span data-stu-id="daec9-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>

<span data-ttu-id="daec9-103">Carga una biblioteca de .NET Framework desde el Common Language Runtime (CLR) representado por una interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="daec9-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="daec9-104">Este método reemplaza a la función [LoadLibraryShim (](loadlibraryshim-function.md) .</span><span class="sxs-lookup"><span data-stu-id="daec9-104">This method supersedes the [LoadLibraryShim](loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daec9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="daec9-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="daec9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="daec9-106">Parameters</span></span>  

 `pwzDllName`  
 <span data-ttu-id="daec9-107">de Nombre del ensamblado que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="daec9-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="daec9-108">enuncia Identificador del ensamblado cargado.</span><span class="sxs-lookup"><span data-stu-id="daec9-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="daec9-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="daec9-109">Return Value</span></span>  

 <span data-ttu-id="daec9-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="daec9-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="daec9-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="daec9-111">HRESULT</span></span>|<span data-ttu-id="daec9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="daec9-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="daec9-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="daec9-113">S_OK</span></span>|<span data-ttu-id="daec9-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="daec9-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="daec9-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="daec9-115">E_POINTER</span></span>|<span data-ttu-id="daec9-116">`pwzDllName` o `phndModule` es null.</span><span class="sxs-lookup"><span data-stu-id="daec9-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="daec9-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="daec9-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="daec9-118">No hay suficiente memoria disponible para controlar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="daec9-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="daec9-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="daec9-119">Remarks</span></span>  

 <span data-ttu-id="daec9-120">Este método solo carga los archivos dll incluidos en el paquete redistribuible de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="daec9-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="daec9-121">No puede cargar los ensamblados generados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="daec9-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daec9-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="daec9-122">Requirements</span></span>  

 <span data-ttu-id="daec9-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="daec9-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daec9-124">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="daec9-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="daec9-125">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="daec9-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="daec9-126">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daec9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daec9-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="daec9-127">See also</span></span>

- [<span data-ttu-id="daec9-128">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="daec9-128">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="daec9-129">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="daec9-129">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="daec9-130">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="daec9-130">Hosting</span></span>](index.md)
