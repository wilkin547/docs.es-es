---
description: 'Más información acerca de: IMetaDataEmit::D método efineImportType'
title: IMetaDataEmit::DefineImportType (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type:
- apiref
ms.openlocfilehash: 7afe0fe400e4eb6e177a06e00b2d69202820804c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753437"
---
# <a name="imetadataemitdefineimporttype-method"></a><span data-ttu-id="c65e4-103">IMetaDataEmit::DefineImportType (Método)</span><span class="sxs-lookup"><span data-stu-id="c65e4-103">IMetaDataEmit::DefineImportType Method</span></span>

<span data-ttu-id="c65e4-104">Crea una referencia al tipo especificado que se define fuera del ámbito actual y define un token para esa referencia.</span><span class="sxs-lookup"><span data-stu-id="c65e4-104">Creates a reference to the specified type that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c65e4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c65e4-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineImportType (
    [in]  IMetaDataAssemblyImport  *pAssemImport,
    [in]  const void               *pbHashValue,
    [in]  ULONG                    cbHashValue,
    [in]  IMetaDataImport          *pImport,
    [in]  mdTypeDef                tdImport,
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,
    [out] mdTypeRef                *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c65e4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c65e4-106">Parameters</span></span>  

 `pAssemImport`  
 <span data-ttu-id="c65e4-107">de Una interfaz [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) que representa el ensamblado desde el que se importa el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="c65e4-107">[in] An [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) interface that represents the assembly from which the target type is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="c65e4-108">de Una matriz que contiene el hash para el ensamblado especificado por `pAssemImport` .</span><span class="sxs-lookup"><span data-stu-id="c65e4-108">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="c65e4-109">[in] Número de bytes en la matriz `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="c65e4-109">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="c65e4-110">de Interfaz [IMetaDataImport](imetadataimport-interface.md) que representa el ámbito de metadatos desde el que se importa el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="c65e4-110">[in] An [IMetaDataImport](imetadataimport-interface.md) interface that represents the metadata scope from which the target type is imported.</span></span>  
  
 `tdImport`  
 <span data-ttu-id="c65e4-111">de `mdTypeDef` Token que especifica el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="c65e4-111">[in] An `mdTypeDef` token that specifies the target type.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="c65e4-112">de Una interfaz [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) que representa el ensamblado en el que se importa el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="c65e4-112">[in] An [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) interface that represents the assembly into which the target type is imported.</span></span>  
  
 `ptr`  
 <span data-ttu-id="c65e4-113">enuncia El `mdTypeRef` token que se define en el ámbito actual para la referencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="c65e4-113">[out] The `mdTypeRef` token that is defined in the current scope for the type reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c65e4-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c65e4-114">Remarks</span></span>  

 <span data-ttu-id="c65e4-115">Antes de llamar al método [IMetaDataEmit::D efineimportmember](imetadataemit-defineimportmember-method.md) , puede utilizar el `DefineImportType` método para crear una referencia de tipo, en el ámbito actual, para la clase primaria o la interfaz primaria del miembro.</span><span class="sxs-lookup"><span data-stu-id="c65e4-115">Prior to calling the [IMetaDataEmit::DefineImportMember](imetadataemit-defineimportmember-method.md) method, you can use the `DefineImportType` method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c65e4-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c65e4-116">Requirements</span></span>  

 <span data-ttu-id="c65e4-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c65e4-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c65e4-118">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c65e4-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c65e4-119">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c65e4-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c65e4-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c65e4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c65e4-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c65e4-121">See also</span></span>

- [<span data-ttu-id="c65e4-122">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c65e4-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="c65e4-123">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c65e4-123">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
