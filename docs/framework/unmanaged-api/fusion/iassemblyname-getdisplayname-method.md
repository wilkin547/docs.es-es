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
ms.openlocfilehash: 00a95646323a5ee08d6758b0f6a7c493c661705d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431781"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="8be48-102">IAssemblyName::GetDisplayName (Método)</span><span class="sxs-lookup"><span data-stu-id="8be48-102">IAssemblyName::GetDisplayName Method</span></span>
<span data-ttu-id="8be48-103">Obtiene el nombre legible del ensamblado que hace referencia esta [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="8be48-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8be48-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8be48-104">Syntax</span></span>  
  
```  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8be48-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8be48-105">Parameters</span></span>  
 `szDisplayName`  
 <span data-ttu-id="8be48-106">[out] El búfer de cadena que contiene el nombre del ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="8be48-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="8be48-107">[entrada, salida] El tamaño de `szDisplayName` en caracteres anchos, incluido el carácter de terminador nulo.</span><span class="sxs-lookup"><span data-stu-id="8be48-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="8be48-108">[in] Una combinación bit a bit de [ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md) valores que influyen en las características de `szDisplayName`.</span><span class="sxs-lookup"><span data-stu-id="8be48-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8be48-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8be48-109">Requirements</span></span>  
 <span data-ttu-id="8be48-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8be48-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8be48-111">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="8be48-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8be48-112">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8be48-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8be48-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="8be48-113">See Also</span></span>  
 [<span data-ttu-id="8be48-114">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8be48-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="8be48-115">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="8be48-115">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
