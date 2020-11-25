---
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
ms.openlocfilehash: b41891227d94b66bf59128d620eba9da117fe92a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722055"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="924c2-102">IMetaDataEmit::GetTokenFromSig (Método)</span><span class="sxs-lookup"><span data-stu-id="924c2-102">IMetaDataEmit::GetTokenFromSig Method</span></span>

<span data-ttu-id="924c2-103">Obtiene un token para la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="924c2-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="924c2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="924c2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromSig (
    [in]  PCCOR_SIGNATURE pvSig,
    [in]  ULONG       cbSig,
    [out] mdSignature *pmsig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="924c2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="924c2-105">Parameters</span></span>  

 `pvSig`  
 <span data-ttu-id="924c2-106">de Firma que se va a conservar y almacenar.</span><span class="sxs-lookup"><span data-stu-id="924c2-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="924c2-107">de Recuento de bytes de `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="924c2-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="924c2-108">enuncia El `mdSignature` token asignado.</span><span class="sxs-lookup"><span data-stu-id="924c2-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="924c2-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="924c2-109">Requirements</span></span>  

 <span data-ttu-id="924c2-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="924c2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="924c2-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="924c2-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="924c2-112">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="924c2-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="924c2-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="924c2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="924c2-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="924c2-114">See also</span></span>

- [<span data-ttu-id="924c2-115">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="924c2-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="924c2-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="924c2-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
