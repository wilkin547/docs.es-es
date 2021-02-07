---
description: 'Más información sobre: IMetaDataImport:: Resolvetyperef ((método)'
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
ms.openlocfilehash: 0634bac77f457432948d0c2887d676e95430d05d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677568"
---
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="2bc2b-103">IMetaDataImport::ResolveTypeRef (Método)</span><span class="sxs-lookup"><span data-stu-id="2bc2b-103">IMetaDataImport::ResolveTypeRef Method</span></span>

<span data-ttu-id="2bc2b-104">Resuelve una <xref:System.Type> referencia representada por el token TypeRef especificado.</span><span class="sxs-lookup"><span data-stu-id="2bc2b-104">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bc2b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2bc2b-105">Syntax</span></span>  
  
```cpp  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bc2b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2bc2b-106">Parameters</span></span>  

 `tr`  
 <span data-ttu-id="2bc2b-107">de Token de metadatos de TypeRef para el que se va a devolver la información de tipos a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="2bc2b-107">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="2bc2b-108">de IID de la interfaz que se va a devolver en `ppIScope` .</span><span class="sxs-lookup"><span data-stu-id="2bc2b-108">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="2bc2b-109">Normalmente, esto sería IID_IMetaDataImport.</span><span class="sxs-lookup"><span data-stu-id="2bc2b-109">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="2bc2b-110">enuncia Interfaz al ámbito del módulo en el que se define el tipo al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="2bc2b-110">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="2bc2b-111">enuncia Un puntero a un token de TypeDef que representa el tipo al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="2bc2b-111">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bc2b-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2bc2b-112">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2bc2b-113">No use este método si se cargan varios dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2bc2b-113">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="2bc2b-114">El método no respeta los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2bc2b-114">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="2bc2b-115">Si se cargan varias versiones de un ensamblado y contienen el mismo tipo con el mismo espacio de nombres, el método devuelve el ámbito del módulo del primer tipo que encuentra.</span><span class="sxs-lookup"><span data-stu-id="2bc2b-115">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="2bc2b-116">El `ResolveTypeRef` método busca la definición de tipo en otros módulos.</span><span class="sxs-lookup"><span data-stu-id="2bc2b-116">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="2bc2b-117">Si se encuentra la definición de tipo, `ResolveTypeRef` devuelve una interfaz a ese ámbito de módulo, así como el token de TypeDef para el tipo.</span><span class="sxs-lookup"><span data-stu-id="2bc2b-117">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="2bc2b-118">Si la referencia de tipo que se va a resolver tiene un ámbito de resolución de AssemblyRef, el `ResolveTypeRef` método busca una coincidencia solo en los ámbitos de metadatos que ya se han abierto con llamadas al método [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) o al método [IMetaDataDispenser:: openscopeonmemory (](imetadatadispenser-openscopeonmemory-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2bc2b-118">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="2bc2b-119">Esto se debe `ResolveTypeRef` a que no puede determinar solo el ámbito de AssemblyRef en el que se almacena en el disco o en la caché global de ensamblados el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2bc2b-119">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bc2b-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2bc2b-120">Requirements</span></span>  

 <span data-ttu-id="2bc2b-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bc2b-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bc2b-122">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2bc2b-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2bc2b-123">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2bc2b-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2bc2b-124">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bc2b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bc2b-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2bc2b-125">See also</span></span>

- [<span data-ttu-id="2bc2b-126">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2bc2b-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="2bc2b-127">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2bc2b-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
