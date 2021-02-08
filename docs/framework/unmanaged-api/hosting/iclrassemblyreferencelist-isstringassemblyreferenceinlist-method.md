---
description: 'Más información acerca de: ICLRAssemblyReferenceList:: IsStringAssemblyReferenceInList ((método)'
title: ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList (Método)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsStringAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList method [.NET Framework hosting]
- IsStringAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: e6121cc3-2f11-42c7-bdae-47808581ff71
topic_type:
- apiref
ms.openlocfilehash: 667764337fbda22a526e51575faf049efc4b86ca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790040"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="30a27-103">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList (Método)</span><span class="sxs-lookup"><span data-stu-id="30a27-103">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>

<span data-ttu-id="30a27-104">Obtiene un valor que indica si el nombre proporcionado coincide con el nombre de un ensamblado de la lista.</span><span class="sxs-lookup"><span data-stu-id="30a27-104">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30a27-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30a27-105">Syntax</span></span>  
  
```cpp  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30a27-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="30a27-106">Parameters</span></span>  

 `pwzAssemblyName`  
 <span data-ttu-id="30a27-107">de Nombre del ensamblado que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="30a27-107">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30a27-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="30a27-108">Return Value</span></span>  
  
|<span data-ttu-id="30a27-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="30a27-109">HRESULT</span></span>|<span data-ttu-id="30a27-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="30a27-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30a27-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="30a27-111">S_OK</span></span>|<span data-ttu-id="30a27-112">La cadena aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="30a27-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="30a27-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="30a27-113">S_FALSE</span></span>|<span data-ttu-id="30a27-114">La cadena no aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="30a27-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="30a27-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="30a27-115">E_FAIL</span></span>|<span data-ttu-id="30a27-116">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="30a27-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="30a27-117">Después de que un método devuelva E_FAIL, el Common Language Runtime ya no se podrá usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="30a27-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="30a27-118">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="30a27-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="30a27-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30a27-119">Requirements</span></span>  

 <span data-ttu-id="30a27-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30a27-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30a27-121">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="30a27-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30a27-122">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="30a27-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30a27-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30a27-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30a27-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="30a27-124">See also</span></span>

- [<span data-ttu-id="30a27-125">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="30a27-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="30a27-126">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="30a27-126">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="30a27-127">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="30a27-127">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="30a27-128">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="30a27-128">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
