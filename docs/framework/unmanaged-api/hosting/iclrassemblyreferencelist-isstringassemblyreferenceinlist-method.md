---
title: ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList (Método)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsStringAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList method [.NET Framework hosting]
- IsStringAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: e6121cc3-2f11-42c7-bdae-47808581ff71
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de17a91b5093372579a4d9435532a95406addd0a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216904"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="03f73-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList (Método)</span><span class="sxs-lookup"><span data-stu-id="03f73-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="03f73-103">Obtiene un valor que indica si el nombre proporcionado coincide con el nombre de un ensamblado en la lista.</span><span class="sxs-lookup"><span data-stu-id="03f73-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03f73-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03f73-104">Syntax</span></span>  
  
```  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03f73-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="03f73-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="03f73-106">[in] El nombre del ensamblado para el que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="03f73-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03f73-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="03f73-107">Return Value</span></span>  
  
|<span data-ttu-id="03f73-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="03f73-108">HRESULT</span></span>|<span data-ttu-id="03f73-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="03f73-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="03f73-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="03f73-110">S_OK</span></span>|<span data-ttu-id="03f73-111">La cadena aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="03f73-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="03f73-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="03f73-112">S_FALSE</span></span>|<span data-ttu-id="03f73-113">La cadena no aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="03f73-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="03f73-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="03f73-114">E_FAIL</span></span>|<span data-ttu-id="03f73-115">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="03f73-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="03f73-116">Después de un método devuelve E_FAIL, common language runtime ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="03f73-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="03f73-117">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="03f73-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="03f73-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03f73-118">Requirements</span></span>  
 <span data-ttu-id="03f73-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03f73-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03f73-120">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="03f73-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="03f73-121">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="03f73-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="03f73-122">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="03f73-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="03f73-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="03f73-123">See also</span></span>

- [<span data-ttu-id="03f73-124">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="03f73-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="03f73-125">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="03f73-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="03f73-126">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="03f73-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="03f73-127">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="03f73-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
