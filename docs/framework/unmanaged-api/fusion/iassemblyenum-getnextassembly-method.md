---
description: 'Más información acerca de: IAssemblyEnum:: GetNextAssembly ((método)'
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
ms.openlocfilehash: 52b264b1d8efad54168a6bf69fd0c715cbfa7e2a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760826"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="d1ee5-103">IAssemblyEnum::GetNextAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="d1ee5-103">IAssemblyEnum::GetNextAssembly Method</span></span>

<span data-ttu-id="d1ee5-104">Obtiene un puntero a la siguiente [IAssemblyName](iassemblyname-interface.md) incluida en este objeto [IAssemblyEnum](iassemblyenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d1ee5-104">Gets a pointer to the next [IAssemblyName](iassemblyname-interface.md) contained in this [IAssemblyEnum](iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1ee5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1ee5-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1ee5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d1ee5-106">Parameters</span></span>  

 `pvReserved`  
 <span data-ttu-id="d1ee5-107">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="d1ee5-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="d1ee5-108">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="d1ee5-108">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="d1ee5-109">enuncia Puntero devuelto `IAssemblyName` .</span><span class="sxs-lookup"><span data-stu-id="d1ee5-109">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d1ee5-110">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="d1ee5-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="d1ee5-111">`dwFlags` debe ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="d1ee5-111">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1ee5-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1ee5-112">Requirements</span></span>  

 <span data-ttu-id="d1ee5-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1ee5-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1ee5-114">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="d1ee5-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d1ee5-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1ee5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1ee5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1ee5-116">See also</span></span>

- [<span data-ttu-id="d1ee5-117">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d1ee5-117">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="d1ee5-118">IAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d1ee5-118">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
