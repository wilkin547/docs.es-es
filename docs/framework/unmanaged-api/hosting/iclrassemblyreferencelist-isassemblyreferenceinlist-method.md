---
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
ms.openlocfilehash: 0632a7f5feee87c386d9488a6c989413af68a47f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615896"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="7da95-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList (Método)</span><span class="sxs-lookup"><span data-stu-id="7da95-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>
<span data-ttu-id="7da95-103">Obtiene un valor que indica si el puntero proporcionado hace referencia a un ensamblado de la lista.</span><span class="sxs-lookup"><span data-stu-id="7da95-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7da95-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7da95-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7da95-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7da95-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="7da95-106">de Puntero de interfaz al ensamblado que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="7da95-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="7da95-107">Los valores válidos son de tipo `IAssemblyName` o `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="7da95-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7da95-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7da95-108">Return Value</span></span>  
  
|<span data-ttu-id="7da95-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7da95-109">HRESULT</span></span>|<span data-ttu-id="7da95-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="7da95-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7da95-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7da95-111">S_OK</span></span>|<span data-ttu-id="7da95-112">La cadena aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="7da95-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="7da95-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="7da95-113">S_FALSE</span></span>|<span data-ttu-id="7da95-114">La cadena no aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="7da95-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="7da95-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7da95-115">E_FAIL</span></span>|<span data-ttu-id="7da95-116">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="7da95-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7da95-117">Después de que un método devuelva E_FAIL, el Common Language Runtime ya no se podrá usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="7da95-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="7da95-118">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7da95-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7da95-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7da95-119">Requirements</span></span>  
 <span data-ttu-id="7da95-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7da95-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7da95-121">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7da95-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7da95-122">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7da95-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7da95-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7da95-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7da95-124">Consulta también</span><span class="sxs-lookup"><span data-stu-id="7da95-124">See also</span></span>

- [<span data-ttu-id="7da95-125">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7da95-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="7da95-126">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7da95-126">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="7da95-127">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7da95-127">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="7da95-128">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7da95-128">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
