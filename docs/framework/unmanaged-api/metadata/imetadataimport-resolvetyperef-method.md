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
ms.openlocfilehash: f55af87e21b48430807166cb03e1d41271e830a1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503450"
---
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="868fc-102">IMetaDataImport::ResolveTypeRef (Método)</span><span class="sxs-lookup"><span data-stu-id="868fc-102">IMetaDataImport::ResolveTypeRef Method</span></span>
<span data-ttu-id="868fc-103">Resuelve una <xref:System.Type> referencia representada por el token TypeRef especificado.</span><span class="sxs-lookup"><span data-stu-id="868fc-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="868fc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="868fc-104">Syntax</span></span>  
  
```cpp  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="868fc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="868fc-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="868fc-106">de Token de metadatos de TypeRef para el que se va a devolver la información de tipos a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="868fc-106">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="868fc-107">de IID de la interfaz que se va a devolver en `ppIScope` .</span><span class="sxs-lookup"><span data-stu-id="868fc-107">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="868fc-108">Normalmente, esto sería IID_IMetaDataImport.</span><span class="sxs-lookup"><span data-stu-id="868fc-108">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="868fc-109">enuncia Interfaz al ámbito del módulo en el que se define el tipo al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="868fc-109">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="868fc-110">enuncia Un puntero a un token de TypeDef que representa el tipo al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="868fc-110">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="868fc-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="868fc-111">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="868fc-112">No use este método si se cargan varios dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="868fc-112">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="868fc-113">El método no respeta los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="868fc-113">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="868fc-114">Si se cargan varias versiones de un ensamblado y contienen el mismo tipo con el mismo espacio de nombres, el método devuelve el ámbito del módulo del primer tipo que encuentra.</span><span class="sxs-lookup"><span data-stu-id="868fc-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="868fc-115">El `ResolveTypeRef` método busca la definición de tipo en otros módulos.</span><span class="sxs-lookup"><span data-stu-id="868fc-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="868fc-116">Si se encuentra la definición de tipo, `ResolveTypeRef` devuelve una interfaz a ese ámbito de módulo, así como el token de TypeDef para el tipo.</span><span class="sxs-lookup"><span data-stu-id="868fc-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="868fc-117">Si la referencia de tipo que se va a resolver tiene un ámbito de resolución de AssemblyRef, el `ResolveTypeRef` método busca una coincidencia solo en los ámbitos de metadatos que ya se han abierto con llamadas al método [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) o al método [IMetaDataDispenser:: openscopeonmemory (](imetadatadispenser-openscopeonmemory-method.md) .</span><span class="sxs-lookup"><span data-stu-id="868fc-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="868fc-118">Esto se debe `ResolveTypeRef` a que no puede determinar solo el ámbito de AssemblyRef en el que se almacena en el disco o en la caché global de ensamblados el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="868fc-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="868fc-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="868fc-119">Requirements</span></span>  
 <span data-ttu-id="868fc-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="868fc-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="868fc-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="868fc-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="868fc-122">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="868fc-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="868fc-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="868fc-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="868fc-124">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="868fc-124">See also</span></span>

- [<span data-ttu-id="868fc-125">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="868fc-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="868fc-126">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="868fc-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
