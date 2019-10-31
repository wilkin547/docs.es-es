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
ms.openlocfilehash: 539a8edf6d7248235a6e672edc9464679a2eab82
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134496"
---
# <a name="iassemblycacheuninstallassembly-method"></a><span data-ttu-id="d2060-102">IAssemblyCache::UninstallAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="d2060-102">IAssemblyCache::UninstallAssembly Method</span></span>
<span data-ttu-id="d2060-103">Desinstala el ensamblado especificado de la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="d2060-103">Uninstalls the specified assembly from the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2060-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2060-104">Syntax</span></span>  
  
```cpp  
HRESULT UninstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData,  
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2060-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d2060-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="d2060-106">de Marcas definidas en Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="d2060-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="d2060-107">de Nombre del ensamblado que se va a desinstalar.</span><span class="sxs-lookup"><span data-stu-id="d2060-107">[in] The name of the assembly to uninstall.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="d2060-108">de Estructura [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) que contiene los datos de instalación del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d2060-108">[in] A [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure that contains the installation data for the assembly.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="d2060-109">[out, opcional] Uno de los valores de disposición definidos en Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="d2060-109">[out, optional] One of the disposition values defined in Fusion.idl.</span></span> <span data-ttu-id="d2060-110">Entre los valores posibles se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d2060-110">Possible values include the following:</span></span>  
  
- <span data-ttu-id="d2060-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span><span class="sxs-lookup"><span data-stu-id="d2060-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span></span>  
  
- <span data-ttu-id="d2060-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span><span class="sxs-lookup"><span data-stu-id="d2060-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span></span>  
  
- <span data-ttu-id="d2060-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span><span class="sxs-lookup"><span data-stu-id="d2060-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span></span>  
  
- <span data-ttu-id="d2060-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span><span class="sxs-lookup"><span data-stu-id="d2060-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span></span>  
  
- <span data-ttu-id="d2060-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span><span class="sxs-lookup"><span data-stu-id="d2060-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span></span>  
  
- <span data-ttu-id="d2060-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span><span class="sxs-lookup"><span data-stu-id="d2060-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2060-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2060-117">Requirements</span></span>  
 <span data-ttu-id="d2060-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2060-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2060-119">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="d2060-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d2060-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2060-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2060-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2060-121">See also</span></span>

- [<span data-ttu-id="d2060-122">IAssemblyCache (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d2060-122">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
