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
ms.openlocfilehash: 6b67ba9d022d94f51d7cc6a4645855f6b6ac3e19
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679329"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromfile-method"></a><span data-ttu-id="4386b-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile (Método)</span><span class="sxs-lookup"><span data-stu-id="4386b-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile Method</span></span>

<span data-ttu-id="4386b-103">Obtiene una instancia de [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) que contiene una lista de ensamblados a los que hace referencia el ensamblado en la ruta de acceso de archivo especificada.</span><span class="sxs-lookup"><span data-stu-id="4386b-103">Gets an [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4386b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4386b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromFile (  
    [in]  LPCWSTR pwzFilePath,  
    [in]  DWORD   dwFlags,  
    [in]  ICLRAssemblyReferenceList   *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum  **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4386b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4386b-105">Parameters</span></span>  

 `pwzFilePath`  
 <span data-ttu-id="4386b-106">de Ruta de acceso al ensamblado que se va a evaluar.</span><span class="sxs-lookup"><span data-stu-id="4386b-106">[in] The path to the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="4386b-107">de Se proporciona para la extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="4386b-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="4386b-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor que admite la versión actual del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="4386b-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="4386b-109">de Un puntero a un objeto [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) que representa los ensamblados que se deben excluir de `ppReferenceEnum` .</span><span class="sxs-lookup"><span data-stu-id="4386b-109">[in] A pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) object that represents assemblies that should be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="4386b-110">enuncia Puntero a la dirección de un `ICLRReferenceAssemblyEnum` objeto que contiene los datos de identidad del ensamblado para los ensamblados a los que hace referencia el ensamblado en `pwzFilePath` , excluyendo los ensamblados representados por `pExcludeAssembliesList` .</span><span class="sxs-lookup"><span data-stu-id="4386b-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly at `pwzFilePath`, excluding the assemblies represented by `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4386b-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4386b-111">Return Value</span></span>  
  
|<span data-ttu-id="4386b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4386b-112">HRESULT</span></span>|<span data-ttu-id="4386b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="4386b-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4386b-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="4386b-114">S_OK</span></span>|<span data-ttu-id="4386b-115">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4386b-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="4386b-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4386b-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4386b-117">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="4386b-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4386b-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4386b-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4386b-119">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="4386b-119">The call timed out.</span></span>|  
|<span data-ttu-id="4386b-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4386b-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4386b-121">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="4386b-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4386b-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4386b-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4386b-123">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="4386b-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4386b-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4386b-124">E_FAIL</span></span>|<span data-ttu-id="4386b-125">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="4386b-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4386b-126">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="4386b-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4386b-127">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4386b-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4386b-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4386b-128">Remarks</span></span>  

 <span data-ttu-id="4386b-129">El autor de la llamada puede optar por excluir un conjunto de referencias de ensamblado conocidas de la lista devuelta.</span><span class="sxs-lookup"><span data-stu-id="4386b-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="4386b-130">Este conjunto lo define el `pExcludeAssembliesList` parámetro.</span><span class="sxs-lookup"><span data-stu-id="4386b-130">This set is defined by the `pExcludeAssembliesList` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4386b-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4386b-131">Requirements</span></span>  

 <span data-ttu-id="4386b-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4386b-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4386b-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4386b-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4386b-134">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4386b-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4386b-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4386b-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4386b-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4386b-136">See also</span></span>

- [<span data-ttu-id="4386b-137">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4386b-137">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="4386b-138">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4386b-138">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="4386b-139">ICLRReferenceAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4386b-139">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)
