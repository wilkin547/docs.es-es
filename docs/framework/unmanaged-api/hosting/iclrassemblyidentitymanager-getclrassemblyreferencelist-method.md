---
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
ms.openlocfilehash: cfc384a71ac7e91181bdec09f0d385bacbe31753
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716673"
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="2a2e9-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList (Método)</span><span class="sxs-lookup"><span data-stu-id="2a2e9-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>

<span data-ttu-id="2a2e9-103">Obtiene un puntero de interfaz a una instancia de [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) a partir de la lista proporcionada de identidades de ensamblado parciales.</span><span class="sxs-lookup"><span data-stu-id="2a2e9-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a2e9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a2e9-104">Syntax</span></span>  
  
```cpp  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a2e9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a2e9-105">Parameters</span></span>  

 `ppwzAssemblyReferences`  
 <span data-ttu-id="2a2e9-106">de Una matriz de cadenas terminadas en NULL con el formato "Name, Property = Value..." que especifica una lista de identidades de ensamblado parciales.</span><span class="sxs-lookup"><span data-stu-id="2a2e9-106">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="2a2e9-107">de Número de elementos de `ppwzAssemblyReferences` .</span><span class="sxs-lookup"><span data-stu-id="2a2e9-107">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="2a2e9-108">enuncia Puntero de interfaz a un `ICLRAssemblyReferenceList` objeto que contiene los datos de identidad del ensamblado para la lista de ensamblados especificada en `ppwzAssemblyReferences` .</span><span class="sxs-lookup"><span data-stu-id="2a2e9-108">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a2e9-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2a2e9-109">Return Value</span></span>  
  
|<span data-ttu-id="2a2e9-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2a2e9-110">HRESULT</span></span>|<span data-ttu-id="2a2e9-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a2e9-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2a2e9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2a2e9-112">S_OK</span></span>|<span data-ttu-id="2a2e9-113">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2a2e9-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="2a2e9-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2a2e9-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2a2e9-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="2a2e9-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2a2e9-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2a2e9-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2a2e9-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2a2e9-117">The call timed out.</span></span>|  
|<span data-ttu-id="2a2e9-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2a2e9-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2a2e9-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2a2e9-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2a2e9-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2a2e9-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2a2e9-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="2a2e9-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2a2e9-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2a2e9-122">E_FAIL</span></span>|<span data-ttu-id="2a2e9-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="2a2e9-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2a2e9-124">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="2a2e9-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2a2e9-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2a2e9-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2a2e9-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a2e9-126">Requirements</span></span>  

 <span data-ttu-id="2a2e9-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a2e9-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a2e9-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2a2e9-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a2e9-129">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2a2e9-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a2e9-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a2e9-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a2e9-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2a2e9-131">See also</span></span>

- [<span data-ttu-id="2a2e9-132">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2a2e9-132">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="2a2e9-133">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2a2e9-133">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
