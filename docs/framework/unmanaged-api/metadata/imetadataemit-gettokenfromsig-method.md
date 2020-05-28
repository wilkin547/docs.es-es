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
ms.openlocfilehash: 740dad54bc3a79ff546176abdc35487d89ed8f44
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009254"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="f3420-102">IMetaDataEmit::GetTokenFromSig (Método)</span><span class="sxs-lookup"><span data-stu-id="f3420-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="f3420-103">Obtiene un token para la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="f3420-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3420-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3420-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromSig (
    [in]  PCCOR_SIGNATURE pvSig,
    [in]  ULONG       cbSig,
    [out] mdSignature *pmsig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3420-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f3420-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="f3420-106">de Firma que se va a conservar y almacenar.</span><span class="sxs-lookup"><span data-stu-id="f3420-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="f3420-107">de Recuento de bytes de `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="f3420-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="f3420-108">enuncia El `mdSignature` token asignado.</span><span class="sxs-lookup"><span data-stu-id="f3420-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3420-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3420-109">Requirements</span></span>  
 <span data-ttu-id="f3420-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3420-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3420-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f3420-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f3420-112">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f3420-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3420-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3420-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3420-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f3420-114">See also</span></span>

- [<span data-ttu-id="f3420-115">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3420-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="f3420-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3420-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
