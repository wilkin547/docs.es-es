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
ms.openlocfilehash: bc7f1740d666211b63cd93e6f1c0e6955f61ec5d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503463"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="231da-102">IMetaDataImport::ResetEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="231da-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="231da-103">Restablece el enumerador especificado a la posición especificada.</span><span class="sxs-lookup"><span data-stu-id="231da-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="231da-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="231da-104">Syntax</span></span>  
  
```cpp  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="231da-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="231da-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="231da-106">de Enumerador que se va a restablecer.</span><span class="sxs-lookup"><span data-stu-id="231da-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="231da-107">de Nueva posición en la que se va a colocar el enumerador.</span><span class="sxs-lookup"><span data-stu-id="231da-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="231da-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="231da-108">Requirements</span></span>  
 <span data-ttu-id="231da-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="231da-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="231da-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="231da-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="231da-111">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="231da-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="231da-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="231da-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="231da-113">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="231da-113">See also</span></span>

- [<span data-ttu-id="231da-114">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="231da-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="231da-115">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="231da-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
