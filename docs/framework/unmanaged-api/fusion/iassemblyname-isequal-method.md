---
description: 'Más información sobre: IAssemblyName:: IsEqual (método)'
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
ms.openlocfilehash: f1bb0e26a217354e904ff79b397771d727a7a661
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760697"
---
# <a name="iassemblynameisequal-method"></a><span data-ttu-id="52609-103">IAssemblyName::IsEqual (Método)</span><span class="sxs-lookup"><span data-stu-id="52609-103">IAssemblyName::IsEqual Method</span></span>

<span data-ttu-id="52609-104">Determina si un objeto de [IAssemblyName](iassemblyname-interface.md) especificado es igual a este `IAssemblyName` , en función de las marcas de comparación especificadas.</span><span class="sxs-lookup"><span data-stu-id="52609-104">Determines whether a specified [IAssemblyName](iassemblyname-interface.md) object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52609-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52609-105">Syntax</span></span>  
  
```cpp  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52609-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52609-106">Parameters</span></span>  

 `pName`  
 <span data-ttu-id="52609-107">de Objeto con el que se va a `IAssemblyName` comparar `IAssemblyName` .</span><span class="sxs-lookup"><span data-stu-id="52609-107">[in] The `IAssemblyName` object to which to compare this `IAssemblyName`.</span></span>  
  
 `dwCmpFlags`  
 <span data-ttu-id="52609-108">de Combinación bit a bit de valores de [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) que influyen en la comparación.</span><span class="sxs-lookup"><span data-stu-id="52609-108">[in] A bitwise combination of [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) values that influence the comparison.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52609-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52609-109">Requirements</span></span>  

 <span data-ttu-id="52609-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52609-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52609-111">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="52609-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="52609-112">**Versiones de .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52609-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52609-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="52609-113">See also</span></span>

- [<span data-ttu-id="52609-114">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="52609-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="52609-115">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="52609-115">Fusion Enumerations</span></span>](fusion-enumerations.md)
