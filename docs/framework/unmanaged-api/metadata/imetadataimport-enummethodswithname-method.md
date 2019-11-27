---
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
ms.openlocfilehash: b0817288040550b5f4c3c4ec063f6a7fdb004137
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450061"
---
# <a name="imetadataimportenummethodswithname-method"></a><span data-ttu-id="76a24-102">IMetaDataImport::EnumMethodsWithName (Método)</span><span class="sxs-lookup"><span data-stu-id="76a24-102">IMetaDataImport::EnumMethodsWithName Method</span></span>
<span data-ttu-id="76a24-103">Enumera los métodos que tienen el nombre especificado y que están definidos por el tipo al que hace referencia el token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="76a24-103">Enumerates methods that have the specified name and that are defined by the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76a24-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76a24-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="76a24-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="76a24-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="76a24-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="76a24-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="76a24-107">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="76a24-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="76a24-108">de Un token de TypeDef que representa el tipo cuyos métodos se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="76a24-108">[in] A TypeDef token representing the type whose methods to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="76a24-109">de Nombre que limita el ámbito de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="76a24-109">[in] The name that limits the scope of the enumeration.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="76a24-110">enuncia Matriz utilizada para almacenar los tokens de MethodDef.</span><span class="sxs-lookup"><span data-stu-id="76a24-110">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="76a24-111">[in] Tamaño máximo de la matriz `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="76a24-111">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="76a24-112">enuncia Número de tokens de MethodDef devueltos en `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="76a24-112">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76a24-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="76a24-113">Remarks</span></span>  
 <span data-ttu-id="76a24-114">Este método enumera los campos y métodos, pero no las propiedades o los eventos.</span><span class="sxs-lookup"><span data-stu-id="76a24-114">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="76a24-115">A diferencia de [IMetaDataImport:: enummethods (](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` descarta todos los tokens de método que no tienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="76a24-115">Unlike [IMetaDataImport::EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76a24-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="76a24-116">Return Value</span></span>  
  
|<span data-ttu-id="76a24-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="76a24-117">HRESULT</span></span>|<span data-ttu-id="76a24-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="76a24-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="76a24-119">`EnumMethodsWithName` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="76a24-119">`EnumMethodsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="76a24-120">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="76a24-120">There are no tokens to enumerate.</span></span> <span data-ttu-id="76a24-121">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="76a24-121">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="76a24-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76a24-122">Requirements</span></span>  
 <span data-ttu-id="76a24-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76a24-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76a24-124">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="76a24-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="76a24-125">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="76a24-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="76a24-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76a24-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76a24-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="76a24-127">See also</span></span>

- [<span data-ttu-id="76a24-128">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="76a24-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="76a24-129">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="76a24-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
