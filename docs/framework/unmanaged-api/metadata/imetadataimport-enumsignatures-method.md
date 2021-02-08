---
description: 'Más información sobre: IMetaDataImport:: Enumsignatures ((método)'
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
ms.openlocfilehash: ed41dd42151791e3d27950f30b10d91217ad7e7a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771631"
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="cfbc6-103">IMetaDataImport::EnumSignatures (Método)</span><span class="sxs-lookup"><span data-stu-id="cfbc6-103">IMetaDataImport::EnumSignatures Method</span></span>

<span data-ttu-id="cfbc6-104">Enumera los tokens de firma que representan las firmas independientes en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="cfbc6-104">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfbc6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cfbc6-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfbc6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cfbc6-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="cfbc6-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="cfbc6-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="cfbc6-108">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="cfbc6-108">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="cfbc6-109">enuncia Matriz utilizada para almacenar los tokens de firma.</span><span class="sxs-lookup"><span data-stu-id="cfbc6-109">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="cfbc6-110">[in] Tamaño máximo de la matriz `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="cfbc6-110">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="cfbc6-111">enuncia El número de tokens de firma devueltos en `rSignatures` .</span><span class="sxs-lookup"><span data-stu-id="cfbc6-111">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cfbc6-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cfbc6-112">Return Value</span></span>  
  
|<span data-ttu-id="cfbc6-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cfbc6-113">HRESULT</span></span>|<span data-ttu-id="cfbc6-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="cfbc6-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="cfbc6-115">`EnumSignatures` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="cfbc6-115">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="cfbc6-116">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="cfbc6-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="cfbc6-117">En ese caso, `pcSignatures` es cero.</span><span class="sxs-lookup"><span data-stu-id="cfbc6-117">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfbc6-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cfbc6-118">Remarks</span></span>  

 <span data-ttu-id="cfbc6-119">El método [IMetaDataEmit:: GetTokenFromSig (](imetadataemit-gettokenfromsig-method.md) crea los tokens de firma.</span><span class="sxs-lookup"><span data-stu-id="cfbc6-119">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfbc6-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cfbc6-120">Requirements</span></span>  

 <span data-ttu-id="cfbc6-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfbc6-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfbc6-122">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cfbc6-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cfbc6-123">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cfbc6-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cfbc6-124">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfbc6-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfbc6-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfbc6-125">See also</span></span>

- [<span data-ttu-id="cfbc6-126">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cfbc6-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="cfbc6-127">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cfbc6-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
