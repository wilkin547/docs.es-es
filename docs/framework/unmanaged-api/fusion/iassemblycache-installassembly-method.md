---
title: IAssemblyCache::InstallAssembly (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyCache.InstallAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::InstallAssembly
helpviewer_keywords:
- InstallAssembly method [.NET Framework fusion]
- IAssemblyCache::InstallAssembly method [.NET Framework fusion]
ms.assetid: 33c1d269-c85e-4cb1-b0e6-1c510c8fb5fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 726a4ed8ee3d451687e0af671d948eb7648f7f58
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430029"
---
# <a name="iassemblycacheinstallassembly-method"></a><span data-ttu-id="a507a-102">IAssemblyCache::InstallAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="a507a-102">IAssemblyCache::InstallAssembly Method</span></span>
<span data-ttu-id="a507a-103">Instala al ensamblado especificado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="a507a-103">Installs the specified assembly in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a507a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a507a-104">Syntax</span></span>  
  
```  
HRESULT InstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszManifestFilePath,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a507a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a507a-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="a507a-106">[in] Marcadores definidos en Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="a507a-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="a507a-107">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a507a-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="a507a-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0 X 00000001)</span><span class="sxs-lookup"><span data-stu-id="a507a-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
-   <span data-ttu-id="a507a-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0 X 00000002)</span><span class="sxs-lookup"><span data-stu-id="a507a-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pszManifestFilePath`  
 <span data-ttu-id="a507a-110">[in] La ruta de acceso al manifiesto del ensamblado que se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="a507a-110">[in] The path to the manifest for the assembly to install.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="a507a-111">[in] A [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) estructura que contiene datos para la instalación.</span><span class="sxs-lookup"><span data-stu-id="a507a-111">[in] A [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure that contains data for the installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a507a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a507a-112">Requirements</span></span>  
 <span data-ttu-id="a507a-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a507a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a507a-114">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="a507a-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a507a-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a507a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a507a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a507a-116">See Also</span></span>  
 [<span data-ttu-id="a507a-117">IAssemblyCache (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a507a-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
