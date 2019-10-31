---
title: ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile (Método)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferenceAssembliesFromFile method [.NET Framework hosting]
- GetReferenceAssembliesFromFile method [.NET Framework hosting]
ms.assetid: eed63d31-d977-4c7d-9443-f9d37a2a7d81
topic_type:
- apiref
ms.openlocfilehash: 65dc330e88cb2457cc34f9994313373ab1ab84aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126699"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromfile-method"></a><span data-ttu-id="7be24-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile (Método)</span><span class="sxs-lookup"><span data-stu-id="7be24-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile Method</span></span>
<span data-ttu-id="7be24-103">Obtiene una instancia de [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) que contiene una lista de ensamblados a los que hace referencia el ensamblado en la ruta de acceso de archivo especificada.</span><span class="sxs-lookup"><span data-stu-id="7be24-103">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7be24-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7be24-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromFile (  
    [in]  LPCWSTR pwzFilePath,  
    [in]  DWORD   dwFlags,  
    [in]  ICLRAssemblyReferenceList   *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum  **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7be24-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7be24-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="7be24-106">de Ruta de acceso al ensamblado que se va a evaluar.</span><span class="sxs-lookup"><span data-stu-id="7be24-106">[in] The path to the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7be24-107">de Se proporciona para la extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="7be24-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="7be24-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor que admite la versión actual del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="7be24-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="7be24-109">de Un puntero a un objeto [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) que representa los ensamblados que se deben excluir de `ppReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="7be24-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that represents assemblies that should be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="7be24-110">enuncia Puntero a la dirección de un objeto `ICLRReferenceAssemblyEnum` que contiene los datos de identidad del ensamblado para los ensamblados a los que hace referencia el ensamblado en `pwzFilePath`, excluyendo los ensamblados representados por `pExcludeAssembliesList`.</span><span class="sxs-lookup"><span data-stu-id="7be24-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly at `pwzFilePath`, excluding the assemblies represented by `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7be24-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7be24-111">Return Value</span></span>  
  
|<span data-ttu-id="7be24-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7be24-112">HRESULT</span></span>|<span data-ttu-id="7be24-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="7be24-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7be24-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="7be24-114">S_OK</span></span>|<span data-ttu-id="7be24-115">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7be24-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="7be24-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7be24-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7be24-117">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="7be24-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7be24-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7be24-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7be24-119">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="7be24-119">The call timed out.</span></span>|  
|<span data-ttu-id="7be24-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7be24-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7be24-121">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7be24-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7be24-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7be24-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7be24-123">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="7be24-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7be24-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7be24-124">E_FAIL</span></span>|<span data-ttu-id="7be24-125">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="7be24-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7be24-126">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="7be24-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7be24-127">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7be24-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7be24-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7be24-128">Remarks</span></span>  
 <span data-ttu-id="7be24-129">El autor de la llamada puede optar por excluir un conjunto de referencias de ensamblado conocidas de la lista devuelta.</span><span class="sxs-lookup"><span data-stu-id="7be24-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="7be24-130">Este conjunto se define mediante el parámetro `pExcludeAssembliesList`.</span><span class="sxs-lookup"><span data-stu-id="7be24-130">This set is defined by the `pExcludeAssembliesList` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7be24-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7be24-131">Requirements</span></span>  
 <span data-ttu-id="7be24-132">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7be24-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7be24-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7be24-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7be24-134">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7be24-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7be24-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7be24-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7be24-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="7be24-136">See also</span></span>

- [<span data-ttu-id="7be24-137">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7be24-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="7be24-138">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7be24-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="7be24-139">ICLRReferenceAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7be24-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
