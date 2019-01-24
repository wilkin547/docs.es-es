---
title: IMetaDataImport::ResolveTypeRef (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResolveTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3c69c67c5c9d996bd746d82ea86caf4a396c0b10
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625242"
---
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="b8121-102">IMetaDataImport::ResolveTypeRef (Método)</span><span class="sxs-lookup"><span data-stu-id="b8121-102">IMetaDataImport::ResolveTypeRef Method</span></span>
<span data-ttu-id="b8121-103">Resuelve un <xref:System.Type> referencia representado por el símbolo (token) de TypeRef especificado.</span><span class="sxs-lookup"><span data-stu-id="b8121-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8121-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8121-104">Syntax</span></span>  
  
```  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8121-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b8121-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="b8121-106">[in] El token de metadatos de TypeRef para devolver la información de tipo que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="b8121-106">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="b8121-107">[in] El IID de la interfaz para devolver en `ppIScope`.</span><span class="sxs-lookup"><span data-stu-id="b8121-107">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="b8121-108">Normalmente, esto sería IID_IMetaDataImport.</span><span class="sxs-lookup"><span data-stu-id="b8121-108">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="b8121-109">[out] Interfaz para el ámbito del módulo en el que se define el tipo que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="b8121-109">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="b8121-110">[out] Un puntero a un token de TypeDef que representa el tipo que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="b8121-110">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8121-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b8121-111">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b8121-112">No utilice este método si se cargan varios dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b8121-112">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="b8121-113">El método no respeta los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b8121-113">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="b8121-114">Si se cargan varias versiones de un ensamblado y contienen el mismo tipo con el mismo espacio de nombres, el método devuelve el ámbito del módulo del primer tipo que busca.</span><span class="sxs-lookup"><span data-stu-id="b8121-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="b8121-115">El `ResolveTypeRef` método busca la definición de tipo en otros módulos.</span><span class="sxs-lookup"><span data-stu-id="b8121-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="b8121-116">Si se encuentra la definición de tipo, `ResolveTypeRef` devuelve una interfaz para ese ámbito de módulo, así como el token de TypeDef para el tipo.</span><span class="sxs-lookup"><span data-stu-id="b8121-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="b8121-117">Si se van a resolver la referencia de tipo tiene un ámbito de resolución AssemblyRef, el `ResolveTypeRef` método busca una coincidencia solo en los ámbitos de metadatos que ya se han abierto con las llamadas a la [IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)método o la [IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="b8121-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="b8121-118">Esto es porque `ResolveTypeRef` no se puede determinar desde únicamente al ámbito de AssemblyRef en disco o en la caché global de ensamblados el ensamblado se guarda.</span><span class="sxs-lookup"><span data-stu-id="b8121-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8121-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8121-119">Requirements</span></span>  
 <span data-ttu-id="b8121-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8121-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8121-121">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="b8121-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b8121-122">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b8121-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b8121-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8121-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8121-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8121-124">See also</span></span>
- [<span data-ttu-id="b8121-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8121-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b8121-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8121-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
