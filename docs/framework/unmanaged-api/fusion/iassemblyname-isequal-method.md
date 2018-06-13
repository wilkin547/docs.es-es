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
ms.openlocfilehash: 043394541f5ed91b85a57f4cb13c61cca442bfec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431846"
---
# <a name="iassemblynameisequal-method"></a><span data-ttu-id="d0829-102">IAssemblyName::IsEqual (Método)</span><span class="sxs-lookup"><span data-stu-id="d0829-102">IAssemblyName::IsEqual Method</span></span>
<span data-ttu-id="d0829-103">Determina si un determinado [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) es igual a este objeto `IAssemblyName`, en función de las marcas de comparación especificada.</span><span class="sxs-lookup"><span data-stu-id="d0829-103">Determines whether a specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0829-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0829-104">Syntax</span></span>  
  
```  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d0829-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d0829-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="d0829-106">[in] El `IAssemblyName` objeto que se va a comparar esta `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="d0829-106">[in] The `IAssemblyName` object to which to compare this `IAssemblyName`.</span></span>  
  
 `dwCmpFlags`  
 <span data-ttu-id="d0829-107">[in] Una combinación bit a bit de [ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md) valores que influyen en la comparación.</span><span class="sxs-lookup"><span data-stu-id="d0829-107">[in] A bitwise combination of [ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md) values that influence the comparison.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0829-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0829-108">Requirements</span></span>  
 <span data-ttu-id="d0829-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0829-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0829-110">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="d0829-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d0829-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0829-111">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0829-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0829-112">See Also</span></span>  
 [<span data-ttu-id="d0829-113">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d0829-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="d0829-114">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="d0829-114">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
