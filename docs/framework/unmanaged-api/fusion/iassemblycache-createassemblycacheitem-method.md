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
ms.openlocfilehash: 215eb3a508a746230d36fdda3e8ba992287be62c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796832"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="305a1-102">IAssemblyCache::CreateAssemblyCacheItem (Método)</span><span class="sxs-lookup"><span data-stu-id="305a1-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="305a1-103">Obtiene una referencia a un nuevo objeto [IAssemblyCacheItem](iassemblycacheitem-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="305a1-103">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="305a1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="305a1-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="305a1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="305a1-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="305a1-106">de Marcas definidas en Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="305a1-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="305a1-107">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="305a1-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="305a1-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="305a1-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="305a1-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="305a1-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="305a1-110">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="305a1-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="305a1-111">`pvReserved`debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="305a1-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="305a1-112">enuncia Puntero devuelto `IAssemblyCacheItem` .</span><span class="sxs-lookup"><span data-stu-id="305a1-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="305a1-113">[in, Optional] Pares no canónicos separados por `name=value` comas.</span><span class="sxs-lookup"><span data-stu-id="305a1-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="305a1-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="305a1-114">Requirements</span></span>  
 <span data-ttu-id="305a1-115">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="305a1-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="305a1-116">**Encabezado**: Fusion. h</span><span class="sxs-lookup"><span data-stu-id="305a1-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="305a1-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="305a1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="305a1-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="305a1-118">See also</span></span>

- [<span data-ttu-id="305a1-119">IAssemblyCache (interfaz)</span><span class="sxs-lookup"><span data-stu-id="305a1-119">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="305a1-120">IAssemblyCacheItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="305a1-120">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
