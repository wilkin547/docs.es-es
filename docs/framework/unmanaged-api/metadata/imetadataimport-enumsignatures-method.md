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
ms.openlocfilehash: 652ebf1be6a58e08da27aaed5b2e84a8f2aee98a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503775"
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="21ff5-102">IMetaDataImport::EnumSignatures (Método)</span><span class="sxs-lookup"><span data-stu-id="21ff5-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="21ff5-103">Enumera los tokens de firma que representan las firmas independientes en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="21ff5-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21ff5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21ff5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21ff5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="21ff5-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="21ff5-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="21ff5-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="21ff5-107">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="21ff5-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="21ff5-108">enuncia Matriz utilizada para almacenar los tokens de firma.</span><span class="sxs-lookup"><span data-stu-id="21ff5-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="21ff5-109">[in] Tamaño máximo de la matriz `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="21ff5-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="21ff5-110">enuncia El número de tokens de firma devueltos en `rSignatures` .</span><span class="sxs-lookup"><span data-stu-id="21ff5-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21ff5-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="21ff5-111">Return Value</span></span>  
  
|<span data-ttu-id="21ff5-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="21ff5-112">HRESULT</span></span>|<span data-ttu-id="21ff5-113">Description</span><span class="sxs-lookup"><span data-stu-id="21ff5-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="21ff5-114">`EnumSignatures`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="21ff5-114">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="21ff5-115">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="21ff5-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="21ff5-116">En ese caso, `pcSignatures` es cero.</span><span class="sxs-lookup"><span data-stu-id="21ff5-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21ff5-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="21ff5-117">Remarks</span></span>  
 <span data-ttu-id="21ff5-118">El método [IMetaDataEmit:: GetTokenFromSig (](imetadataemit-gettokenfromsig-method.md) crea los tokens de firma.</span><span class="sxs-lookup"><span data-stu-id="21ff5-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21ff5-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="21ff5-119">Requirements</span></span>  
 <span data-ttu-id="21ff5-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21ff5-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21ff5-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="21ff5-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="21ff5-122">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="21ff5-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="21ff5-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21ff5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21ff5-124">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="21ff5-124">See also</span></span>

- [<span data-ttu-id="21ff5-125">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="21ff5-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="21ff5-126">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="21ff5-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
