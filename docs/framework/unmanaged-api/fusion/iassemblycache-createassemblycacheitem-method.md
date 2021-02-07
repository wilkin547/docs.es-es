---
description: 'Más información sobre: IAssemblyCache:: Createassemblycacheitem ((método)'
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
ms.openlocfilehash: 3377901d358bcf643ce0d30336c1c0cd8089e50c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760984"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="3607c-103">IAssemblyCache::CreateAssemblyCacheItem (Método)</span><span class="sxs-lookup"><span data-stu-id="3607c-103">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>

<span data-ttu-id="3607c-104">Obtiene una referencia a un nuevo objeto [IAssemblyCacheItem](iassemblycacheitem-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="3607c-104">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3607c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3607c-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3607c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3607c-106">Parameters</span></span>  

 `dwFlags`  
 <span data-ttu-id="3607c-107">de Marcas definidas en Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="3607c-107">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="3607c-108">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="3607c-108">The following values are supported:</span></span>  
  
- <span data-ttu-id="3607c-109">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="3607c-109">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="3607c-110">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="3607c-110">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="3607c-111">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="3607c-111">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="3607c-112">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="3607c-112">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="3607c-113">enuncia Puntero devuelto `IAssemblyCacheItem` .</span><span class="sxs-lookup"><span data-stu-id="3607c-113">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="3607c-114">[in, Optional] Pares no canónicos separados por comas `name=value` .</span><span class="sxs-lookup"><span data-stu-id="3607c-114">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3607c-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3607c-115">Requirements</span></span>  

 <span data-ttu-id="3607c-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3607c-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3607c-117">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="3607c-117">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3607c-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3607c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3607c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3607c-119">See also</span></span>

- [<span data-ttu-id="3607c-120">IAssemblyCache (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3607c-120">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="3607c-121">IAssemblyCacheItem (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3607c-121">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
