---
title: "ICLRAssemblyReferenceList::IsAssemblyReferenceInList (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyReferenceList.IsAssemblyReferenceInList
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyReferenceList::IsAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList method [.NET Framework hosting]
- IsAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: 8a570813-21be-407e-92a6-7ae8de3bc728
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 923f7f4178d3c310b51ebb7e7df06040ba69f9c7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="b0e5c-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList (Método)</span><span class="sxs-lookup"><span data-stu-id="b0e5c-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>
<span data-ttu-id="b0e5c-103">Obtiene un valor que indica si el puntero proporcionado hace referencia a un ensamblado en la lista.</span><span class="sxs-lookup"><span data-stu-id="b0e5c-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0e5c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0e5c-104">Syntax</span></span>  
  
```  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b0e5c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b0e5c-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="b0e5c-106">[in] Un puntero de interfaz al ensamblado para el que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="b0e5c-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="b0e5c-107">Los valores válidos son de tipo `IAssemblyName` o `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b0e5c-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0e5c-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b0e5c-108">Return Value</span></span>  
  
|<span data-ttu-id="b0e5c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b0e5c-109">HRESULT</span></span>|<span data-ttu-id="b0e5c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0e5c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b0e5c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0e5c-111">S_OK</span></span>|<span data-ttu-id="b0e5c-112">La cadena aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="b0e5c-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="b0e5c-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b0e5c-113">S_FALSE</span></span>|<span data-ttu-id="b0e5c-114">La cadena no aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="b0e5c-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="b0e5c-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0e5c-115">E_FAIL</span></span>|<span data-ttu-id="b0e5c-116">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="b0e5c-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b0e5c-117">Cuando un método devuelve E_FAIL, common language runtime ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="b0e5c-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="b0e5c-118">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b0e5c-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b0e5c-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0e5c-119">Requirements</span></span>  
 <span data-ttu-id="b0e5c-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0e5c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0e5c-121">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b0e5c-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b0e5c-122">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b0e5c-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b0e5c-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0e5c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0e5c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0e5c-124">See Also</span></span>  
 [<span data-ttu-id="b0e5c-125">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b0e5c-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="b0e5c-126">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b0e5c-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="b0e5c-127">IHostAssemblyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b0e5c-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="b0e5c-128">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b0e5c-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
