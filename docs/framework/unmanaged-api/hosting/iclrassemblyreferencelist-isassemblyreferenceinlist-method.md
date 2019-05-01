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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969928"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="9a1fa-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList (Método)</span><span class="sxs-lookup"><span data-stu-id="9a1fa-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>
<span data-ttu-id="9a1fa-103">Obtiene un valor que indica si el puntero proporcionado hace referencia a un ensamblado en la lista.</span><span class="sxs-lookup"><span data-stu-id="9a1fa-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a1fa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a1fa-104">Syntax</span></span>  
  
```  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a1fa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9a1fa-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="9a1fa-106">[in] Un puntero de interfaz al ensamblado para el que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="9a1fa-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="9a1fa-107">Los valores válidos son de tipo `IAssemblyName` o `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="9a1fa-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a1fa-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9a1fa-108">Return Value</span></span>  
  
|<span data-ttu-id="9a1fa-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9a1fa-109">HRESULT</span></span>|<span data-ttu-id="9a1fa-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a1fa-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9a1fa-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a1fa-111">S_OK</span></span>|<span data-ttu-id="9a1fa-112">La cadena aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="9a1fa-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="9a1fa-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="9a1fa-113">S_FALSE</span></span>|<span data-ttu-id="9a1fa-114">La cadena no aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="9a1fa-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="9a1fa-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9a1fa-115">E_FAIL</span></span>|<span data-ttu-id="9a1fa-116">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="9a1fa-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9a1fa-117">Después de un método devuelve E_FAIL, common language runtime ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="9a1fa-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="9a1fa-118">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9a1fa-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9a1fa-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a1fa-119">Requirements</span></span>  
 <span data-ttu-id="9a1fa-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a1fa-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a1fa-121">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9a1fa-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9a1fa-122">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9a1fa-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a1fa-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a1fa-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a1fa-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a1fa-124">See also</span></span>

- [<span data-ttu-id="9a1fa-125">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a1fa-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="9a1fa-126">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a1fa-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="9a1fa-127">IHostAssemblyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a1fa-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="9a1fa-128">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a1fa-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
