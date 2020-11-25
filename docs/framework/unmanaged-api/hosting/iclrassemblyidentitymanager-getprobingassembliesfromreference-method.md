---
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
ms.openlocfilehash: 263058131e63205aa37f81847ed647944fef7540
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731402"
---
# <a name="iclrassemblyidentitymanagergetprobingassembliesfromreference-method"></a><span data-ttu-id="42b18-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference (Método)</span><span class="sxs-lookup"><span data-stu-id="42b18-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Method</span></span>

<span data-ttu-id="42b18-103">Obtiene un enumerador [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) para las identidades de ensamblado a las que hace referencia el ensamblado con el tipo de identidad especificado.</span><span class="sxs-lookup"><span data-stu-id="42b18-103">Gets an [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42b18-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42b18-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProbingAssembliesFromReference (  
    [in] DWORD   dwMachineType,  
    [in] DWORD   dwFlags,  
    [in] LPCWSTR pwzReferenceIdentity,  
    [out] ICLRProbingAssemblyEnum **ppProbingAssemblyEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42b18-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="42b18-105">Parameters</span></span>  

 `dwMachineType`  
 <span data-ttu-id="42b18-106">de Valor válido que especifica la arquitectura del procesador, tal y como se define en Winnt. h.</span><span class="sxs-lookup"><span data-stu-id="42b18-106">[in] A valid value that specifies the processor architecture, as defined in WinNT.h.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="42b18-107">de Se proporciona para la extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="42b18-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="42b18-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor que admite la versión actual del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="42b18-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzReferenceIdentity`  
 <span data-ttu-id="42b18-109">de Una identidad de enlace de ensamblado opaca, normalmente devuelta por una llamada al método [ICLRAssemblyIdentityManager:: getbindingidentityfromfile (](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) o [ICLRAssemblyIdentityManager:: getbindingidentityfromstream (](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) .</span><span class="sxs-lookup"><span data-stu-id="42b18-109">[in] An opaque assembly binding identity, typically returned from a call to the [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) or [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) method.</span></span>  
  
 `ppProbingAssemblyEnum`  
 <span data-ttu-id="42b18-110">enuncia Puntero de interfaz a un `ICLRProbingAssemblyEnum` enumerador que contiene referencias a los ensamblados a los que hace referencia el ensamblado identificado por `pwzReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="42b18-110">[out] An interface pointer to an `ICLRProbingAssemblyEnum` enumerator that contains references to the assemblies referenced by the assembly identified by `pwzReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42b18-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="42b18-111">Return Value</span></span>  
  
|<span data-ttu-id="42b18-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="42b18-112">HRESULT</span></span>|<span data-ttu-id="42b18-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="42b18-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="42b18-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="42b18-114">S_OK</span></span>|<span data-ttu-id="42b18-115">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="42b18-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="42b18-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="42b18-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="42b18-117">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="42b18-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="42b18-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="42b18-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="42b18-119">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="42b18-119">The call timed out.</span></span>|  
|<span data-ttu-id="42b18-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="42b18-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="42b18-121">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="42b18-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="42b18-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="42b18-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="42b18-123">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="42b18-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="42b18-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="42b18-124">E_FAIL</span></span>|<span data-ttu-id="42b18-125">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="42b18-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="42b18-126">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="42b18-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="42b18-127">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="42b18-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="42b18-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42b18-128">Requirements</span></span>  

 <span data-ttu-id="42b18-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42b18-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42b18-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="42b18-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42b18-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="42b18-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42b18-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42b18-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42b18-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42b18-133">See also</span></span>

- [<span data-ttu-id="42b18-134">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="42b18-134">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="42b18-135">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="42b18-135">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="42b18-136">ICLRProbingAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="42b18-136">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)
