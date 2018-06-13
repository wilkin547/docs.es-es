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
ms.openlocfilehash: ad7230731775cbc56dd0f1eaed72df19512d3733
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432601"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="bd296-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList (Método)</span><span class="sxs-lookup"><span data-stu-id="bd296-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="bd296-103">Obtiene un valor que indica si el nombre proporcionado coincide con el nombre de un ensamblado en la lista.</span><span class="sxs-lookup"><span data-stu-id="bd296-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd296-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd296-104">Syntax</span></span>  
  
```  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd296-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bd296-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="bd296-106">[in] El nombre del ensamblado para el que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="bd296-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd296-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bd296-107">Return Value</span></span>  
  
|<span data-ttu-id="bd296-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bd296-108">HRESULT</span></span>|<span data-ttu-id="bd296-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd296-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bd296-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="bd296-110">S_OK</span></span>|<span data-ttu-id="bd296-111">La cadena aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="bd296-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="bd296-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="bd296-112">S_FALSE</span></span>|<span data-ttu-id="bd296-113">La cadena no aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="bd296-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="bd296-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bd296-114">E_FAIL</span></span>|<span data-ttu-id="bd296-115">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="bd296-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bd296-116">Cuando un método devuelve E_FAIL, common language runtime ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="bd296-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="bd296-117">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bd296-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bd296-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd296-118">Requirements</span></span>  
 <span data-ttu-id="bd296-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd296-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd296-120">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bd296-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bd296-121">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bd296-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd296-122">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd296-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd296-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd296-123">See Also</span></span>  
 [<span data-ttu-id="bd296-124">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bd296-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="bd296-125">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bd296-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="bd296-126">IHostAssemblyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bd296-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="bd296-127">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bd296-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
