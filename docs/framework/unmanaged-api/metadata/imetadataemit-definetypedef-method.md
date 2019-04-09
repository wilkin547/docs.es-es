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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9b6f5881f289bed258191baf4f43264ea6ba35db
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141809"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="300f5-102">IMetaDataEmit::DefineTypeDef (Método)</span><span class="sxs-lookup"><span data-stu-id="300f5-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="300f5-103">Crea una definición de tipo para un tipo de common language runtime y obtiene un token de metadatos para esa definición de tipo.</span><span class="sxs-lookup"><span data-stu-id="300f5-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="300f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="300f5-104">Syntax</span></span>  
  
```  
HRESULT DefineTypeDef (   
    [in]  LPCWSTR     szTypeDef,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="300f5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="300f5-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="300f5-106">[in] El nombre del tipo en formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="300f5-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="300f5-107">[in] `TypeDef` atributos.</span><span class="sxs-lookup"><span data-stu-id="300f5-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="300f5-108">Se trata de una máscara de bits de `CoreTypeAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="300f5-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="300f5-109">[in] El token de la clase base.</span><span class="sxs-lookup"><span data-stu-id="300f5-109">[in] The token of the base class.</span></span> <span data-ttu-id="300f5-110">Debe ser un `mdTypeDef` o un `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="300f5-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="300f5-111">[in] Una matriz de los tokens de especificación de las interfaces que implementa esta clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="300f5-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="300f5-112">[out] El `mdTypeDef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="300f5-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="300f5-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="300f5-113">Remarks</span></span>  
 <span data-ttu-id="300f5-114">Una marca en `dwTypeDefFlags` especifica si el tipo que se va a crear es un sistema tipo común tipo de referencia (clase o interfaz) o un tipo de valor de sistema de tipo común.</span><span class="sxs-lookup"><span data-stu-id="300f5-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="300f5-115">Dependiendo de los parámetros proporcionados, este método, como un efecto secundario, también puede crear una `mdInterfaceImpl` registros para cada interfaz que es heredado o implementada por este tipo.</span><span class="sxs-lookup"><span data-stu-id="300f5-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="300f5-116">Sin embargo, este método no devuelve cualquiera de estos `mdInterfaceImpl` tokens.</span><span class="sxs-lookup"><span data-stu-id="300f5-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="300f5-117">Si un cliente desea agregar más adelante o modificar un `mdInterfaceImpl` token, debe usar el `IMetaDataImport` interfaz para enumerarlas.</span><span class="sxs-lookup"><span data-stu-id="300f5-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="300f5-118">Si desea usar la semántica de COM de la `[default]` interfaz, debe proporcionar la interfaz predeterminada como el primer elemento en `rtkImplements`; un atributo personalizado establecido en la clase indicará que la clase tiene una interfaz predeterminada (que siempre se supone que es el en primer lugar `mdInterfaceImpl` token declarado para la clase).</span><span class="sxs-lookup"><span data-stu-id="300f5-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="300f5-119">Cada elemento de la `rtkImplements` matriz contiene un `mdTypeDef` o `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="300f5-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="300f5-120">El último elemento de la matriz debe ser `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="300f5-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="300f5-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="300f5-121">Requirements</span></span>  
 <span data-ttu-id="300f5-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="300f5-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="300f5-123">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="300f5-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="300f5-124">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="300f5-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="300f5-125">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="300f5-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="300f5-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="300f5-126">See also</span></span>

- [<span data-ttu-id="300f5-127">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="300f5-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="300f5-128">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="300f5-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
