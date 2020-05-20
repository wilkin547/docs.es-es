---
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
ms.openlocfilehash: 91f174cab4986882df795eb531baedfc0dd43962
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615870"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="42ace-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList (Método)</span><span class="sxs-lookup"><span data-stu-id="42ace-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="42ace-103">Obtiene un valor que indica si el nombre proporcionado coincide con el nombre de un ensamblado de la lista.</span><span class="sxs-lookup"><span data-stu-id="42ace-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42ace-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42ace-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42ace-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="42ace-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="42ace-106">de Nombre del ensamblado que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="42ace-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42ace-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="42ace-107">Return Value</span></span>  
  
|<span data-ttu-id="42ace-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="42ace-108">HRESULT</span></span>|<span data-ttu-id="42ace-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="42ace-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="42ace-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="42ace-110">S_OK</span></span>|<span data-ttu-id="42ace-111">La cadena aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="42ace-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="42ace-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="42ace-112">S_FALSE</span></span>|<span data-ttu-id="42ace-113">La cadena no aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="42ace-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="42ace-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="42ace-114">E_FAIL</span></span>|<span data-ttu-id="42ace-115">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="42ace-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="42ace-116">Después de que un método devuelva E_FAIL, el Common Language Runtime ya no se podrá usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="42ace-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="42ace-117">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="42ace-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="42ace-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42ace-118">Requirements</span></span>  
 <span data-ttu-id="42ace-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42ace-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42ace-120">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="42ace-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42ace-121">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="42ace-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42ace-122">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42ace-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42ace-123">Consulta también</span><span class="sxs-lookup"><span data-stu-id="42ace-123">See also</span></span>

- [<span data-ttu-id="42ace-124">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="42ace-124">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="42ace-125">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="42ace-125">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="42ace-126">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="42ace-126">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="42ace-127">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="42ace-127">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
