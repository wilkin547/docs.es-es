---
description: 'Más información sobre: ICLRAssemblyIdentityManager:: Getclrassemblyreferencelist ((método)'
title: ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList (Método)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetCLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList
helpviewer_keywords:
- GetClrAssemblyReferenceList method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList method [.NET Framework hosting]
ms.assetid: cb5ffae5-287b-4a87-9ca8-7ce3ae0601b7
topic_type:
- apiref
ms.openlocfilehash: 91f7b9eaacee559c5e404b5dda0f8b4201f91a66
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649564"
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="1cd59-103">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList (Método)</span><span class="sxs-lookup"><span data-stu-id="1cd59-103">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>

<span data-ttu-id="1cd59-104">Obtiene un puntero de interfaz a una instancia de [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) a partir de la lista proporcionada de identidades de ensamblado parciales.</span><span class="sxs-lookup"><span data-stu-id="1cd59-104">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cd59-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1cd59-105">Syntax</span></span>  
  
```cpp  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1cd59-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1cd59-106">Parameters</span></span>  

 `ppwzAssemblyReferences`  
 <span data-ttu-id="1cd59-107">de Una matriz de cadenas terminadas en NULL con el formato "Name, Property = Value..." que especifica una lista de identidades de ensamblado parciales.</span><span class="sxs-lookup"><span data-stu-id="1cd59-107">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="1cd59-108">de Número de elementos de `ppwzAssemblyReferences` .</span><span class="sxs-lookup"><span data-stu-id="1cd59-108">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="1cd59-109">enuncia Puntero de interfaz a un `ICLRAssemblyReferenceList` objeto que contiene los datos de identidad del ensamblado para la lista de ensamblados especificada en `ppwzAssemblyReferences` .</span><span class="sxs-lookup"><span data-stu-id="1cd59-109">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1cd59-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1cd59-110">Return Value</span></span>  
  
|<span data-ttu-id="1cd59-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1cd59-111">HRESULT</span></span>|<span data-ttu-id="1cd59-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="1cd59-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1cd59-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="1cd59-113">S_OK</span></span>|<span data-ttu-id="1cd59-114">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1cd59-114">The method returned successfully.</span></span>|  
|<span data-ttu-id="1cd59-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1cd59-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1cd59-116">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="1cd59-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1cd59-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1cd59-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1cd59-118">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1cd59-118">The call timed out.</span></span>|  
|<span data-ttu-id="1cd59-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1cd59-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1cd59-120">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1cd59-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1cd59-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1cd59-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1cd59-122">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="1cd59-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1cd59-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1cd59-123">E_FAIL</span></span>|<span data-ttu-id="1cd59-124">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="1cd59-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1cd59-125">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="1cd59-125">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1cd59-126">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1cd59-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1cd59-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1cd59-127">Requirements</span></span>  

 <span data-ttu-id="1cd59-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cd59-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cd59-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1cd59-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1cd59-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1cd59-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1cd59-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cd59-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cd59-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="1cd59-132">See also</span></span>

- [<span data-ttu-id="1cd59-133">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1cd59-133">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="1cd59-134">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1cd59-134">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
