---
title: IAssemblyCache::UninstallAssembly (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyCache.UninstallAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::UninstallAssembly
helpviewer_keywords:
- UninstallAssembly method [.NET Framework fusion]
- IAssemblyCache::UninstallAssembly method [.NET Framework fusion]
ms.assetid: 973b2c44-8dfc-40c1-9035-10f4846627e9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75ef24162adbb653671ed070587e7155fae6b949
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079115"
---
# <a name="iassemblycacheuninstallassembly-method"></a><span data-ttu-id="92ac5-102">IAssemblyCache::UninstallAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="92ac5-102">IAssemblyCache::UninstallAssembly Method</span></span>
<span data-ttu-id="92ac5-103">Desinstala el ensamblado especificado de la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="92ac5-103">Uninstalls the specified assembly from the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92ac5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="92ac5-104">Syntax</span></span>  
  
```  
HRESULT UninstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData,  
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92ac5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="92ac5-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="92ac5-106">[in] Marcadores definidos en Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="92ac5-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="92ac5-107">[in] El nombre del ensamblado que se va a desinstalar.</span><span class="sxs-lookup"><span data-stu-id="92ac5-107">[in] The name of the assembly to uninstall.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="92ac5-108">[in] Un [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) estructura que contiene los datos de instalación para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="92ac5-108">[in] A [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure that contains the installation data for the assembly.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="92ac5-109">[out, optional] Uno de los valores de disposición definidos en Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="92ac5-109">[out, optional] One of the disposition values defined in Fusion.idl.</span></span> <span data-ttu-id="92ac5-110">Los valores posibles incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="92ac5-110">Possible values include the following:</span></span>  
  
-   <span data-ttu-id="92ac5-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span><span class="sxs-lookup"><span data-stu-id="92ac5-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span></span>  
  
-   <span data-ttu-id="92ac5-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span><span class="sxs-lookup"><span data-stu-id="92ac5-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span></span>  
  
-   <span data-ttu-id="92ac5-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span><span class="sxs-lookup"><span data-stu-id="92ac5-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span></span>  
  
-   <span data-ttu-id="92ac5-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span><span class="sxs-lookup"><span data-stu-id="92ac5-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span></span>  
  
-   <span data-ttu-id="92ac5-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span><span class="sxs-lookup"><span data-stu-id="92ac5-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span></span>  
  
-   <span data-ttu-id="92ac5-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span><span class="sxs-lookup"><span data-stu-id="92ac5-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92ac5-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="92ac5-117">Requirements</span></span>  
 <span data-ttu-id="92ac5-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92ac5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92ac5-119">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="92ac5-119">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="92ac5-120">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="92ac5-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="92ac5-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="92ac5-121">See also</span></span>

- [<span data-ttu-id="92ac5-122">IAssemblyCache (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="92ac5-122">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
