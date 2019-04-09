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
ms.openlocfilehash: 7199fbc0c8760354269a50b647952729860c805b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155368"
---
# <a name="iassemblycacheinstallassembly-method"></a><span data-ttu-id="ea9b1-102">IAssemblyCache::InstallAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="ea9b1-102">IAssemblyCache::InstallAssembly Method</span></span>
<span data-ttu-id="ea9b1-103">Instala al ensamblado especificado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ea9b1-103">Installs the specified assembly in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea9b1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea9b1-104">Syntax</span></span>  
  
```  
HRESULT InstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszManifestFilePath,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea9b1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ea9b1-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="ea9b1-106">[in] Marcadores definidos en Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="ea9b1-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="ea9b1-107">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="ea9b1-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="ea9b1-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="ea9b1-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
-   <span data-ttu-id="ea9b1-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="ea9b1-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pszManifestFilePath`  
 <span data-ttu-id="ea9b1-110">[in] La ruta de acceso al manifiesto del ensamblado que se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="ea9b1-110">[in] The path to the manifest for the assembly to install.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="ea9b1-111">[in] Un [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) estructura que contiene datos para la instalación.</span><span class="sxs-lookup"><span data-stu-id="ea9b1-111">[in] A [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure that contains data for the installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea9b1-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ea9b1-112">Requirements</span></span>  
 <span data-ttu-id="ea9b1-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea9b1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea9b1-114">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ea9b1-114">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="ea9b1-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ea9b1-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ea9b1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea9b1-116">See also</span></span>

- [<span data-ttu-id="ea9b1-117">IAssemblyCache (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ea9b1-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
