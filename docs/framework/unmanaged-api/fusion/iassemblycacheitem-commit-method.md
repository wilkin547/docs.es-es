---
title: IAssemblyCacheItem::Commit (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.Commit
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::Commit
helpviewer_keywords:
- IAssemblyCacheItem::Commit method [.NET Framework fusion]
- Commit method, IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: c2321f17-f46f-4815-ae41-b28678753613
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3757eee4c013ccf4f0f6d21ef64a92a5ffd70f19
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697508"
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="596e7-102">IAssemblyCacheItem::Commit (Método)</span><span class="sxs-lookup"><span data-stu-id="596e7-102">IAssemblyCacheItem::Commit Method</span></span>
<span data-ttu-id="596e7-103">Confirma la referencia de ensamblado en la caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="596e7-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="596e7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="596e7-104">Syntax</span></span>  
  
```  
HRESULT Commit (  
    [in] DWORD dwFlags,   
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="596e7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="596e7-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="596e7-106">[in] Marcadores definidos en Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="596e7-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="596e7-107">[out, optional] Un valor que indica el resultado de la operación.</span><span class="sxs-lookup"><span data-stu-id="596e7-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="596e7-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="596e7-108">Requirements</span></span>  
 <span data-ttu-id="596e7-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="596e7-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="596e7-110">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="596e7-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="596e7-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="596e7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="596e7-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="596e7-112">See also</span></span>

- [<span data-ttu-id="596e7-113">IAssemblyCacheItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="596e7-113">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
