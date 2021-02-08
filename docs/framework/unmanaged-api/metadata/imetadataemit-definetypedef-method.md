---
description: 'Más información acerca de: IMetaDataEmit::D método efineTypeDef'
title: IMetaDataEmit::DefineTypeDef (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
ms.openlocfilehash: ca0c74b8c067771e9f45a8c00639d75c9ad08de1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784046"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="59e0c-103">IMetaDataEmit::DefineTypeDef (Método)</span><span class="sxs-lookup"><span data-stu-id="59e0c-103">IMetaDataEmit::DefineTypeDef Method</span></span>

<span data-ttu-id="59e0c-104">Crea una definición de tipo para un Common Language Runtime tipo y obtiene un símbolo (token) de metadatos para esa definición de tipo.</span><span class="sxs-lookup"><span data-stu-id="59e0c-104">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59e0c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59e0c-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeDef (
    [in]  LPCWSTR     szTypeDef,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59e0c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="59e0c-106">Parameters</span></span>  

 `szTypeDef`  
 <span data-ttu-id="59e0c-107">de Nombre del tipo en Unicode.</span><span class="sxs-lookup"><span data-stu-id="59e0c-107">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="59e0c-108">[in] `TypeDef` sus.</span><span class="sxs-lookup"><span data-stu-id="59e0c-108">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="59e0c-109">Se trata de una máscara de máscara de `CoreTypeAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="59e0c-109">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="59e0c-110">de Token de la clase base.</span><span class="sxs-lookup"><span data-stu-id="59e0c-110">[in] The token of the base class.</span></span> <span data-ttu-id="59e0c-111">Debe ser un `mdTypeDef` o un `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="59e0c-111">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="59e0c-112">de Una matriz de tokens que especifican las interfaces que esta clase o interfaz implementa.</span><span class="sxs-lookup"><span data-stu-id="59e0c-112">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="59e0c-113">enuncia El `mdTypeDef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="59e0c-113">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59e0c-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="59e0c-114">Remarks</span></span>  

 <span data-ttu-id="59e0c-115">Una marca en `dwTypeDefFlags` especifica si el tipo que se va a crear es un tipo de referencia del sistema de tipos comunes (clase o interfaz) o un tipo de valor del sistema de tipos comunes.</span><span class="sxs-lookup"><span data-stu-id="59e0c-115">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="59e0c-116">Dependiendo de los parámetros proporcionados, este método, como efecto secundario, también puede crear un `mdInterfaceImpl` registro para cada interfaz heredada o implementada por este tipo.</span><span class="sxs-lookup"><span data-stu-id="59e0c-116">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="59e0c-117">Sin embargo, este método no devuelve ninguno de estos `mdInterfaceImpl` tokens.</span><span class="sxs-lookup"><span data-stu-id="59e0c-117">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="59e0c-118">Si un cliente desea agregar o modificar un token más tarde `mdInterfaceImpl` , debe usar la `IMetaDataImport` interfaz para enumerarlos.</span><span class="sxs-lookup"><span data-stu-id="59e0c-118">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="59e0c-119">Si desea utilizar la semántica COM de la `[default]` interfaz, debe proporcionar la interfaz predeterminada como el primer elemento de `rtkImplements` ; un atributo personalizado establecido en la clase indicará que la clase tiene una interfaz predeterminada (que siempre se supone que es el primer `mdInterfaceImpl` token declarado para la clase).</span><span class="sxs-lookup"><span data-stu-id="59e0c-119">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="59e0c-120">Cada elemento de la `rtkImplements` matriz contiene un `mdTypeDef` `mdTypeRef` token o.</span><span class="sxs-lookup"><span data-stu-id="59e0c-120">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="59e0c-121">El último elemento de la matriz debe ser `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="59e0c-121">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59e0c-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59e0c-122">Requirements</span></span>  

 <span data-ttu-id="59e0c-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59e0c-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59e0c-124">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="59e0c-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="59e0c-125">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="59e0c-125">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="59e0c-126">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59e0c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59e0c-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="59e0c-127">See also</span></span>

- [<span data-ttu-id="59e0c-128">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="59e0c-128">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="59e0c-129">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="59e0c-129">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
