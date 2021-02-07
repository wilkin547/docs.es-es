---
description: 'Más información sobre: IAssemblyCache:: InstallAssembly ((método)'
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
ms.openlocfilehash: 0bb9fe31467506a03f5e81e5a29a6b1fb65f5804
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760951"
---
# <a name="iassemblycacheinstallassembly-method"></a><span data-ttu-id="2de71-103">IAssemblyCache::InstallAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="2de71-103">IAssemblyCache::InstallAssembly Method</span></span>

<span data-ttu-id="2de71-104">Instala el ensamblado especificado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="2de71-104">Installs the specified assembly in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2de71-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2de71-105">Syntax</span></span>  
  
```cpp  
HRESULT InstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszManifestFilePath,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2de71-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2de71-106">Parameters</span></span>  

 `dwFlags`  
 <span data-ttu-id="2de71-107">de Marcas definidas en Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="2de71-107">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="2de71-108">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="2de71-108">The following values are supported:</span></span>  
  
- <span data-ttu-id="2de71-109">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="2de71-109">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="2de71-110">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="2de71-110">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pszManifestFilePath`  
 <span data-ttu-id="2de71-111">de Ruta de acceso al manifiesto del ensamblado que se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="2de71-111">[in] The path to the manifest for the assembly to install.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="2de71-112">de [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) estructura que contiene los datos de la instalación.</span><span class="sxs-lookup"><span data-stu-id="2de71-112">[in] A [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure that contains data for the installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2de71-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2de71-113">Requirements</span></span>  

 <span data-ttu-id="2de71-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2de71-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2de71-115">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="2de71-115">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2de71-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2de71-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2de71-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2de71-117">See also</span></span>

- [<span data-ttu-id="2de71-118">IAssemblyCache (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2de71-118">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
