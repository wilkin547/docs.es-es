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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969915"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="8c086-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList (Método)</span><span class="sxs-lookup"><span data-stu-id="8c086-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="8c086-103">Obtiene un valor que indica si el nombre proporcionado coincide con el nombre de un ensamblado en la lista.</span><span class="sxs-lookup"><span data-stu-id="8c086-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c086-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c086-104">Syntax</span></span>  
  
```  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c086-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8c086-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="8c086-106">[in] El nombre del ensamblado para el que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="8c086-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c086-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8c086-107">Return Value</span></span>  
  
|<span data-ttu-id="8c086-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8c086-108">HRESULT</span></span>|<span data-ttu-id="8c086-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c086-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8c086-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8c086-110">S_OK</span></span>|<span data-ttu-id="8c086-111">La cadena aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="8c086-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="8c086-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="8c086-112">S_FALSE</span></span>|<span data-ttu-id="8c086-113">La cadena no aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="8c086-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="8c086-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8c086-114">E_FAIL</span></span>|<span data-ttu-id="8c086-115">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="8c086-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8c086-116">Después de un método devuelve E_FAIL, common language runtime ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="8c086-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="8c086-117">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8c086-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c086-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c086-118">Requirements</span></span>  
 <span data-ttu-id="8c086-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c086-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c086-120">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8c086-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8c086-121">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8c086-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c086-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c086-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c086-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c086-123">See also</span></span>

- [<span data-ttu-id="8c086-124">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c086-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="8c086-125">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c086-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="8c086-126">IHostAssemblyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c086-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="8c086-127">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c086-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
