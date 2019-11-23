---
title: IMetaDataImport::GetSigFromToken (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetSigFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetSigFromToken
helpviewer_keywords:
- IMetaDataImport::GetSigFromToken method [.NET Framework metadata]
- GetSigFromToken method [.NET Framework metadata]
ms.assetid: ab894dc4-f7b6-4afc-bfcb-582a4b7e53a2
topic_type:
- apiref
ms.openlocfilehash: 205f48fb417365565695c72095187d349127e536
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436850"
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="9edc3-102">IMetaDataImport::GetSigFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="9edc3-102">IMetaDataImport::GetSigFromToken Method</span></span>
<span data-ttu-id="9edc3-103">Obtiene la firma de metadatos binaria asociada al token especificado.</span><span class="sxs-lookup"><span data-stu-id="9edc3-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9edc3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9edc3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSigFromToken (   
   [in]   mdSignature        mdSig,   
   [out]  PCCOR_SIGNATURE    *ppvSig,   
   [out]  ULONG              *pcbSig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9edc3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9edc3-105">Parameters</span></span>  
 `mdSig`  
 <span data-ttu-id="9edc3-106">[in] The token to return the binary metadata signature for.</span><span class="sxs-lookup"><span data-stu-id="9edc3-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="9edc3-107">[out] A pointer to the returned metadata signature.</span><span class="sxs-lookup"><span data-stu-id="9edc3-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="9edc3-108">[out] The size in bytes of the binary metadata signature.</span><span class="sxs-lookup"><span data-stu-id="9edc3-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9edc3-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9edc3-109">Requirements</span></span>  
 <span data-ttu-id="9edc3-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9edc3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9edc3-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9edc3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9edc3-112">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9edc3-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9edc3-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9edc3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9edc3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9edc3-114">See also</span></span>

- [<span data-ttu-id="9edc3-115">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9edc3-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9edc3-116">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9edc3-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
