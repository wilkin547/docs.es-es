---
title: IMetaDataEmit::GetTokenFromTypeSpec (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromTypeSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromTypeSpec
helpviewer_keywords:
- GetTokenFromTypeSpec method [.NET Framework metadata]
- IMetaDataEmit::GetTokenFromTypeSpec method [.NET Framework metadata]
ms.assetid: 7de6447a-a751-49d8-87e2-951cee77b536
topic_type:
- apiref
ms.openlocfilehash: 6e73160fb1927560ad381dbb85d03796296ba9a4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434289"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="e9930-102">IMetaDataEmit::GetTokenFromTypeSpec (Método)</span><span class="sxs-lookup"><span data-stu-id="e9930-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="e9930-103">Obtiene un símbolo (token) de metadatos para el tipo con la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="e9930-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9930-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9930-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromTypeSpec (   
    [in]  PCCOR_SIGNATURE       pvSig,   
    [in]  ULONG                 cbSig,   
    [out] mdTypeSpec            *ptypespec   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9930-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9930-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="e9930-106">de Firma que se va a definir.</span><span class="sxs-lookup"><span data-stu-id="e9930-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="e9930-107">de Recuento de bytes de `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="e9930-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="e9930-108">enuncia El token de `mdTypeSpec` asignado.</span><span class="sxs-lookup"><span data-stu-id="e9930-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9930-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9930-109">Requirements</span></span>  
 <span data-ttu-id="e9930-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9930-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9930-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e9930-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9930-112">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e9930-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9930-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9930-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9930-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9930-114">See also</span></span>

- [<span data-ttu-id="e9930-115">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9930-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e9930-116">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9930-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
