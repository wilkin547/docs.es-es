---
title: ICLRAssemblyIdentityManager::IsStronglyNamed (Método)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.IsStronglyNamed
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::IsStronglyNamed
helpviewer_keywords:
- IsStronglyNamed method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::IsStronglyNamed method [.NET Framework hosting]
ms.assetid: 954bd386-2076-4d00-9d46-38c728aa9cab
topic_type:
- apiref
ms.openlocfilehash: d388f366671f50c3dcb3bd9d387300dd1bbb168f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615909"
---
# <a name="iclrassemblyidentitymanagerisstronglynamed-method"></a><span data-ttu-id="f742c-102">ICLRAssemblyIdentityManager::IsStronglyNamed (Método)</span><span class="sxs-lookup"><span data-stu-id="f742c-102">ICLRAssemblyIdentityManager::IsStronglyNamed Method</span></span>
<span data-ttu-id="f742c-103">Obtiene un valor que indica si el ensamblado especificado tiene un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="f742c-103">Gets a value that indicates whether the specified assembly is strongly named.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f742c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f742c-104">Syntax</span></span>  
  
```cpp  
RESULT IsStronglyNamed (  
    [in]  LPCWSTR  pwzAssemblyIdentity,  
    [out] BOOL    *pbIsStronglyNamed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f742c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f742c-105">Parameters</span></span>  
 `pwzAssemblyIdentity`  
 <span data-ttu-id="f742c-106">de Datos de identidad del ensamblado canónico opaco del ensamblado que se va a evaluar.</span><span class="sxs-lookup"><span data-stu-id="f742c-106">[in] The opaque canonical assembly identity data of the assembly to be evaluated.</span></span>  
  
 `pbIsStronglyNamed`  
 <span data-ttu-id="f742c-107">[out] `true` si el ensamblado al que hace referencia el `pwzAssemblyIdentity` parámetro tiene un nombre seguro; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="f742c-107">[out] `true`, if the assembly referenced by the `pwzAssemblyIdentity` parameter is strongly named; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f742c-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f742c-108">Return Value</span></span>  
  
|<span data-ttu-id="f742c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f742c-109">HRESULT</span></span>|<span data-ttu-id="f742c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="f742c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f742c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f742c-111">S_OK</span></span>|<span data-ttu-id="f742c-112">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f742c-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="f742c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f742c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f742c-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="f742c-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f742c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f742c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f742c-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f742c-116">The call timed out.</span></span>|  
|<span data-ttu-id="f742c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f742c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f742c-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f742c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f742c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f742c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f742c-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="f742c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f742c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f742c-121">E_FAIL</span></span>|<span data-ttu-id="f742c-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="f742c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f742c-123">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f742c-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f742c-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f742c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f742c-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f742c-125">Requirements</span></span>  
 <span data-ttu-id="f742c-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f742c-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f742c-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f742c-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f742c-128">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f742c-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f742c-129">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f742c-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f742c-130">Consulta también</span><span class="sxs-lookup"><span data-stu-id="f742c-130">See also</span></span>

- [<span data-ttu-id="f742c-131">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f742c-131">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
