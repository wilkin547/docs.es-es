---
description: 'Más información sobre: IInstallReferenceEnum (:: GetNextInstallReferenceItem ((método)'
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
ms.openlocfilehash: d410407fe16a46b45786ff74f694aaa8931be542
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800128"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="4aaab-103">IInstallReferenceEnum::GetNextInstallReferenceItem (Método)</span><span class="sxs-lookup"><span data-stu-id="4aaab-103">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>

<span data-ttu-id="4aaab-104">Obtiene un puntero al siguiente objeto [IInstallReferenceItem (](iinstallreferenceitem-interface.md) incluido en este objeto [IInstallReferenceEnum (](iinstallreferenceenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4aaab-104">Gets a pointer to the next [IInstallReferenceItem](iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4aaab-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4aaab-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4aaab-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4aaab-106">Parameters</span></span>  

 `ppRefItem`  
 <span data-ttu-id="4aaab-107">enuncia Puntero devuelto `IInstallReferenceItem` .</span><span class="sxs-lookup"><span data-stu-id="4aaab-107">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="4aaab-108">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="4aaab-108">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="4aaab-109">`dwFlags` debe ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="4aaab-109">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="4aaab-110">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="4aaab-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="4aaab-111">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="4aaab-111">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4aaab-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4aaab-112">Requirements</span></span>  

 <span data-ttu-id="4aaab-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4aaab-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4aaab-114">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="4aaab-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4aaab-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4aaab-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aaab-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4aaab-116">See also</span></span>

- [<span data-ttu-id="4aaab-117">IInstallReferenceItem (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4aaab-117">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="4aaab-118">IInstallReferenceEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4aaab-118">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
