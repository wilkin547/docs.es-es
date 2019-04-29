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
ms.openlocfilehash: 80402234d9374fa4f16e1f8bb315536a9bdfb2c2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697217"
---
# <a name="iassemblynameisequal-method"></a><span data-ttu-id="56d96-102">IAssemblyName::IsEqual (Método)</span><span class="sxs-lookup"><span data-stu-id="56d96-102">IAssemblyName::IsEqual Method</span></span>
<span data-ttu-id="56d96-103">Determina si un [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) es igual a este objeto `IAssemblyName`, en función de las marcas de comparación especificado.</span><span class="sxs-lookup"><span data-stu-id="56d96-103">Determines whether a specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56d96-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56d96-104">Syntax</span></span>  
  
```  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56d96-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="56d96-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="56d96-106">[in] El `IAssemblyName` objeto al que se compara este `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="56d96-106">[in] The `IAssemblyName` object to which to compare this `IAssemblyName`.</span></span>  
  
 `dwCmpFlags`  
 <span data-ttu-id="56d96-107">[in] Una combinación bit a bit de [ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md) valores que influyen en la comparación.</span><span class="sxs-lookup"><span data-stu-id="56d96-107">[in] A bitwise combination of [ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md) values that influence the comparison.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56d96-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="56d96-108">Requirements</span></span>  
 <span data-ttu-id="56d96-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56d96-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56d96-110">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="56d96-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="56d96-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56d96-111">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56d96-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="56d96-112">See also</span></span>

- [<span data-ttu-id="56d96-113">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="56d96-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="56d96-114">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="56d96-114">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
