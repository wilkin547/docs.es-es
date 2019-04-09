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
ms.openlocfilehash: 648b641cbd2ec97305674451df06ce5be6a93a49
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183695"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="0ea11-102">IAssemblyCache::CreateAssemblyCacheItem (Método)</span><span class="sxs-lookup"><span data-stu-id="0ea11-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="0ea11-103">Obtiene una referencia a un nuevo [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="0ea11-103">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ea11-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ea11-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ea11-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0ea11-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="0ea11-106">[in] Marcadores definidos en Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="0ea11-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="0ea11-107">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="0ea11-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="0ea11-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="0ea11-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
-   <span data-ttu-id="0ea11-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="0ea11-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="0ea11-110">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="0ea11-110">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="0ea11-111">debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="0ea11-111">must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="0ea11-112">[out] El valor devuelto `IAssemblyCacheItem` puntero.</span><span class="sxs-lookup"><span data-stu-id="0ea11-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="0ea11-113">[in, optional] Separados por comas, sin formato canónico `name=value` pares.</span><span class="sxs-lookup"><span data-stu-id="0ea11-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ea11-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ea11-114">Requirements</span></span>  
 <span data-ttu-id="0ea11-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ea11-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ea11-116">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="0ea11-116">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="0ea11-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0ea11-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0ea11-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ea11-118">See also</span></span>

- [<span data-ttu-id="0ea11-119">IAssemblyCache (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0ea11-119">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="0ea11-120">IAssemblyCacheItem (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0ea11-120">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
