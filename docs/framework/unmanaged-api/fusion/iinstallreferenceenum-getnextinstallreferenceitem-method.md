---
title: IInstallReferenceEnum::GetNextInstallReferenceItem (Método)
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum.GetNextInstallReferenceItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem
helpviewer_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem method [.NET Framework fusion]
- GetNextInstallReferenceItem method [.NET Framework fusion]
ms.assetid: ce969c9d-6538-4c34-8784-148ffd99fe7a
topic_type:
- apiref
ms.openlocfilehash: e093de7d2c2388274cbe9ebbe46084ee6ae3ff8c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721106"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="e47f0-102">IInstallReferenceEnum::GetNextInstallReferenceItem (Método)</span><span class="sxs-lookup"><span data-stu-id="e47f0-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>

<span data-ttu-id="e47f0-103">Obtiene un puntero al siguiente objeto [IInstallReferenceItem (](iinstallreferenceitem-interface.md) incluido en este objeto [IInstallReferenceEnum (](iinstallreferenceenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e47f0-103">Gets a pointer to the next [IInstallReferenceItem](iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e47f0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e47f0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e47f0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e47f0-105">Parameters</span></span>  

 `ppRefItem`  
 <span data-ttu-id="e47f0-106">enuncia Puntero devuelto `IInstallReferenceItem` .</span><span class="sxs-lookup"><span data-stu-id="e47f0-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e47f0-107">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="e47f0-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="e47f0-108">`dwFlags` debe ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="e47f0-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="e47f0-109">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="e47f0-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="e47f0-110">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="e47f0-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e47f0-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e47f0-111">Requirements</span></span>  

 <span data-ttu-id="e47f0-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e47f0-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e47f0-113">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="e47f0-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e47f0-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e47f0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e47f0-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e47f0-115">See also</span></span>

- [<span data-ttu-id="e47f0-116">IInstallReferenceItem (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e47f0-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="e47f0-117">IInstallReferenceEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e47f0-117">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
