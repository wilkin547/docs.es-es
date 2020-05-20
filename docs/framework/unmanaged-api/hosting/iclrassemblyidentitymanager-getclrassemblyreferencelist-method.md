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
ms.openlocfilehash: 7f09cb2264b21fdfbc892069f2c2f0a963b131f8
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615974"
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="c24e7-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList (Método)</span><span class="sxs-lookup"><span data-stu-id="c24e7-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>
<span data-ttu-id="c24e7-103">Obtiene un puntero de interfaz a una instancia de [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) a partir de la lista proporcionada de identidades de ensamblado parciales.</span><span class="sxs-lookup"><span data-stu-id="c24e7-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c24e7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c24e7-104">Syntax</span></span>  
  
```cpp  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c24e7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c24e7-105">Parameters</span></span>  
 `ppwzAssemblyReferences`  
 <span data-ttu-id="c24e7-106">de Una matriz de cadenas terminadas en NULL con el formato "Name, Property = Value..." que especifica una lista de identidades de ensamblado parciales.</span><span class="sxs-lookup"><span data-stu-id="c24e7-106">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="c24e7-107">de Número de elementos de `ppwzAssemblyReferences` .</span><span class="sxs-lookup"><span data-stu-id="c24e7-107">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="c24e7-108">enuncia Puntero de interfaz a un `ICLRAssemblyReferenceList` objeto que contiene los datos de identidad del ensamblado para la lista de ensamblados especificada en `ppwzAssemblyReferences` .</span><span class="sxs-lookup"><span data-stu-id="c24e7-108">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c24e7-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c24e7-109">Return Value</span></span>  
  
|<span data-ttu-id="c24e7-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c24e7-110">HRESULT</span></span>|<span data-ttu-id="c24e7-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="c24e7-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c24e7-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c24e7-112">S_OK</span></span>|<span data-ttu-id="c24e7-113">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c24e7-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="c24e7-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c24e7-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c24e7-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c24e7-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c24e7-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c24e7-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c24e7-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c24e7-117">The call timed out.</span></span>|  
|<span data-ttu-id="c24e7-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c24e7-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c24e7-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c24e7-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c24e7-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c24e7-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c24e7-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="c24e7-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c24e7-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c24e7-122">E_FAIL</span></span>|<span data-ttu-id="c24e7-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="c24e7-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c24e7-124">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c24e7-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c24e7-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c24e7-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c24e7-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c24e7-126">Requirements</span></span>  
 <span data-ttu-id="c24e7-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c24e7-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c24e7-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c24e7-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c24e7-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c24e7-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c24e7-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c24e7-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c24e7-131">Consulta también</span><span class="sxs-lookup"><span data-stu-id="c24e7-131">See also</span></span>

- [<span data-ttu-id="c24e7-132">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c24e7-132">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="c24e7-133">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c24e7-133">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
