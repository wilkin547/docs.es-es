---
title: IAssemblyName::IsEqual (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyName.IsEqual
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::IsEqual
helpviewer_keywords:
- IsEqual method [.NET Framework fusion]
- IAssemblyName::IsEqual method [.NET Framework fusion]
ms.assetid: 6dfc220f-d0d4-45b3-bfce-5829f817766f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 926bdcee3a3c3974c8546f3a6dfe98f0b62c93c8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796564"
---
# <a name="iassemblynameisequal-method"></a><span data-ttu-id="3b210-102">IAssemblyName::IsEqual (Método)</span><span class="sxs-lookup"><span data-stu-id="3b210-102">IAssemblyName::IsEqual Method</span></span>
<span data-ttu-id="3b210-103">Determina si un objeto de [IAssemblyName](iassemblyname-interface.md) especificado es igual a `IAssemblyName`este, en función de las marcas de comparación especificadas.</span><span class="sxs-lookup"><span data-stu-id="3b210-103">Determines whether a specified [IAssemblyName](iassemblyname-interface.md) object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b210-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b210-104">Syntax</span></span>  
  
```cpp  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b210-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3b210-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="3b210-106">de Objeto `IAssemblyName` con el que se va a `IAssemblyName`comparar.</span><span class="sxs-lookup"><span data-stu-id="3b210-106">[in] The `IAssemblyName` object to which to compare this `IAssemblyName`.</span></span>  
  
 `dwCmpFlags`  
 <span data-ttu-id="3b210-107">de Combinación bit a bit de los valores de [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) que influyen en la comparación.</span><span class="sxs-lookup"><span data-stu-id="3b210-107">[in] A bitwise combination of [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) values that influence the comparison.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b210-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b210-108">Requirements</span></span>  
 <span data-ttu-id="3b210-109">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b210-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b210-110">**Encabezado**: Fusion. h</span><span class="sxs-lookup"><span data-stu-id="3b210-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3b210-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b210-111">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b210-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b210-112">See also</span></span>

- [<span data-ttu-id="3b210-113">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b210-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="3b210-114">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="3b210-114">Fusion Enumerations</span></span>](fusion-enumerations.md)
