---
title: IAssemblyCache::QueryAssemblyInfo (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyCache.QueryAssemblyInfo
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::QueryAssemblyInfo
helpviewer_keywords:
- IAssemblyCache::QueryAssemblyInfo method [.NET Framework fusion]
- QueryAssemblyInfo method [.NET Framework fusion]
ms.assetid: 09313cb5-06f6-43bd-94f4-1055c6b0c99a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81b647032b2e9474e3b4472552ed884cec92ffc3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216435"
---
# <a name="iassemblycachequeryassemblyinfo-method"></a><span data-ttu-id="b0d67-102">IAssemblyCache::QueryAssemblyInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="b0d67-102">IAssemblyCache::QueryAssemblyInfo Method</span></span>
<span data-ttu-id="b0d67-103">Obtiene los datos solicitados sobre el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="b0d67-103">Gets the requested data about the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0d67-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0d67-104">Syntax</span></span>  
  
```  
HRESULT QueryAssemblyInfo (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in, out] ASSEMBLY_INFO *pAsmInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0d67-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b0d67-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="b0d67-106">[in] Marcadores definidos en Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="b0d67-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="b0d67-107">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="b0d67-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="b0d67-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="b0d67-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span></span>  
  
-   <span data-ttu-id="b0d67-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="b0d67-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="b0d67-110">[in] El nombre del ensamblado para el que se recuperarán los datos.</span><span class="sxs-lookup"><span data-stu-id="b0d67-110">[in] The name of the assembly for which data will be retrieved.</span></span>  
  
 `pAsmInfo`  
 <span data-ttu-id="b0d67-111">[in, out] Un [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) estructura que contiene datos sobre el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b0d67-111">[in, out] An [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) structure that contains data about the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0d67-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0d67-112">Requirements</span></span>  
 <span data-ttu-id="b0d67-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0d67-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0d67-114">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="b0d67-114">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="b0d67-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b0d67-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b0d67-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0d67-116">See also</span></span>

- [<span data-ttu-id="b0d67-117">IAssemblyCache (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b0d67-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
