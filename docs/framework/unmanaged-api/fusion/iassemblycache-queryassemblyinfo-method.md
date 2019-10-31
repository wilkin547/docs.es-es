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
ms.openlocfilehash: e975db68252e866a0bf7898f1c9d3cbe67bbe24f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134578"
---
# <a name="iassemblycachequeryassemblyinfo-method"></a><span data-ttu-id="511fe-102">IAssemblyCache::QueryAssemblyInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="511fe-102">IAssemblyCache::QueryAssemblyInfo Method</span></span>
<span data-ttu-id="511fe-103">Obtiene los datos solicitados sobre el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="511fe-103">Gets the requested data about the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="511fe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="511fe-104">Syntax</span></span>  
  
```cpp  
HRESULT QueryAssemblyInfo (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in, out] ASSEMBLY_INFO *pAsmInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="511fe-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="511fe-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="511fe-106">de Marcas definidas en Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="511fe-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="511fe-107">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="511fe-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="511fe-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="511fe-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span></span>  
  
- <span data-ttu-id="511fe-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="511fe-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="511fe-110">de Nombre del ensamblado para el que se recuperarán los datos.</span><span class="sxs-lookup"><span data-stu-id="511fe-110">[in] The name of the assembly for which data will be retrieved.</span></span>  
  
 `pAsmInfo`  
 <span data-ttu-id="511fe-111">[in, out] Estructura [ASSEMBLY_INFO](assembly-info-structure.md) que contiene datos sobre el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="511fe-111">[in, out] An [ASSEMBLY_INFO](assembly-info-structure.md) structure that contains data about the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="511fe-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="511fe-112">Requirements</span></span>  
 <span data-ttu-id="511fe-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="511fe-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="511fe-114">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="511fe-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="511fe-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="511fe-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="511fe-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="511fe-116">See also</span></span>

- [<span data-ttu-id="511fe-117">IAssemblyCache (interfaz)</span><span class="sxs-lookup"><span data-stu-id="511fe-117">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
