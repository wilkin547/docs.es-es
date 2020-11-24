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
ms.openlocfilehash: 36a2a609e95740ffc45722635a7e1f09e0ed5601
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670789"
---
# <a name="iassemblycacheuninstallassembly-method"></a><span data-ttu-id="3c193-102">IAssemblyCache::UninstallAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="3c193-102">IAssemblyCache::UninstallAssembly Method</span></span>

<span data-ttu-id="3c193-103">Desinstala el ensamblado especificado de la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3c193-103">Uninstalls the specified assembly from the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c193-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c193-104">Syntax</span></span>  
  
```cpp  
HRESULT UninstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData,  
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c193-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c193-105">Parameters</span></span>  

 `dwFlags`  
 <span data-ttu-id="3c193-106">de Marcas definidas en Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="3c193-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="3c193-107">de Nombre del ensamblado que se va a desinstalar.</span><span class="sxs-lookup"><span data-stu-id="3c193-107">[in] The name of the assembly to uninstall.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="3c193-108">de [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) estructura que contiene los datos de instalación del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3c193-108">[in] A [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure that contains the installation data for the assembly.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="3c193-109">[out, opcional] Uno de los valores de disposición definidos en Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="3c193-109">[out, optional] One of the disposition values defined in Fusion.idl.</span></span> <span data-ttu-id="3c193-110">Entre los valores posibles figuran los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3c193-110">Possible values include the following:</span></span>  
  
- <span data-ttu-id="3c193-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span><span class="sxs-lookup"><span data-stu-id="3c193-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span></span>  
  
- <span data-ttu-id="3c193-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span><span class="sxs-lookup"><span data-stu-id="3c193-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span></span>  
  
- <span data-ttu-id="3c193-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span><span class="sxs-lookup"><span data-stu-id="3c193-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span></span>  
  
- <span data-ttu-id="3c193-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span><span class="sxs-lookup"><span data-stu-id="3c193-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span></span>  
  
- <span data-ttu-id="3c193-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span><span class="sxs-lookup"><span data-stu-id="3c193-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span></span>  
  
- <span data-ttu-id="3c193-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span><span class="sxs-lookup"><span data-stu-id="3c193-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c193-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c193-117">Requirements</span></span>  

 <span data-ttu-id="3c193-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c193-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c193-119">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="3c193-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3c193-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c193-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c193-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c193-121">See also</span></span>

- [<span data-ttu-id="3c193-122">IAssemblyCache (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3c193-122">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
