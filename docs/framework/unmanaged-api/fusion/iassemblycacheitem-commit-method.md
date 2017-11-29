---
title: "IAssemblyCacheItem::Commit (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCacheItem.Commit
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCacheItem::Commit
helpviewer_keywords:
- IAssemblyCacheItem::Commit method [.NET Framework fusion]
- Commit method, IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: c2321f17-f46f-4815-ae41-b28678753613
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a5a25f24fd1f09ebc1cda0442e41fde9eef059d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="7b765-102">IAssemblyCacheItem::Commit (Método)</span><span class="sxs-lookup"><span data-stu-id="7b765-102">IAssemblyCacheItem::Commit Method</span></span>
<span data-ttu-id="7b765-103">Confirma la referencia de ensamblado en la caché a la memoria.</span><span class="sxs-lookup"><span data-stu-id="7b765-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b765-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b765-104">Syntax</span></span>  
  
```  
HRESULT Commit (  
    [in] DWORD dwFlags,   
    [out, optional] ULONG *pulDisposition  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b765-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b765-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="7b765-106">[in] Marcadores definidos en Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="7b765-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="7b765-107">[out, optional] Un valor que indica el resultado de la operación.</span><span class="sxs-lookup"><span data-stu-id="7b765-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b765-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b765-108">Requirements</span></span>  
 <span data-ttu-id="7b765-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b765-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b765-110">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="7b765-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7b765-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b765-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b765-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b765-112">See Also</span></span>  
 [<span data-ttu-id="7b765-113">IAssemblyCacheItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b765-113">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
