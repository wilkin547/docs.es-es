---
description: 'Más información sobre: IAssemblyCache:: UninstallAssembly ((método)'
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
ms.openlocfilehash: d50108b9090b4250e8a6cec1d9b5c54bb78dee9c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760906"
---
# <a name="iassemblycacheuninstallassembly-method"></a><span data-ttu-id="8cc21-103">IAssemblyCache::UninstallAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="8cc21-103">IAssemblyCache::UninstallAssembly Method</span></span>

<span data-ttu-id="8cc21-104">Desinstala el ensamblado especificado de la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="8cc21-104">Uninstalls the specified assembly from the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cc21-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8cc21-105">Syntax</span></span>  
  
```cpp  
HRESULT UninstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData,  
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cc21-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8cc21-106">Parameters</span></span>  

 `dwFlags`  
 <span data-ttu-id="8cc21-107">de Marcas definidas en Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="8cc21-107">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="8cc21-108">de Nombre del ensamblado que se va a desinstalar.</span><span class="sxs-lookup"><span data-stu-id="8cc21-108">[in] The name of the assembly to uninstall.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="8cc21-109">de [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) estructura que contiene los datos de instalación del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8cc21-109">[in] A [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure that contains the installation data for the assembly.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="8cc21-110">[out, opcional] Uno de los valores de disposición definidos en Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="8cc21-110">[out, optional] One of the disposition values defined in Fusion.idl.</span></span> <span data-ttu-id="8cc21-111">Entre los valores posibles figuran los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8cc21-111">Possible values include the following:</span></span>  
  
- <span data-ttu-id="8cc21-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span><span class="sxs-lookup"><span data-stu-id="8cc21-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span></span>  
  
- <span data-ttu-id="8cc21-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span><span class="sxs-lookup"><span data-stu-id="8cc21-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span></span>  
  
- <span data-ttu-id="8cc21-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span><span class="sxs-lookup"><span data-stu-id="8cc21-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span></span>  
  
- <span data-ttu-id="8cc21-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span><span class="sxs-lookup"><span data-stu-id="8cc21-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span></span>  
  
- <span data-ttu-id="8cc21-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span><span class="sxs-lookup"><span data-stu-id="8cc21-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span></span>  
  
- <span data-ttu-id="8cc21-117">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span><span class="sxs-lookup"><span data-stu-id="8cc21-117">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cc21-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8cc21-118">Requirements</span></span>  

 <span data-ttu-id="8cc21-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cc21-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cc21-120">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="8cc21-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8cc21-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cc21-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cc21-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="8cc21-122">See also</span></span>

- [<span data-ttu-id="8cc21-123">IAssemblyCache (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8cc21-123">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
