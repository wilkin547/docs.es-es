---
title: IMetaDataImport::EnumSignatures (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumSignatures
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumSignatures
helpviewer_keywords:
- EnumSignatures method [.NET Framework metadata]
- IMetaDataImport::EnumSignatures method [.NET Framework metadata]
ms.assetid: d0d65060-6f90-42a2-95cf-6ffb04352996
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 58fa2a6d34f1f3627378c1355a1a292b665899ee
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756408"
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="dfe38-102">IMetaDataImport::EnumSignatures (Método)</span><span class="sxs-lookup"><span data-stu-id="dfe38-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="dfe38-103">Enumera los tokens de firma que representan las firmas independientes en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="dfe38-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfe38-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dfe38-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfe38-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dfe38-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="dfe38-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="dfe38-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="dfe38-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="dfe38-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="dfe38-108">[out] Matriz utilizada para almacenar los tokens de firma.</span><span class="sxs-lookup"><span data-stu-id="dfe38-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="dfe38-109">[in] Tamaño máximo de la matriz `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="dfe38-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="dfe38-110">[out] El número de tokens de firma que se devuelven en `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="dfe38-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dfe38-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dfe38-111">Return Value</span></span>  
  
|<span data-ttu-id="dfe38-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dfe38-112">HRESULT</span></span>|<span data-ttu-id="dfe38-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="dfe38-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="dfe38-114">`EnumSignatures` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="dfe38-114">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="dfe38-115">No hay ningún token para enumerar.</span><span class="sxs-lookup"><span data-stu-id="dfe38-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="dfe38-116">En ese caso, `pcSignatures` es cero.</span><span class="sxs-lookup"><span data-stu-id="dfe38-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfe38-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dfe38-117">Remarks</span></span>  
 <span data-ttu-id="dfe38-118">Los tokens de firma se crean mediante el [GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="dfe38-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfe38-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dfe38-119">Requirements</span></span>  
 <span data-ttu-id="dfe38-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfe38-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfe38-121">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="dfe38-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dfe38-122">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dfe38-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dfe38-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfe38-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfe38-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfe38-124">See also</span></span>

- [<span data-ttu-id="dfe38-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dfe38-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="dfe38-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dfe38-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
