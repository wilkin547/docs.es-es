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
ms.openlocfilehash: 13d71a9da2539c45076e5eb92e153e37c1df4b47
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727918"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="9b760-102">IAssemblyName::GetDisplayName (Método)</span><span class="sxs-lookup"><span data-stu-id="9b760-102">IAssemblyName::GetDisplayName Method</span></span>

<span data-ttu-id="9b760-103">Obtiene el nombre legible del ensamblado al que hace referencia este objeto [IAssemblyName](iassemblyname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9b760-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b760-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b760-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b760-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9b760-105">Parameters</span></span>  

 `szDisplayName`  
 <span data-ttu-id="9b760-106">enuncia Búfer de cadena que contiene el nombre del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="9b760-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="9b760-107">[in, out] Tamaño de `szDisplayName` en caracteres anchos, incluido un carácter de terminador nulo.</span><span class="sxs-lookup"><span data-stu-id="9b760-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="9b760-108">de Combinación bit a bit de valores de [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) que influyen en las características de `szDisplayName` .</span><span class="sxs-lookup"><span data-stu-id="9b760-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b760-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9b760-109">Requirements</span></span>  

 <span data-ttu-id="9b760-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b760-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b760-111">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="9b760-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9b760-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b760-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b760-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9b760-113">See also</span></span>

- [<span data-ttu-id="9b760-114">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9b760-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="9b760-115">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="9b760-115">Fusion Enumerations</span></span>](fusion-enumerations.md)
