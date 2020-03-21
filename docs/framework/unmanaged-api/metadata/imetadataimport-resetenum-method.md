---
title: IMetaDataImport::ResetEnum (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResetEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResetEnum
helpviewer_keywords:
- ResetEnum method [.NET Framework metadata]
- IMetaDataImport::ResetEnum method [.NET Framework metadata]
ms.assetid: dda867b5-1050-49ba-b01c-fcc83b7a5617
topic_type:
- apiref
ms.openlocfilehash: 3dd82588cf2dbf92fdda66fd7674c17ddc8b7306
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177191"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="bb40d-102">IMetaDataImport::ResetEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="bb40d-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="bb40d-103">Restablece el enumerador especificado a la posición especificada.</span><span class="sxs-lookup"><span data-stu-id="bb40d-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb40d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb40d-104">Syntax</span></span>  
  
```cpp  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb40d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bb40d-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="bb40d-106">[en] El enumerador que se ha de restablecer.</span><span class="sxs-lookup"><span data-stu-id="bb40d-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="bb40d-107">[en] La nueva posición en la que colocar el enumerador.</span><span class="sxs-lookup"><span data-stu-id="bb40d-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb40d-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb40d-108">Requirements</span></span>  
 <span data-ttu-id="bb40d-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb40d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb40d-110">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bb40d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bb40d-111">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bb40d-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bb40d-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb40d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb40d-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bb40d-113">See also</span></span>

- [<span data-ttu-id="bb40d-114">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb40d-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="bb40d-115">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb40d-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
