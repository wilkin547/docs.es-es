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
ms.openlocfilehash: 014bd4f2b12c84790065f76a67765aaf35e8b2d8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131676"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="e7cee-102">IInstallReferenceItem::GetReference (Método)</span><span class="sxs-lookup"><span data-stu-id="e7cee-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="e7cee-103">Obtiene un puntero a la estructura [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) representada por este objeto [IInstallReferenceItem (](iinstallreferenceitem-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e7cee-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7cee-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7cee-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7cee-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e7cee-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="e7cee-106">enuncia Puntero `FUSION_INSTALL_REFERENCE` devuelto.</span><span class="sxs-lookup"><span data-stu-id="e7cee-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e7cee-107">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="e7cee-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="e7cee-108">`dwFlags` debe ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="e7cee-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="e7cee-109">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="e7cee-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="e7cee-110">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="e7cee-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7cee-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7cee-111">Requirements</span></span>  
 <span data-ttu-id="e7cee-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7cee-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7cee-113">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="e7cee-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e7cee-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7cee-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7cee-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7cee-115">See also</span></span>

- [<span data-ttu-id="e7cee-116">IInstallReferenceItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e7cee-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="e7cee-117">FUSION_INSTALL_REFERENCE (estructura)</span><span class="sxs-lookup"><span data-stu-id="e7cee-117">FUSION_INSTALL_REFERENCE Structure</span></span>](fusion-install-reference-structure.md)
