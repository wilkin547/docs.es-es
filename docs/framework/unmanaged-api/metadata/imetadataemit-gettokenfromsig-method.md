---
description: 'Más información sobre: IMetaDataEmit:: GetTokenFromSig ((método)'
title: IMetaDataEmit::GetTokenFromSig (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromSig
helpviewer_keywords:
- IMetaDataEmit::GetTokenFromSig method [.NET Framework metadata]
- GetTokenFromSig method [.NET Framework metadata]
ms.assetid: 50a58a83-6287-40a4-b315-47823cea0a5c
topic_type:
- apiref
ms.openlocfilehash: 3b9b38389a2bf78a65baa2cf96e3a422c54d0bcb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783929"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="e22be-103">IMetaDataEmit::GetTokenFromSig (Método)</span><span class="sxs-lookup"><span data-stu-id="e22be-103">IMetaDataEmit::GetTokenFromSig Method</span></span>

<span data-ttu-id="e22be-104">Obtiene un token para la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="e22be-104">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e22be-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e22be-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromSig (
    [in]  PCCOR_SIGNATURE pvSig,
    [in]  ULONG       cbSig,
    [out] mdSignature *pmsig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e22be-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e22be-106">Parameters</span></span>  

 `pvSig`  
 <span data-ttu-id="e22be-107">de Firma que se va a conservar y almacenar.</span><span class="sxs-lookup"><span data-stu-id="e22be-107">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="e22be-108">de Recuento de bytes de `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="e22be-108">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="e22be-109">enuncia El `mdSignature` token asignado.</span><span class="sxs-lookup"><span data-stu-id="e22be-109">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e22be-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e22be-110">Requirements</span></span>  

 <span data-ttu-id="e22be-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e22be-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e22be-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e22be-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e22be-113">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e22be-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e22be-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e22be-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e22be-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e22be-115">See also</span></span>

- [<span data-ttu-id="e22be-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e22be-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="e22be-117">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e22be-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
