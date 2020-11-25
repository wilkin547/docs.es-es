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
ms.openlocfilehash: 230b904dd1cca1a1289713e3df7a709bd1c3a22b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696913"
---
# <a name="iassemblycacheinstallassembly-method"></a><span data-ttu-id="fdb09-102">IAssemblyCache::InstallAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="fdb09-102">IAssemblyCache::InstallAssembly Method</span></span>

<span data-ttu-id="fdb09-103">Instala el ensamblado especificado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="fdb09-103">Installs the specified assembly in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdb09-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fdb09-104">Syntax</span></span>  
  
```cpp  
HRESULT InstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszManifestFilePath,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdb09-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fdb09-105">Parameters</span></span>  

 `dwFlags`  
 <span data-ttu-id="fdb09-106">de Marcas definidas en Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="fdb09-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="fdb09-107">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="fdb09-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="fdb09-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="fdb09-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="fdb09-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="fdb09-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pszManifestFilePath`  
 <span data-ttu-id="fdb09-110">de Ruta de acceso al manifiesto del ensamblado que se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="fdb09-110">[in] The path to the manifest for the assembly to install.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="fdb09-111">de [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) estructura que contiene los datos de la instalación.</span><span class="sxs-lookup"><span data-stu-id="fdb09-111">[in] A [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure that contains data for the installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdb09-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fdb09-112">Requirements</span></span>  

 <span data-ttu-id="fdb09-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdb09-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdb09-114">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="fdb09-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="fdb09-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdb09-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdb09-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fdb09-116">See also</span></span>

- [<span data-ttu-id="fdb09-117">IAssemblyCache (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fdb09-117">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
