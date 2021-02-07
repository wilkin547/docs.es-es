---
description: 'Más información acerca de: ICLRAssemblyReferenceList:: Isassemblyreferenceinlist ((método)'
title: ICLRAssemblyReferenceList::IsAssemblyReferenceInList (Método)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList method [.NET Framework hosting]
- IsAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: 8a570813-21be-407e-92a6-7ae8de3bc728
topic_type:
- apiref
ms.openlocfilehash: ce90423715d6cbe07c1112cb2136c11fd58c982a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716775"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="b2a85-103">ICLRAssemblyReferenceList::IsAssemblyReferenceInList (Método)</span><span class="sxs-lookup"><span data-stu-id="b2a85-103">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>

<span data-ttu-id="b2a85-104">Obtiene un valor que indica si el puntero proporcionado hace referencia a un ensamblado de la lista.</span><span class="sxs-lookup"><span data-stu-id="b2a85-104">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2a85-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2a85-105">Syntax</span></span>  
  
```cpp  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2a85-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b2a85-106">Parameters</span></span>  

 `pName`  
 <span data-ttu-id="b2a85-107">de Puntero de interfaz al ensamblado que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="b2a85-107">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="b2a85-108">Los valores válidos son de tipo `IAssemblyName` o `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="b2a85-108">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2a85-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b2a85-109">Return Value</span></span>  
  
|<span data-ttu-id="b2a85-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b2a85-110">HRESULT</span></span>|<span data-ttu-id="b2a85-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2a85-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b2a85-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2a85-112">S_OK</span></span>|<span data-ttu-id="b2a85-113">La cadena aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="b2a85-113">The string appears in the list.</span></span>|  
|<span data-ttu-id="b2a85-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b2a85-114">S_FALSE</span></span>|<span data-ttu-id="b2a85-115">La cadena no aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="b2a85-115">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="b2a85-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b2a85-116">E_FAIL</span></span>|<span data-ttu-id="b2a85-117">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="b2a85-117">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b2a85-118">Después de que un método devuelva E_FAIL, el Common Language Runtime ya no se podrá usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="b2a85-118">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="b2a85-119">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b2a85-119">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2a85-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2a85-120">Requirements</span></span>  

 <span data-ttu-id="b2a85-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2a85-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2a85-122">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b2a85-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b2a85-123">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b2a85-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2a85-124">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2a85-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2a85-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2a85-125">See also</span></span>

- [<span data-ttu-id="b2a85-126">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2a85-126">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="b2a85-127">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2a85-127">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="b2a85-128">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2a85-128">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="b2a85-129">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2a85-129">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
