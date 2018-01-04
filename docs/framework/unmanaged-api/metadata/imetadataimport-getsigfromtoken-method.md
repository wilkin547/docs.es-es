---
title: "IMetaDataImport::GetSigFromToken (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetSigFromToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetSigFromToken
helpviewer_keywords:
- IMetaDataImport::GetSigFromToken method [.NET Framework metadata]
- GetSigFromToken method [.NET Framework metadata]
ms.assetid: ab894dc4-f7b6-4afc-bfcb-582a4b7e53a2
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6328e112aa948ecc2f0f5d816c4fd77673e06244
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="e6038-102">IMetaDataImport::GetSigFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="e6038-102">IMetaDataImport::GetSigFromToken Method</span></span>
<span data-ttu-id="e6038-103">Obtiene la firma de metadatos binaria asociada al token especificado.</span><span class="sxs-lookup"><span data-stu-id="e6038-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6038-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6038-104">Syntax</span></span>  
  
```  
HRESULT GetSigFromToken (   
   [in]   mdSignature        mdSig,   
   [out]  PCCOR_SIGNATURE    *ppvSig,   
   [out]  ULONG              *pcbSig   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e6038-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e6038-105">Parameters</span></span>  
 `mdSig`  
 <span data-ttu-id="e6038-106">[in] El token para devolver la firma de metadatos binaria.</span><span class="sxs-lookup"><span data-stu-id="e6038-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="e6038-107">[out] Un puntero a la firma de metadatos devuelta.</span><span class="sxs-lookup"><span data-stu-id="e6038-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="e6038-108">[out] El tamaño en bytes de la firma de metadatos binaria.</span><span class="sxs-lookup"><span data-stu-id="e6038-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6038-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6038-109">Requirements</span></span>  
 <span data-ttu-id="e6038-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6038-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6038-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e6038-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e6038-112">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e6038-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e6038-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6038-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6038-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6038-114">See Also</span></span>  
 [<span data-ttu-id="e6038-115">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6038-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="e6038-116">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6038-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
