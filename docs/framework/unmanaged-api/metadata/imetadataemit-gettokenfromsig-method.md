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
ms.openlocfilehash: d02943f28435fc00aad8e319aa260a24cca5e307
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177587"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="7b22f-102">IMetaDataEmit::GetTokenFromSig (Método)</span><span class="sxs-lookup"><span data-stu-id="7b22f-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="7b22f-103">Obtiene un token para la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="7b22f-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b22f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b22f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromSig (
    [in]  PCCOR_SIGNATURE pvSig,
    [in]  ULONG       cbSig,
    [out] mdSignature *pmsig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b22f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b22f-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="7b22f-106">[en] La firma que se va a conservar y almacenar.</span><span class="sxs-lookup"><span data-stu-id="7b22f-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="7b22f-107">[en] El recuento de `pvSig`bytes en .</span><span class="sxs-lookup"><span data-stu-id="7b22f-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="7b22f-108">[fuera] El `mdSignature` token asignado.</span><span class="sxs-lookup"><span data-stu-id="7b22f-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b22f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b22f-109">Requirements</span></span>  
 <span data-ttu-id="7b22f-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b22f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b22f-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7b22f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7b22f-112">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7b22f-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7b22f-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b22f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b22f-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7b22f-114">See also</span></span>

- [<span data-ttu-id="7b22f-115">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b22f-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7b22f-116">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b22f-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
