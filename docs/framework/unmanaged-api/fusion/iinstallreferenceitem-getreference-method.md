---
description: 'Más información sobre: IInstallReferenceItem (:: GetReference (método)'
title: IInstallReferenceItem::GetReference (Método)
ms.date: 03/30/2017
api_name:
- IInstallReferenceItem.GetReference
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceItem::GetReference
helpviewer_keywords:
- IInstallReferenceItem::GetReference method [.NET Framework fusion]
- GetReference method [.NET Framework fusion]
ms.assetid: 8960332f-c98a-405a-ba92-7003de0c1187
topic_type:
- apiref
ms.openlocfilehash: 88f5ca21b6f3494031e1cd232f71253e39d9e648
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800125"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="6494d-103">IInstallReferenceItem::GetReference (Método)</span><span class="sxs-lookup"><span data-stu-id="6494d-103">IInstallReferenceItem::GetReference Method</span></span>

<span data-ttu-id="6494d-104">Obtiene un puntero a la estructura [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) representada por este objeto [IInstallReferenceItem (](iinstallreferenceitem-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="6494d-104">Gets a pointer to the [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6494d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6494d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6494d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6494d-106">Parameters</span></span>  

 `ppRefData`  
 <span data-ttu-id="6494d-107">enuncia Puntero devuelto `FUSION_INSTALL_REFERENCE` .</span><span class="sxs-lookup"><span data-stu-id="6494d-107">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="6494d-108">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="6494d-108">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="6494d-109">`dwFlags` debe ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="6494d-109">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="6494d-110">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="6494d-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="6494d-111">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="6494d-111">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6494d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6494d-112">Requirements</span></span>  

 <span data-ttu-id="6494d-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6494d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6494d-114">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="6494d-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="6494d-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6494d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6494d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6494d-116">See also</span></span>

- [<span data-ttu-id="6494d-117">IInstallReferenceItem (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6494d-117">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="6494d-118">FUSION_INSTALL_REFERENCE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="6494d-118">FUSION_INSTALL_REFERENCE Structure</span></span>](fusion-install-reference-structure.md)
