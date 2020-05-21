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
ms.openlocfilehash: 09c80c3a56d86943ebe00e5222bb5452ab44e150
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762180"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="cf906-102">ICLRRuntimeInfo::LoadLibrary (Método)</span><span class="sxs-lookup"><span data-stu-id="cf906-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>
<span data-ttu-id="cf906-103">Carga una biblioteca de .NET Framework desde el Common Language Runtime (CLR) representado por una interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="cf906-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="cf906-104">Este método reemplaza a la función [LoadLibraryShim (](loadlibraryshim-function.md) .</span><span class="sxs-lookup"><span data-stu-id="cf906-104">This method supersedes the [LoadLibraryShim](loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf906-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf906-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf906-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf906-106">Parameters</span></span>  
 `pwzDllName`  
 <span data-ttu-id="cf906-107">de Nombre del ensamblado que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="cf906-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="cf906-108">enuncia Identificador del ensamblado cargado.</span><span class="sxs-lookup"><span data-stu-id="cf906-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf906-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cf906-109">Return Value</span></span>  
 <span data-ttu-id="cf906-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="cf906-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="cf906-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cf906-111">HRESULT</span></span>|<span data-ttu-id="cf906-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="cf906-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cf906-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="cf906-113">S_OK</span></span>|<span data-ttu-id="cf906-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="cf906-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="cf906-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="cf906-115">E_POINTER</span></span>|<span data-ttu-id="cf906-116">`pwzDllName` o `phndModule` es null.</span><span class="sxs-lookup"><span data-stu-id="cf906-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="cf906-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="cf906-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="cf906-118">No hay suficiente memoria disponible para controlar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="cf906-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf906-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cf906-119">Remarks</span></span>  
 <span data-ttu-id="cf906-120">Este método solo carga los archivos dll incluidos en el paquete redistribuible de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cf906-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="cf906-121">No puede cargar los ensamblados generados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="cf906-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf906-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf906-122">Requirements</span></span>  
 <span data-ttu-id="cf906-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf906-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf906-124">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="cf906-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="cf906-125">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cf906-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cf906-126">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf906-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf906-127">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="cf906-127">See also</span></span>

- [<span data-ttu-id="cf906-128">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf906-128">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="cf906-129">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="cf906-129">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="cf906-130">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="cf906-130">Hosting</span></span>](index.md)
