---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9395fcc6d896114c25770edbc17761323285099f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796396"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="fac0d-102">IInstallReferenceItem::GetReference (Método)</span><span class="sxs-lookup"><span data-stu-id="fac0d-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="fac0d-103">Obtiene un puntero a la estructura [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) representada por este objeto [IInstallReferenceItem (](iinstallreferenceitem-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="fac0d-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fac0d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fac0d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fac0d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fac0d-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="fac0d-106">enuncia Puntero devuelto `FUSION_INSTALL_REFERENCE` .</span><span class="sxs-lookup"><span data-stu-id="fac0d-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="fac0d-107">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="fac0d-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="fac0d-108">`dwFlags`debe ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="fac0d-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="fac0d-109">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="fac0d-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="fac0d-110">`pvReserved`debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="fac0d-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fac0d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fac0d-111">Requirements</span></span>  
 <span data-ttu-id="fac0d-112">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fac0d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fac0d-113">**Encabezado**: Fusion. h</span><span class="sxs-lookup"><span data-stu-id="fac0d-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="fac0d-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fac0d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac0d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="fac0d-115">See also</span></span>

- [<span data-ttu-id="fac0d-116">IInstallReferenceItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fac0d-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="fac0d-117">FUSION_INSTALL_REFERENCE (estructura)</span><span class="sxs-lookup"><span data-stu-id="fac0d-117">FUSION_INSTALL_REFERENCE Structure</span></span>](fusion-install-reference-structure.md)
