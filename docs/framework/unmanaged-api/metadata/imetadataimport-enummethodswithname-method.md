---
description: 'Más información sobre: IMetaDataImport:: Enummethodswithname ((método)'
title: IMetaDataImport::EnumMethodsWithName (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type:
- apiref
ms.openlocfilehash: b77fc15bd7752b5b6b2b95d66a6bf04518616884
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745611"
---
# <a name="imetadataimportenummethodswithname-method"></a><span data-ttu-id="f4dde-103">IMetaDataImport::EnumMethodsWithName (Método)</span><span class="sxs-lookup"><span data-stu-id="f4dde-103">IMetaDataImport::EnumMethodsWithName Method</span></span>

<span data-ttu-id="f4dde-104">Enumera los métodos que tienen el nombre especificado y que están definidos por el tipo al que hace referencia el token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="f4dde-104">Enumerates methods that have the specified name and that are defined by the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4dde-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4dde-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4dde-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4dde-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="f4dde-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="f4dde-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="f4dde-108">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="f4dde-108">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="f4dde-109">de Un token de TypeDef que representa el tipo cuyos métodos se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="f4dde-109">[in] A TypeDef token representing the type whose methods to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="f4dde-110">de Nombre que limita el ámbito de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="f4dde-110">[in] The name that limits the scope of the enumeration.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="f4dde-111">enuncia Matriz utilizada para almacenar los tokens de MethodDef.</span><span class="sxs-lookup"><span data-stu-id="f4dde-111">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f4dde-112">[in] Tamaño máximo de la matriz `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="f4dde-112">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="f4dde-113">enuncia Número de tokens de MethodDef devueltos en `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="f4dde-113">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4dde-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f4dde-114">Remarks</span></span>  

 <span data-ttu-id="f4dde-115">Este método enumera los campos y métodos, pero no las propiedades o los eventos.</span><span class="sxs-lookup"><span data-stu-id="f4dde-115">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="f4dde-116">A diferencia de [IMetaDataImport:: enummethods (](imetadataimport-enummethods-method.md), `EnumMethodsWithName` descarta todos los tokens de método que no tienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="f4dde-116">Unlike [IMetaDataImport::EnumMethods](imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4dde-117">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f4dde-117">Return Value</span></span>  
  
|<span data-ttu-id="f4dde-118">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f4dde-118">HRESULT</span></span>|<span data-ttu-id="f4dde-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4dde-119">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f4dde-120">`EnumMethodsWithName` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f4dde-120">`EnumMethodsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f4dde-121">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="f4dde-121">There are no tokens to enumerate.</span></span> <span data-ttu-id="f4dde-122">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="f4dde-122">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f4dde-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4dde-123">Requirements</span></span>  

 <span data-ttu-id="f4dde-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4dde-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4dde-125">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f4dde-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f4dde-126">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f4dde-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f4dde-127">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4dde-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4dde-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4dde-128">See also</span></span>

- [<span data-ttu-id="f4dde-129">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4dde-129">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="f4dde-130">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4dde-130">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
