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
ms.openlocfilehash: 76c5519a6cd1b8994e2f869281f13d8269e89fde
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702829"
---
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="ec7a5-102">IMetaDataImport::ResolveTypeRef (Método)</span><span class="sxs-lookup"><span data-stu-id="ec7a5-102">IMetaDataImport::ResolveTypeRef Method</span></span>

<span data-ttu-id="ec7a5-103">Resuelve una <xref:System.Type> referencia representada por el token TypeRef especificado.</span><span class="sxs-lookup"><span data-stu-id="ec7a5-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec7a5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec7a5-104">Syntax</span></span>  
  
```cpp  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec7a5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ec7a5-105">Parameters</span></span>  

 `tr`  
 <span data-ttu-id="ec7a5-106">de Token de metadatos de TypeRef para el que se va a devolver la información de tipos a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="ec7a5-106">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="ec7a5-107">de IID de la interfaz que se va a devolver en `ppIScope` .</span><span class="sxs-lookup"><span data-stu-id="ec7a5-107">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="ec7a5-108">Normalmente, esto sería IID_IMetaDataImport.</span><span class="sxs-lookup"><span data-stu-id="ec7a5-108">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="ec7a5-109">enuncia Interfaz al ámbito del módulo en el que se define el tipo al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="ec7a5-109">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="ec7a5-110">enuncia Un puntero a un token de TypeDef que representa el tipo al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="ec7a5-110">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec7a5-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ec7a5-111">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ec7a5-112">No use este método si se cargan varios dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec7a5-112">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="ec7a5-113">El método no respeta los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec7a5-113">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="ec7a5-114">Si se cargan varias versiones de un ensamblado y contienen el mismo tipo con el mismo espacio de nombres, el método devuelve el ámbito del módulo del primer tipo que encuentra.</span><span class="sxs-lookup"><span data-stu-id="ec7a5-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="ec7a5-115">El `ResolveTypeRef` método busca la definición de tipo en otros módulos.</span><span class="sxs-lookup"><span data-stu-id="ec7a5-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="ec7a5-116">Si se encuentra la definición de tipo, `ResolveTypeRef` devuelve una interfaz a ese ámbito de módulo, así como el token de TypeDef para el tipo.</span><span class="sxs-lookup"><span data-stu-id="ec7a5-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="ec7a5-117">Si la referencia de tipo que se va a resolver tiene un ámbito de resolución de AssemblyRef, el `ResolveTypeRef` método busca una coincidencia solo en los ámbitos de metadatos que ya se han abierto con llamadas al método [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) o al método [IMetaDataDispenser:: openscopeonmemory (](imetadatadispenser-openscopeonmemory-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ec7a5-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="ec7a5-118">Esto se debe `ResolveTypeRef` a que no puede determinar solo el ámbito de AssemblyRef en el que se almacena en el disco o en la caché global de ensamblados el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ec7a5-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec7a5-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec7a5-119">Requirements</span></span>  

 <span data-ttu-id="ec7a5-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec7a5-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec7a5-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ec7a5-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ec7a5-122">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ec7a5-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ec7a5-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec7a5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec7a5-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec7a5-124">See also</span></span>

- [<span data-ttu-id="ec7a5-125">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec7a5-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ec7a5-126">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec7a5-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
