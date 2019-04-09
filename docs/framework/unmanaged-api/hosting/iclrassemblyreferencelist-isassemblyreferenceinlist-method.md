---
title: ICLRAssemblyReferenceList::IsAssemblyReferenceInList (Método)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList method [.NET Framework hosting]
- IsAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: 8a570813-21be-407e-92a6-7ae8de3bc728
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6a95a636623f0b4ea75706039194572ecf1bbe0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136206"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="c7fda-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList (Método)</span><span class="sxs-lookup"><span data-stu-id="c7fda-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>
<span data-ttu-id="c7fda-103">Obtiene un valor que indica si el puntero proporcionado hace referencia a un ensamblado en la lista.</span><span class="sxs-lookup"><span data-stu-id="c7fda-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7fda-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c7fda-104">Syntax</span></span>  
  
```  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7fda-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c7fda-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="c7fda-106">[in] Un puntero de interfaz al ensamblado para el que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="c7fda-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="c7fda-107">Los valores válidos son de tipo `IAssemblyName` o `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="c7fda-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7fda-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c7fda-108">Return Value</span></span>  
  
|<span data-ttu-id="c7fda-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c7fda-109">HRESULT</span></span>|<span data-ttu-id="c7fda-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c7fda-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c7fda-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c7fda-111">S_OK</span></span>|<span data-ttu-id="c7fda-112">La cadena aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="c7fda-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="c7fda-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c7fda-113">S_FALSE</span></span>|<span data-ttu-id="c7fda-114">La cadena no aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="c7fda-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="c7fda-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c7fda-115">E_FAIL</span></span>|<span data-ttu-id="c7fda-116">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="c7fda-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c7fda-117">Después de un método devuelve E_FAIL, common language runtime ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="c7fda-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="c7fda-118">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c7fda-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c7fda-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c7fda-119">Requirements</span></span>  
 <span data-ttu-id="c7fda-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7fda-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7fda-121">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c7fda-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c7fda-122">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c7fda-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c7fda-123">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c7fda-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c7fda-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7fda-124">See also</span></span>

- [<span data-ttu-id="c7fda-125">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c7fda-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="c7fda-126">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c7fda-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="c7fda-127">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c7fda-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="c7fda-128">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c7fda-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
