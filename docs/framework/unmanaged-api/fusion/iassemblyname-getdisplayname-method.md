---
title: IAssemblyName::GetDisplayName (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetDisplayName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetDisplayName
helpviewer_keywords:
- GetDisplayName method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::GetDisplayName method [.NET Framework fusion]
ms.assetid: 9a26547a-9a34-4284-a463-78a7d4b496cf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ddcfe7a4066686da918cf5ed93aebec0d6f306f5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482046"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="50d1b-102">IAssemblyName::GetDisplayName (Método)</span><span class="sxs-lookup"><span data-stu-id="50d1b-102">IAssemblyName::GetDisplayName Method</span></span>
<span data-ttu-id="50d1b-103">Obtiene el nombre legible del ensamblado que hace referencia esta [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="50d1b-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50d1b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50d1b-104">Syntax</span></span>  
  
```  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50d1b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="50d1b-105">Parameters</span></span>  
 `szDisplayName`  
 <span data-ttu-id="50d1b-106">[out] El búfer de cadena que contiene el nombre del ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="50d1b-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="50d1b-107">[in, out] El tamaño de `szDisplayName` en caracteres anchos, incluido un carácter terminador nulo.</span><span class="sxs-lookup"><span data-stu-id="50d1b-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="50d1b-108">[in] Una combinación bit a bit de [ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md) valores que influyen en las características de `szDisplayName`.</span><span class="sxs-lookup"><span data-stu-id="50d1b-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50d1b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="50d1b-109">Requirements</span></span>  
 <span data-ttu-id="50d1b-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50d1b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50d1b-111">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="50d1b-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="50d1b-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50d1b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50d1b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="50d1b-113">See also</span></span>
- [<span data-ttu-id="50d1b-114">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="50d1b-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="50d1b-115">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="50d1b-115">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
