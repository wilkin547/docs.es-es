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
ms.openlocfilehash: 4f1c3e823b35fcf7d5935eee111e042b2291d216
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175764"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="8bc36-102">IMetaDataEmit::DefineTypeDef (Método)</span><span class="sxs-lookup"><span data-stu-id="8bc36-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="8bc36-103">Crea una definición de tipo para un tipo de Common Language Runtime y obtiene un token de metadatos para esa definición de tipo.</span><span class="sxs-lookup"><span data-stu-id="8bc36-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bc36-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8bc36-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeDef (
    [in]  LPCWSTR     szTypeDef,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bc36-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8bc36-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="8bc36-106">[en] El nombre del tipo en Unicode.</span><span class="sxs-lookup"><span data-stu-id="8bc36-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="8bc36-107">[en] `TypeDef` atributos.</span><span class="sxs-lookup"><span data-stu-id="8bc36-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="8bc36-108">Esta es una `CoreTypeAttr` máscara de bits de valores.</span><span class="sxs-lookup"><span data-stu-id="8bc36-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="8bc36-109">[en] El token de la clase base.</span><span class="sxs-lookup"><span data-stu-id="8bc36-109">[in] The token of the base class.</span></span> <span data-ttu-id="8bc36-110">Debe ser un `mdTypeDef` token `mdTypeRef` o un token.</span><span class="sxs-lookup"><span data-stu-id="8bc36-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="8bc36-111">[en] Matriz de tokens que especifica las interfaces que implementa esta clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="8bc36-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="8bc36-112">[fuera] El `mdTypeDef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="8bc36-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bc36-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8bc36-113">Remarks</span></span>  
 <span data-ttu-id="8bc36-114">Un indicador `dwTypeDefFlags` en especifica si el tipo que se está creando es un tipo de referencia de sistema de tipo común (clase o interfaz) o un tipo de valor de sistema de tipo común.</span><span class="sxs-lookup"><span data-stu-id="8bc36-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="8bc36-115">Dependiendo de los parámetros proporcionados, este método, `mdInterfaceImpl` como efecto secundario, también puede crear un registro para cada interfaz heredada o implementada por este tipo.</span><span class="sxs-lookup"><span data-stu-id="8bc36-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="8bc36-116">Sin embargo, este método `mdInterfaceImpl` no devuelve ninguno de estos tokens.</span><span class="sxs-lookup"><span data-stu-id="8bc36-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="8bc36-117">Si un cliente desea agregar `mdInterfaceImpl` o modificar posteriormente `IMetaDataImport` un token, debe usar la interfaz para enumerarlos.</span><span class="sxs-lookup"><span data-stu-id="8bc36-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="8bc36-118">Si desea utilizar la semántica `[default]` COM de la interfaz, debe proporcionar `rtkImplements`la interfaz predeterminada como el primer elemento en ; un atributo personalizado establecido en la clase indicará que la clase tiene una `mdInterfaceImpl` interfaz predeterminada (que siempre se supone que es el primer token declarado para la clase).</span><span class="sxs-lookup"><span data-stu-id="8bc36-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="8bc36-119">Cada elemento `rtkImplements` de la `mdTypeDef` matriz `mdTypeRef` contiene un token o.</span><span class="sxs-lookup"><span data-stu-id="8bc36-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="8bc36-120">El último elemento de `mdTokenNil`la matriz debe ser .</span><span class="sxs-lookup"><span data-stu-id="8bc36-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bc36-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8bc36-121">Requirements</span></span>  
 <span data-ttu-id="8bc36-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bc36-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bc36-123">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8bc36-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8bc36-124">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8bc36-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8bc36-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bc36-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bc36-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8bc36-126">See also</span></span>

- [<span data-ttu-id="8bc36-127">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8bc36-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8bc36-128">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8bc36-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
