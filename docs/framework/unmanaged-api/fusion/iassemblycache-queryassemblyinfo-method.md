---
title: "IAssemblyCache::QueryAssemblyInfo (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCache.QueryAssemblyInfo
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCache::QueryAssemblyInfo
helpviewer_keywords:
- IAssemblyCache::QueryAssemblyInfo method [.NET Framework fusion]
- QueryAssemblyInfo method [.NET Framework fusion]
ms.assetid: 09313cb5-06f6-43bd-94f4-1055c6b0c99a
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 567ff7fc5b9038c4af9aa04e3a07d9585adf44fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblycachequeryassemblyinfo-method"></a><span data-ttu-id="92e01-102">IAssemblyCache::QueryAssemblyInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="92e01-102">IAssemblyCache::QueryAssemblyInfo Method</span></span>
<span data-ttu-id="92e01-103">Obtiene los datos solicitados sobre el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="92e01-103">Gets the requested data about the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92e01-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="92e01-104">Syntax</span></span>  
  
```  
HRESULT QueryAssemblyInfo (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in, out] ASSEMBLY_INFO *pAsmInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92e01-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="92e01-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="92e01-106">[in] Marcadores definidos en Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="92e01-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="92e01-107">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="92e01-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="92e01-108">QUERYASMINFO_FLAG_VALIDATE (0 X 00000001)</span><span class="sxs-lookup"><span data-stu-id="92e01-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span></span>  
  
-   <span data-ttu-id="92e01-109">QUERYASMINFO_FLAG_GETSIZE (0 X 00000002)</span><span class="sxs-lookup"><span data-stu-id="92e01-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="92e01-110">[in] El nombre del ensamblado para el que se recuperarán los datos.</span><span class="sxs-lookup"><span data-stu-id="92e01-110">[in] The name of the assembly for which data will be retrieved.</span></span>  
  
 `pAsmInfo`  
 <span data-ttu-id="92e01-111">[entrada, salida] Un [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) estructura que contiene datos sobre el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="92e01-111">[in, out] An [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) structure that contains data about the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92e01-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="92e01-112">Requirements</span></span>  
 <span data-ttu-id="92e01-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92e01-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92e01-114">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="92e01-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="92e01-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92e01-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92e01-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="92e01-116">See Also</span></span>  
 [<span data-ttu-id="92e01-117">IAssemblyCache (interfaz)</span><span class="sxs-lookup"><span data-stu-id="92e01-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
