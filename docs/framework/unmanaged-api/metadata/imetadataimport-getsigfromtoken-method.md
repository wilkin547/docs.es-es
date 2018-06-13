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
ms.openlocfilehash: f40fb2e94eac13211cf8ccf179904071a23f59ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447232"
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="aae1b-102">IMetaDataImport::GetSigFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="aae1b-102">IMetaDataImport::GetSigFromToken Method</span></span>
<span data-ttu-id="aae1b-103">Obtiene la firma de metadatos binaria asociada al token especificado.</span><span class="sxs-lookup"><span data-stu-id="aae1b-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aae1b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aae1b-104">Syntax</span></span>  
  
```  
HRESULT GetSigFromToken (   
   [in]   mdSignature        mdSig,   
   [out]  PCCOR_SIGNATURE    *ppvSig,   
   [out]  ULONG              *pcbSig   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aae1b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aae1b-105">Parameters</span></span>  
 `mdSig`  
 <span data-ttu-id="aae1b-106">[in] El token para devolver la firma de metadatos binaria.</span><span class="sxs-lookup"><span data-stu-id="aae1b-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="aae1b-107">[out] Un puntero a la firma de metadatos devuelta.</span><span class="sxs-lookup"><span data-stu-id="aae1b-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="aae1b-108">[out] El tamaño en bytes de la firma de metadatos binaria.</span><span class="sxs-lookup"><span data-stu-id="aae1b-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aae1b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aae1b-109">Requirements</span></span>  
 <span data-ttu-id="aae1b-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aae1b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aae1b-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="aae1b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aae1b-112">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aae1b-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aae1b-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aae1b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aae1b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="aae1b-114">See Also</span></span>  
 [<span data-ttu-id="aae1b-115">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aae1b-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="aae1b-116">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aae1b-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
