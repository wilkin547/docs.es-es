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
ms.openlocfilehash: 23bc251053dd27a7c5accb48ab4759ecdb79fe09
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134305"
---
# <a name="iassemblynameisequal-method"></a><span data-ttu-id="f4ef6-102">IAssemblyName::IsEqual (Método)</span><span class="sxs-lookup"><span data-stu-id="f4ef6-102">IAssemblyName::IsEqual Method</span></span>
<span data-ttu-id="f4ef6-103">Determina si un objeto [IAssemblyName](iassemblyname-interface.md) especificado es igual a este `IAssemblyName`, en función de las marcas de comparación especificadas.</span><span class="sxs-lookup"><span data-stu-id="f4ef6-103">Determines whether a specified [IAssemblyName](iassemblyname-interface.md) object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4ef6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4ef6-104">Syntax</span></span>  
  
```cpp  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4ef6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4ef6-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="f4ef6-106">de Objeto `IAssemblyName` en el que se va a comparar este `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="f4ef6-106">[in] The `IAssemblyName` object to which to compare this `IAssemblyName`.</span></span>  
  
 `dwCmpFlags`  
 <span data-ttu-id="f4ef6-107">de Combinación bit a bit de los valores de [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) que influyen en la comparación.</span><span class="sxs-lookup"><span data-stu-id="f4ef6-107">[in] A bitwise combination of [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) values that influence the comparison.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4ef6-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4ef6-108">Requirements</span></span>  
 <span data-ttu-id="f4ef6-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4ef6-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4ef6-110">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="f4ef6-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f4ef6-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4ef6-111">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4ef6-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4ef6-112">See also</span></span>

- [<span data-ttu-id="f4ef6-113">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4ef6-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="f4ef6-114">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="f4ef6-114">Fusion Enumerations</span></span>](fusion-enumerations.md)
