---
description: 'Más información acerca de: IAssemblyCacheItem:: Commit (método)'
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
ms.openlocfilehash: bd73bb9099090089e52d52009cfef309b33adc53
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760865"
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="b1a19-103">IAssemblyCacheItem::Commit (Método)</span><span class="sxs-lookup"><span data-stu-id="b1a19-103">IAssemblyCacheItem::Commit Method</span></span>

<span data-ttu-id="b1a19-104">Confirma la referencia de ensamblado en caché a la memoria.</span><span class="sxs-lookup"><span data-stu-id="b1a19-104">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1a19-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1a19-105">Syntax</span></span>  
  
```cpp  
HRESULT Commit (  
    [in] DWORD dwFlags,
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1a19-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b1a19-106">Parameters</span></span>  

 `dwFlags`  
 <span data-ttu-id="b1a19-107">de Marcas definidas en Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="b1a19-107">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="b1a19-108">[out, opcional] Valor que indica el resultado de la operación.</span><span class="sxs-lookup"><span data-stu-id="b1a19-108">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1a19-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b1a19-109">Requirements</span></span>  

 <span data-ttu-id="b1a19-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1a19-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1a19-111">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="b1a19-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b1a19-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1a19-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1a19-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1a19-113">See also</span></span>

- [<span data-ttu-id="b1a19-114">IAssemblyCacheItem (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b1a19-114">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
