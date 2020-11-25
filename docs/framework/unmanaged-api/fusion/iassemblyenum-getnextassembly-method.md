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
ms.openlocfilehash: af43d9cf4d5aa790036a13d060fc6ccf113f335d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719897"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="e3631-102">IAssemblyEnum::GetNextAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="e3631-102">IAssemblyEnum::GetNextAssembly Method</span></span>

<span data-ttu-id="e3631-103">Obtiene un puntero a la siguiente [IAssemblyName](iassemblyname-interface.md) incluida en este objeto [IAssemblyEnum](iassemblyenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e3631-103">Gets a pointer to the next [IAssemblyName](iassemblyname-interface.md) contained in this [IAssemblyEnum](iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3631-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3631-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3631-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e3631-105">Parameters</span></span>  

 `pvReserved`  
 <span data-ttu-id="e3631-106">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="e3631-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="e3631-107">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="e3631-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="e3631-108">enuncia Puntero devuelto `IAssemblyName` .</span><span class="sxs-lookup"><span data-stu-id="e3631-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e3631-109">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="e3631-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="e3631-110">`dwFlags` debe ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="e3631-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3631-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e3631-111">Requirements</span></span>  

 <span data-ttu-id="e3631-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3631-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3631-113">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="e3631-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e3631-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3631-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3631-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e3631-115">See also</span></span>

- [<span data-ttu-id="e3631-116">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3631-116">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="e3631-117">IAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3631-117">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
