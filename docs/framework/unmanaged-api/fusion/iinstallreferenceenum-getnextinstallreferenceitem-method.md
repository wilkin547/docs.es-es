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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc04bb12e4271a3237ebef140c481620fc01ad7e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202383"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="63036-102">IInstallReferenceEnum::GetNextInstallReferenceItem (Método)</span><span class="sxs-lookup"><span data-stu-id="63036-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>
<span data-ttu-id="63036-103">Obtiene un puntero a la siguiente [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) contenida en esta instancia de objeto [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="63036-103">Gets a pointer to the next [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63036-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63036-104">Syntax</span></span>  
  
```  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63036-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="63036-105">Parameters</span></span>  
 `ppRefItem`  
 <span data-ttu-id="63036-106">[out] El valor devuelto `IInstallReferenceItem` puntero.</span><span class="sxs-lookup"><span data-stu-id="63036-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="63036-107">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="63036-107">[in] Reserved for future extensibility.</span></span> `dwFlags` <span data-ttu-id="63036-108">debe ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="63036-108">must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="63036-109">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="63036-109">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="63036-110">debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="63036-110">must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63036-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63036-111">Requirements</span></span>  
 <span data-ttu-id="63036-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63036-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63036-113">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="63036-113">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="63036-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="63036-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="63036-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="63036-115">See also</span></span>

- [<span data-ttu-id="63036-116">IInstallReferenceItem (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="63036-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
- [<span data-ttu-id="63036-117">IInstallReferenceEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="63036-117">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
