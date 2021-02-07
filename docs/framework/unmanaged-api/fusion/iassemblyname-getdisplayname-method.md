---
description: 'Más información acerca de: IAssemblyName:: GetDisplayName (método)'
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
ms.openlocfilehash: 9b52a901385fa9b3ba7cb6bcd1678d0718f8f695
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760763"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="f4973-103">IAssemblyName::GetDisplayName (Método)</span><span class="sxs-lookup"><span data-stu-id="f4973-103">IAssemblyName::GetDisplayName Method</span></span>

<span data-ttu-id="f4973-104">Obtiene el nombre legible del ensamblado al que hace referencia este objeto [IAssemblyName](iassemblyname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f4973-104">Gets the human-readable name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4973-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4973-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4973-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4973-106">Parameters</span></span>  

 `szDisplayName`  
 <span data-ttu-id="f4973-107">enuncia Búfer de cadena que contiene el nombre del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="f4973-107">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="f4973-108">[in, out] Tamaño de `szDisplayName` en caracteres anchos, incluido un carácter de terminador nulo.</span><span class="sxs-lookup"><span data-stu-id="f4973-108">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="f4973-109">de Combinación bit a bit de valores de [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) que influyen en las características de `szDisplayName` .</span><span class="sxs-lookup"><span data-stu-id="f4973-109">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4973-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4973-110">Requirements</span></span>  

 <span data-ttu-id="f4973-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4973-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4973-112">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="f4973-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f4973-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4973-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4973-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4973-114">See also</span></span>

- [<span data-ttu-id="f4973-115">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4973-115">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="f4973-116">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="f4973-116">Fusion Enumerations</span></span>](fusion-enumerations.md)
