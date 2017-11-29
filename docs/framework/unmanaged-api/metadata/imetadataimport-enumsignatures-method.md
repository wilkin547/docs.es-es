---
title: "IMetaDataImport::EnumSignatures (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumSignatures
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumSignatures
helpviewer_keywords:
- EnumSignatures method [.NET Framework metadata]
- IMetaDataImport::EnumSignatures method [.NET Framework metadata]
ms.assetid: d0d65060-6f90-42a2-95cf-6ffb04352996
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 25fb32b0780dc91157d39ece37f93d7abd582cf7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="52107-102">IMetaDataImport::EnumSignatures (Método)</span><span class="sxs-lookup"><span data-stu-id="52107-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="52107-103">Enumera los tokens de firma que representan las firmas independientes en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="52107-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52107-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52107-104">Syntax</span></span>  
  
```  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52107-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52107-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="52107-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="52107-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="52107-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="52107-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="52107-108">[out] Matriz utilizada para almacenar los tokens de firma.</span><span class="sxs-lookup"><span data-stu-id="52107-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="52107-109">[in] Tamaño máximo de la matriz `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="52107-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="52107-110">[out] El número de tokens de firma que se devuelven en `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="52107-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52107-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="52107-111">Return Value</span></span>  
  
|<span data-ttu-id="52107-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="52107-112">HRESULT</span></span>|<span data-ttu-id="52107-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="52107-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="52107-114">`EnumSignatures`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="52107-114">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="52107-115">No hay ningún tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="52107-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="52107-116">En ese caso, `pcSignatures` es cero.</span><span class="sxs-lookup"><span data-stu-id="52107-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52107-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="52107-117">Remarks</span></span>  
 <span data-ttu-id="52107-118">Los tokens de firma se crean mediante el [GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="52107-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52107-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52107-119">Requirements</span></span>  
 <span data-ttu-id="52107-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52107-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52107-121">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="52107-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="52107-122">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="52107-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="52107-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52107-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52107-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="52107-124">See Also</span></span>  
 [<span data-ttu-id="52107-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="52107-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="52107-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="52107-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
