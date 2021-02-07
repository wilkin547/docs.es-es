---
description: 'Más información sobre: ICLRAssemblyIdentityManager:: Getreferencedassembliesfromstream ((método)'
title: ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream (Método)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream method [.NET Framework hosting]
- GetReferencedAssembliesFromStream method [.NET Framework hosting]
ms.assetid: fe9849c1-c3fc-477b-a31f-e8619f5516f5
topic_type:
- apiref
ms.openlocfilehash: 9173587125e7b528e203dcb7e6a19d3e3f2fb990
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746118"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromstream-method"></a><span data-ttu-id="134d3-103">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream (Método)</span><span class="sxs-lookup"><span data-stu-id="134d3-103">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream Method</span></span>

<span data-ttu-id="134d3-104">Obtiene un puntero a un objeto [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) que contiene los datos de identidad del ensamblado para los ensamblados a los que hace referencia el ensamblado en la secuencia especificada.</span><span class="sxs-lookup"><span data-stu-id="134d3-104">Gets a pointer to an [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="134d3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="134d3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromStream (  
    [in]  IStream *pStream,  
    [in]  DWORD    dwFlags,  
    [in]  ICLRAssemblyReferenceList  *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="134d3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="134d3-106">Parameters</span></span>  

 `pStream`  
 <span data-ttu-id="134d3-107">de Puntero de interfaz a un objeto `IStream` que contiene el ensamblado que se va a evaluar.</span><span class="sxs-lookup"><span data-stu-id="134d3-107">[in] An interface pointer to an `IStream` containing the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="134d3-108">de Se proporciona para la extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="134d3-108">[in] Provided for future extensibility.</span></span> <span data-ttu-id="134d3-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor que admite la versión actual del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="134d3-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="134d3-110">de Un puntero a un objeto [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) que contiene los datos de identidad del ensamblado de los ensamblados que se van a excluir `ppReferenceEnum` .</span><span class="sxs-lookup"><span data-stu-id="134d3-110">[in] A pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) object that contains assembly identity data for the assemblies to be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="134d3-111">enuncia Puntero a la dirección de un `ICLRReferenceAssemblyEnum` objeto que contiene los datos de identidad del ensamblado para los ensamblados a los que hace referencia el ensamblado en `pStream` , excluyendo los ensamblados de `pExcludeAssembliesList` .</span><span class="sxs-lookup"><span data-stu-id="134d3-111">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in `pStream`, excluding the assemblies in `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="134d3-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="134d3-112">Return Value</span></span>  
  
|<span data-ttu-id="134d3-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="134d3-113">HRESULT</span></span>|<span data-ttu-id="134d3-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="134d3-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="134d3-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="134d3-115">S_OK</span></span>|<span data-ttu-id="134d3-116">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="134d3-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="134d3-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="134d3-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="134d3-118">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="134d3-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="134d3-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="134d3-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="134d3-120">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="134d3-120">The call timed out.</span></span>|  
|<span data-ttu-id="134d3-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="134d3-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="134d3-122">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="134d3-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="134d3-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="134d3-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="134d3-124">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="134d3-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="134d3-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="134d3-125">E_FAIL</span></span>|<span data-ttu-id="134d3-126">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="134d3-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="134d3-127">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="134d3-127">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="134d3-128">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="134d3-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="134d3-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="134d3-129">Remarks</span></span>  

 <span data-ttu-id="134d3-130">El autor de la llamada puede optar por excluir un conjunto de referencias de ensamblado conocidas de la lista devuelta.</span><span class="sxs-lookup"><span data-stu-id="134d3-130">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="134d3-131">Este conjunto lo define `pExcludeAssembliesList` .</span><span class="sxs-lookup"><span data-stu-id="134d3-131">This set is defined by `pExcludeAssembliesList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="134d3-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="134d3-132">Requirements</span></span>  

 <span data-ttu-id="134d3-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="134d3-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="134d3-134">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="134d3-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="134d3-135">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="134d3-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="134d3-136">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="134d3-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="134d3-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="134d3-137">See also</span></span>

- [<span data-ttu-id="134d3-138">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="134d3-138">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="134d3-139">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="134d3-139">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="134d3-140">ICLRReferenceAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="134d3-140">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)
