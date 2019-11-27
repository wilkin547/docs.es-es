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
ms.openlocfilehash: 9dbbdcc9d0fb9f0a8d2a64edfa4a0ad92570933c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450007"
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="58e4d-102">IMetaDataImport::EnumSignatures (Método)</span><span class="sxs-lookup"><span data-stu-id="58e4d-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="58e4d-103">Enumera los tokens de firma que representan las firmas independientes en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="58e4d-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58e4d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58e4d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58e4d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="58e4d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="58e4d-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="58e4d-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="58e4d-107">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="58e4d-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="58e4d-108">enuncia Matriz utilizada para almacenar los tokens de firma.</span><span class="sxs-lookup"><span data-stu-id="58e4d-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="58e4d-109">[in] Tamaño máximo de la matriz `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="58e4d-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="58e4d-110">enuncia El número de tokens de firma devueltos en `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="58e4d-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58e4d-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="58e4d-111">Return Value</span></span>  
  
|<span data-ttu-id="58e4d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="58e4d-112">HRESULT</span></span>|<span data-ttu-id="58e4d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="58e4d-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="58e4d-114">`EnumSignatures` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="58e4d-114">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="58e4d-115">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="58e4d-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="58e4d-116">En ese caso, `pcSignatures` es cero.</span><span class="sxs-lookup"><span data-stu-id="58e4d-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58e4d-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="58e4d-117">Remarks</span></span>  
 <span data-ttu-id="58e4d-118">El método [IMetaDataEmit:: GetTokenFromSig (](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) crea los tokens de firma.</span><span class="sxs-lookup"><span data-stu-id="58e4d-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58e4d-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58e4d-119">Requirements</span></span>  
 <span data-ttu-id="58e4d-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58e4d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58e4d-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="58e4d-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="58e4d-122">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="58e4d-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="58e4d-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58e4d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58e4d-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="58e4d-124">See also</span></span>

- [<span data-ttu-id="58e4d-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="58e4d-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="58e4d-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="58e4d-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
