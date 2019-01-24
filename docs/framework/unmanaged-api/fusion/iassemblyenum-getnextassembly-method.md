---
title: IAssemblyEnum::GetNextAssembly (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 563784dd2fe3881cbf3278992ca2c75a94df1d3f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727565"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="ed917-102">IAssemblyEnum::GetNextAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="ed917-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="ed917-103">Obtiene un puntero a la siguiente [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) incluidos en este [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="ed917-103">Gets a pointer to the next [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) contained in this [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed917-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed917-104">Syntax</span></span>  
  
```  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed917-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ed917-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="ed917-106">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="ed917-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="ed917-107">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="ed917-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="ed917-108">[out] El valor devuelto `IAssemblyName` puntero.</span><span class="sxs-lookup"><span data-stu-id="ed917-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ed917-109">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="ed917-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="ed917-110">`dwFlags` debe ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="ed917-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed917-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed917-111">Requirements</span></span>  
 <span data-ttu-id="ed917-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed917-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed917-113">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ed917-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ed917-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed917-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed917-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed917-115">See also</span></span>
- [<span data-ttu-id="ed917-116">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed917-116">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="ed917-117">IAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed917-117">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
