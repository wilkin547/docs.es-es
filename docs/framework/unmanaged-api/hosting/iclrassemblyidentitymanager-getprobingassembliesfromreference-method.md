---
description: 'Más información sobre: ICLRAssemblyIdentityManager:: Getprobingassembliesfromreference ((método)'
title: ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference (Método)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetProbingAssembliesFromReference
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference method [.NET Framework hosting]
- GetProbingAssembliesFromReference method [.NET Framework hosting]
ms.assetid: aec05744-e8d4-44c6-b4a8-e583229ac34e
topic_type:
- apiref
ms.openlocfilehash: 38fcea460537ebed0e54103b460a48c2e58d8173
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100431430"
---
# <a name="iclrassemblyidentitymanagergetprobingassembliesfromreference-method"></a><span data-ttu-id="57bff-103">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference (Método)</span><span class="sxs-lookup"><span data-stu-id="57bff-103">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Method</span></span>

<span data-ttu-id="57bff-104">Obtiene un enumerador [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) para las identidades de ensamblado a las que hace referencia el ensamblado con el tipo de identidad especificado.</span><span class="sxs-lookup"><span data-stu-id="57bff-104">Gets an [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57bff-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57bff-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProbingAssembliesFromReference (  
    [in] DWORD   dwMachineType,  
    [in] DWORD   dwFlags,  
    [in] LPCWSTR pwzReferenceIdentity,  
    [out] ICLRProbingAssemblyEnum **ppProbingAssemblyEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57bff-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="57bff-106">Parameters</span></span>  

 `dwMachineType`  
 <span data-ttu-id="57bff-107">de Valor válido que especifica la arquitectura del procesador, tal y como se define en Winnt. h.</span><span class="sxs-lookup"><span data-stu-id="57bff-107">[in] A valid value that specifies the processor architecture, as defined in WinNT.h.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="57bff-108">de Se proporciona para la extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="57bff-108">[in] Provided for future extensibility.</span></span> <span data-ttu-id="57bff-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor que admite la versión actual del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="57bff-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzReferenceIdentity`  
 <span data-ttu-id="57bff-110">de Una identidad de enlace de ensamblado opaca, normalmente devuelta por una llamada al método [ICLRAssemblyIdentityManager:: getbindingidentityfromfile (](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) o [ICLRAssemblyIdentityManager:: getbindingidentityfromstream (](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) .</span><span class="sxs-lookup"><span data-stu-id="57bff-110">[in] An opaque assembly binding identity, typically returned from a call to the [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) or [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) method.</span></span>  
  
 `ppProbingAssemblyEnum`  
 <span data-ttu-id="57bff-111">enuncia Puntero de interfaz a un `ICLRProbingAssemblyEnum` enumerador que contiene referencias a los ensamblados a los que hace referencia el ensamblado identificado por `pwzReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="57bff-111">[out] An interface pointer to an `ICLRProbingAssemblyEnum` enumerator that contains references to the assemblies referenced by the assembly identified by `pwzReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57bff-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="57bff-112">Return Value</span></span>  
  
|<span data-ttu-id="57bff-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="57bff-113">HRESULT</span></span>|<span data-ttu-id="57bff-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="57bff-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="57bff-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="57bff-115">S_OK</span></span>|<span data-ttu-id="57bff-116">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="57bff-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="57bff-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="57bff-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="57bff-118">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="57bff-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="57bff-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="57bff-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="57bff-120">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="57bff-120">The call timed out.</span></span>|  
|<span data-ttu-id="57bff-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="57bff-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="57bff-122">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="57bff-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="57bff-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="57bff-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="57bff-124">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="57bff-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="57bff-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="57bff-125">E_FAIL</span></span>|<span data-ttu-id="57bff-126">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="57bff-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="57bff-127">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="57bff-127">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="57bff-128">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="57bff-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="57bff-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57bff-129">Requirements</span></span>  

 <span data-ttu-id="57bff-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57bff-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57bff-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="57bff-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="57bff-132">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="57bff-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="57bff-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57bff-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57bff-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57bff-134">See also</span></span>

- [<span data-ttu-id="57bff-135">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="57bff-135">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="57bff-136">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="57bff-136">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="57bff-137">ICLRProbingAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="57bff-137">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)
