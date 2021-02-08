---
description: 'Más información acerca de: ICLRRuntimeInfo:: LoadLibrary (método)'
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
ms.openlocfilehash: 47557934868c7c1b68b23bf4eded0e90705d7252
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785060"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="9d78e-103">ICLRRuntimeInfo::LoadLibrary (Método)</span><span class="sxs-lookup"><span data-stu-id="9d78e-103">ICLRRuntimeInfo::LoadLibrary Method</span></span>

<span data-ttu-id="9d78e-104">Carga una biblioteca de .NET Framework desde el Common Language Runtime (CLR) representado por una interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9d78e-104">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="9d78e-105">Este método reemplaza a la función [LoadLibraryShim (](loadlibraryshim-function.md) .</span><span class="sxs-lookup"><span data-stu-id="9d78e-105">This method supersedes the [LoadLibraryShim](loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d78e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d78e-106">Syntax</span></span>  
  
```cpp  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d78e-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9d78e-107">Parameters</span></span>  

 `pwzDllName`  
 <span data-ttu-id="9d78e-108">de Nombre del ensamblado que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="9d78e-108">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="9d78e-109">enuncia Identificador del ensamblado cargado.</span><span class="sxs-lookup"><span data-stu-id="9d78e-109">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d78e-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9d78e-110">Return Value</span></span>  

 <span data-ttu-id="9d78e-111">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="9d78e-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9d78e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9d78e-112">HRESULT</span></span>|<span data-ttu-id="9d78e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d78e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9d78e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9d78e-114">S_OK</span></span>|<span data-ttu-id="9d78e-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="9d78e-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="9d78e-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="9d78e-116">E_POINTER</span></span>|<span data-ttu-id="9d78e-117">`pwzDllName` o `phndModule` es null.</span><span class="sxs-lookup"><span data-stu-id="9d78e-117">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="9d78e-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9d78e-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="9d78e-119">No hay suficiente memoria disponible para controlar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="9d78e-119">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d78e-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9d78e-120">Remarks</span></span>  

 <span data-ttu-id="9d78e-121">Este método solo carga los archivos dll incluidos en el paquete redistribuible de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9d78e-121">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="9d78e-122">No puede cargar los ensamblados generados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="9d78e-122">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d78e-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d78e-123">Requirements</span></span>  

 <span data-ttu-id="9d78e-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d78e-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d78e-125">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="9d78e-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9d78e-126">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9d78e-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d78e-127">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d78e-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d78e-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d78e-128">See also</span></span>

- [<span data-ttu-id="9d78e-129">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9d78e-129">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="9d78e-130">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="9d78e-130">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="9d78e-131">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="9d78e-131">Hosting</span></span>](index.md)
