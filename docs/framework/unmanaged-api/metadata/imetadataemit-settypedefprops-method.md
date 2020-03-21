---
title: IMetaDataEmit::SetTypeDefProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
ms.openlocfilehash: e59e7695246b2c83171e77352e16464258516f8d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177462"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="506c6-102">IMetaDataEmit::SetTypeDefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="506c6-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="506c6-103">Establece las características de un tipo definido por una llamada anterior a [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="506c6-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="506c6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="506c6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="506c6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="506c6-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="506c6-106">[en] Un `mdTypeDef` token obtenido de la llamada original a [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="506c6-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="506c6-107">[en] `TypeDef` atributos.</span><span class="sxs-lookup"><span data-stu-id="506c6-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="506c6-108">Esta es una `CorTypeAttr` máscara de bits de valores.</span><span class="sxs-lookup"><span data-stu-id="506c6-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="506c6-109">[en] El `mdToken` de la clase base.</span><span class="sxs-lookup"><span data-stu-id="506c6-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="506c6-110">Obtenido de una llamada anterior a [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)o `null`.</span><span class="sxs-lookup"><span data-stu-id="506c6-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="506c6-111">[en] Matriz de tokens para las interfaces que implementa este tipo.</span><span class="sxs-lookup"><span data-stu-id="506c6-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="506c6-112">Estos `mdTypeRef` tokens se obtienen mediante [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="506c6-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="506c6-113">El último elemento de la `mdTokenNil`matriz debe ser .</span><span class="sxs-lookup"><span data-stu-id="506c6-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="506c6-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="506c6-114">Requirements</span></span>  
 <span data-ttu-id="506c6-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="506c6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="506c6-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="506c6-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="506c6-117">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="506c6-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="506c6-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="506c6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="506c6-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="506c6-119">See also</span></span>

- [<span data-ttu-id="506c6-120">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="506c6-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="506c6-121">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="506c6-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
