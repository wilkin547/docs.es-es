---
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
ms.openlocfilehash: 2e75b6322e40fe010e9e0a3412a99c0d3460afae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719377"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="fc701-102">IMetaDataEmit::DefineTypeDef (Método)</span><span class="sxs-lookup"><span data-stu-id="fc701-102">IMetaDataEmit::DefineTypeDef Method</span></span>

<span data-ttu-id="fc701-103">Crea una definición de tipo para un Common Language Runtime tipo y obtiene un símbolo (token) de metadatos para esa definición de tipo.</span><span class="sxs-lookup"><span data-stu-id="fc701-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc701-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc701-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeDef (
    [in]  LPCWSTR     szTypeDef,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc701-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fc701-105">Parameters</span></span>  

 `szTypeDef`  
 <span data-ttu-id="fc701-106">de Nombre del tipo en Unicode.</span><span class="sxs-lookup"><span data-stu-id="fc701-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="fc701-107">[in] `TypeDef` sus.</span><span class="sxs-lookup"><span data-stu-id="fc701-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="fc701-108">Se trata de una máscara de máscara de `CoreTypeAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="fc701-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="fc701-109">de Token de la clase base.</span><span class="sxs-lookup"><span data-stu-id="fc701-109">[in] The token of the base class.</span></span> <span data-ttu-id="fc701-110">Debe ser un `mdTypeDef` o un `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="fc701-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="fc701-111">de Una matriz de tokens que especifican las interfaces que esta clase o interfaz implementa.</span><span class="sxs-lookup"><span data-stu-id="fc701-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="fc701-112">enuncia El `mdTypeDef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="fc701-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc701-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fc701-113">Remarks</span></span>  

 <span data-ttu-id="fc701-114">Una marca en `dwTypeDefFlags` especifica si el tipo que se va a crear es un tipo de referencia del sistema de tipos comunes (clase o interfaz) o un tipo de valor del sistema de tipos comunes.</span><span class="sxs-lookup"><span data-stu-id="fc701-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="fc701-115">Dependiendo de los parámetros proporcionados, este método, como efecto secundario, también puede crear un `mdInterfaceImpl` registro para cada interfaz heredada o implementada por este tipo.</span><span class="sxs-lookup"><span data-stu-id="fc701-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="fc701-116">Sin embargo, este método no devuelve ninguno de estos `mdInterfaceImpl` tokens.</span><span class="sxs-lookup"><span data-stu-id="fc701-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="fc701-117">Si un cliente desea agregar o modificar un token más tarde `mdInterfaceImpl` , debe usar la `IMetaDataImport` interfaz para enumerarlos.</span><span class="sxs-lookup"><span data-stu-id="fc701-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="fc701-118">Si desea utilizar la semántica COM de la `[default]` interfaz, debe proporcionar la interfaz predeterminada como el primer elemento de `rtkImplements` ; un atributo personalizado establecido en la clase indicará que la clase tiene una interfaz predeterminada (que siempre se supone que es el primer `mdInterfaceImpl` token declarado para la clase).</span><span class="sxs-lookup"><span data-stu-id="fc701-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="fc701-119">Cada elemento de la `rtkImplements` matriz contiene un `mdTypeDef` `mdTypeRef` token o.</span><span class="sxs-lookup"><span data-stu-id="fc701-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="fc701-120">El último elemento de la matriz debe ser `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="fc701-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc701-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc701-121">Requirements</span></span>  

 <span data-ttu-id="fc701-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc701-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc701-123">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fc701-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fc701-124">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fc701-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc701-125">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc701-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc701-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fc701-126">See also</span></span>

- [<span data-ttu-id="fc701-127">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc701-127">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="fc701-128">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc701-128">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
