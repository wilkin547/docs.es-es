---
title: IAssemblyCache::CreateAssemblyCacheItem (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyCache.CreateAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::CreateAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCache::CreateAssemblyCacheItem method [.NET Framework fusion]
- CreateAssemblyCacheItem method [.NET Framework fusion]
ms.assetid: 017a7ba5-aaaf-44e2-9cbe-ceebef259df0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4432b17e5d9aa875d8346b3329cd618e15222040
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771021"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="c3873-102">IAssemblyCache::CreateAssemblyCacheItem (Método)</span><span class="sxs-lookup"><span data-stu-id="c3873-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="c3873-103">Obtiene una referencia a un nuevo [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="c3873-103">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3873-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3873-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3873-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c3873-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="c3873-106">[in] Marcadores definidos en Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="c3873-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="c3873-107">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c3873-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="c3873-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="c3873-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="c3873-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="c3873-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="c3873-110">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="c3873-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="c3873-111">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="c3873-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="c3873-112">[out] El valor devuelto `IAssemblyCacheItem` puntero.</span><span class="sxs-lookup"><span data-stu-id="c3873-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="c3873-113">[in, optional] Separados por comas, sin formato canónico `name=value` pares.</span><span class="sxs-lookup"><span data-stu-id="c3873-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3873-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3873-114">Requirements</span></span>  
 <span data-ttu-id="c3873-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3873-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3873-116">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="c3873-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c3873-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3873-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3873-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3873-118">See also</span></span>

- [<span data-ttu-id="c3873-119">IAssemblyCache (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c3873-119">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="c3873-120">IAssemblyCacheItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c3873-120">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
