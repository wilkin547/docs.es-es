---
description: 'Más información sobre: ICLRAssemblyIdentityManager:: Getreferencedassembliesfromfile ((método)'
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
ms.openlocfilehash: 46b2f392746c6e23e2a8a11aded5eacd8f5a597b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790066"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromfile-method"></a><span data-ttu-id="67f1e-103">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile (Método)</span><span class="sxs-lookup"><span data-stu-id="67f1e-103">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile Method</span></span>

<span data-ttu-id="67f1e-104">Obtiene una instancia de [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) que contiene una lista de ensamblados a los que hace referencia el ensamblado en la ruta de acceso de archivo especificada.</span><span class="sxs-lookup"><span data-stu-id="67f1e-104">Gets an [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67f1e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67f1e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromFile (  
    [in]  LPCWSTR pwzFilePath,  
    [in]  DWORD   dwFlags,  
    [in]  ICLRAssemblyReferenceList   *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum  **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67f1e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="67f1e-106">Parameters</span></span>  

 `pwzFilePath`  
 <span data-ttu-id="67f1e-107">de Ruta de acceso al ensamblado que se va a evaluar.</span><span class="sxs-lookup"><span data-stu-id="67f1e-107">[in] The path to the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="67f1e-108">de Se proporciona para la extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="67f1e-108">[in] Provided for future extensibility.</span></span> <span data-ttu-id="67f1e-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor que admite la versión actual del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="67f1e-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="67f1e-110">de Un puntero a un objeto [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) que representa los ensamblados que se deben excluir de `ppReferenceEnum` .</span><span class="sxs-lookup"><span data-stu-id="67f1e-110">[in] A pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) object that represents assemblies that should be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="67f1e-111">enuncia Puntero a la dirección de un `ICLRReferenceAssemblyEnum` objeto que contiene los datos de identidad del ensamblado para los ensamblados a los que hace referencia el ensamblado en `pwzFilePath` , excluyendo los ensamblados representados por `pExcludeAssembliesList` .</span><span class="sxs-lookup"><span data-stu-id="67f1e-111">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly at `pwzFilePath`, excluding the assemblies represented by `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67f1e-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="67f1e-112">Return Value</span></span>  
  
|<span data-ttu-id="67f1e-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="67f1e-113">HRESULT</span></span>|<span data-ttu-id="67f1e-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="67f1e-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="67f1e-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="67f1e-115">S_OK</span></span>|<span data-ttu-id="67f1e-116">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="67f1e-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="67f1e-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="67f1e-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="67f1e-118">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="67f1e-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="67f1e-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="67f1e-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="67f1e-120">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="67f1e-120">The call timed out.</span></span>|  
|<span data-ttu-id="67f1e-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="67f1e-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="67f1e-122">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="67f1e-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="67f1e-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="67f1e-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="67f1e-124">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="67f1e-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="67f1e-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="67f1e-125">E_FAIL</span></span>|<span data-ttu-id="67f1e-126">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="67f1e-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="67f1e-127">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="67f1e-127">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="67f1e-128">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="67f1e-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67f1e-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="67f1e-129">Remarks</span></span>  

 <span data-ttu-id="67f1e-130">El autor de la llamada puede optar por excluir un conjunto de referencias de ensamblado conocidas de la lista devuelta.</span><span class="sxs-lookup"><span data-stu-id="67f1e-130">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="67f1e-131">Este conjunto lo define el `pExcludeAssembliesList` parámetro.</span><span class="sxs-lookup"><span data-stu-id="67f1e-131">This set is defined by the `pExcludeAssembliesList` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67f1e-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="67f1e-132">Requirements</span></span>  

 <span data-ttu-id="67f1e-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67f1e-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67f1e-134">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="67f1e-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67f1e-135">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="67f1e-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67f1e-136">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67f1e-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67f1e-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="67f1e-137">See also</span></span>

- [<span data-ttu-id="67f1e-138">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="67f1e-138">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="67f1e-139">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="67f1e-139">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="67f1e-140">ICLRReferenceAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="67f1e-140">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)
