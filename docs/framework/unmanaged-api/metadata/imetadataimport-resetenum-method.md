---
description: 'Más información sobre: IMetaDataImport:: Resetenum ((método)'
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
ms.openlocfilehash: 7b1572be2e2b905e6db5cf6e422643dbb76ca9be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670585"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="9f21b-103">IMetaDataImport::ResetEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="9f21b-103">IMetaDataImport::ResetEnum Method</span></span>

<span data-ttu-id="9f21b-104">Restablece el enumerador especificado a la posición especificada.</span><span class="sxs-lookup"><span data-stu-id="9f21b-104">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f21b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f21b-105">Syntax</span></span>  
  
```cpp  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f21b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9f21b-106">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="9f21b-107">de Enumerador que se va a restablecer.</span><span class="sxs-lookup"><span data-stu-id="9f21b-107">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="9f21b-108">de Nueva posición en la que se va a colocar el enumerador.</span><span class="sxs-lookup"><span data-stu-id="9f21b-108">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f21b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f21b-109">Requirements</span></span>  

 <span data-ttu-id="9f21b-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f21b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f21b-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9f21b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9f21b-112">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9f21b-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9f21b-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f21b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f21b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f21b-114">See also</span></span>

- [<span data-ttu-id="9f21b-115">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9f21b-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="9f21b-116">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9f21b-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
