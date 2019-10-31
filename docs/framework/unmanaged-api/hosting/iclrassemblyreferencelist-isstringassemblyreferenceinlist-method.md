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
ms.openlocfilehash: 4dc91723f009d46f9c57b1c99aa66ba7a1b127e4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126632"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="aa15c-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList (Método)</span><span class="sxs-lookup"><span data-stu-id="aa15c-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="aa15c-103">Obtiene un valor que indica si el nombre proporcionado coincide con el nombre de un ensamblado de la lista.</span><span class="sxs-lookup"><span data-stu-id="aa15c-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa15c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa15c-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa15c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aa15c-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="aa15c-106">de Nombre del ensamblado que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="aa15c-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa15c-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="aa15c-107">Return Value</span></span>  
  
|<span data-ttu-id="aa15c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aa15c-108">HRESULT</span></span>|<span data-ttu-id="aa15c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa15c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aa15c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="aa15c-110">S_OK</span></span>|<span data-ttu-id="aa15c-111">La cadena aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="aa15c-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="aa15c-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="aa15c-112">S_FALSE</span></span>|<span data-ttu-id="aa15c-113">La cadena no aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="aa15c-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="aa15c-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="aa15c-114">E_FAIL</span></span>|<span data-ttu-id="aa15c-115">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="aa15c-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="aa15c-116">Una vez que un método devuelve E_FAIL, el Common Language Runtime ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="aa15c-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="aa15c-117">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="aa15c-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa15c-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa15c-118">Requirements</span></span>  
 <span data-ttu-id="aa15c-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa15c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa15c-120">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="aa15c-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aa15c-121">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="aa15c-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa15c-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa15c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa15c-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa15c-123">See also</span></span>

- [<span data-ttu-id="aa15c-124">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa15c-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="aa15c-125">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa15c-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="aa15c-126">IHostAssemblyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa15c-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="aa15c-127">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa15c-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
