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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b25eb71d78797b5f764cfe4de7abd45f0143fde4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717641"
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="b1b50-102">IMetaDataImport::GetSigFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="b1b50-102">IMetaDataImport::GetSigFromToken Method</span></span>
<span data-ttu-id="b1b50-103">Obtiene la firma de metadatos binaria asociada al token especificado.</span><span class="sxs-lookup"><span data-stu-id="b1b50-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1b50-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1b50-104">Syntax</span></span>  
  
```  
HRESULT GetSigFromToken (   
   [in]   mdSignature        mdSig,   
   [out]  PCCOR_SIGNATURE    *ppvSig,   
   [out]  ULONG              *pcbSig   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b1b50-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b1b50-105">Parameters</span></span>  
 `mdSig`  
 <span data-ttu-id="b1b50-106">[in] El token para devolver la firma de metadatos binaria.</span><span class="sxs-lookup"><span data-stu-id="b1b50-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="b1b50-107">[out] Un puntero a la firma de metadatos devuelta.</span><span class="sxs-lookup"><span data-stu-id="b1b50-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="b1b50-108">[out] El tamaño en bytes de la firma de metadatos binaria.</span><span class="sxs-lookup"><span data-stu-id="b1b50-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1b50-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b1b50-109">Requirements</span></span>  
 <span data-ttu-id="b1b50-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1b50-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1b50-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="b1b50-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b1b50-112">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b1b50-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b1b50-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1b50-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1b50-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1b50-114">See also</span></span>
- [<span data-ttu-id="b1b50-115">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b1b50-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b1b50-116">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b1b50-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
