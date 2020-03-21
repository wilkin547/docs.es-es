---
title: IMetaDataImport::EnumMembers (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type:
- apiref
ms.openlocfilehash: 20c7a90f27defa18a5ef311d1f3a549b81fc5c40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175491"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="cf722-102">IMetaDataImport::EnumMembers (Método)</span><span class="sxs-lookup"><span data-stu-id="cf722-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="cf722-103">Enumera los tokens de MemberDef que representan a miembros del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="cf722-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf722-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf722-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembers (
   [in, out]  HCORENUM    *phEnum,
   [in]  mdTypeDef   cl,
   [out] mdToken     rMembers[],
   [in]  ULONG       cMax,
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf722-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf722-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="cf722-106">[adentro, fuera] Un puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="cf722-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="cf722-107">[en] Un token TypeDef que representa el tipo cuyos miembros se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="cf722-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="cf722-108">[fuera] Matriz utilizada para contener los tokens MemberDef.</span><span class="sxs-lookup"><span data-stu-id="cf722-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="cf722-109">[in] Tamaño máximo de la matriz `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="cf722-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="cf722-110">[fuera] El número real de tokens `rMembers`MemberDef devueltos en .</span><span class="sxs-lookup"><span data-stu-id="cf722-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf722-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cf722-111">Return Value</span></span>  
  
|<span data-ttu-id="cf722-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cf722-112">HRESULT</span></span>|<span data-ttu-id="cf722-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="cf722-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="cf722-114">`EnumMembers`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="cf722-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="cf722-115">No hay tokens MemberDef que enumerar.</span><span class="sxs-lookup"><span data-stu-id="cf722-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="cf722-116">En ese `pcTokens` caso, es cero.</span><span class="sxs-lookup"><span data-stu-id="cf722-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf722-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cf722-117">Remarks</span></span>  
 <span data-ttu-id="cf722-118">Al enumerar colecciones de miembros para una clase, `EnumMembers` devuelve solo los miembros (campos y métodos, pero **no** las propiedades o eventos) definidos directamente en la clase.</span><span class="sxs-lookup"><span data-stu-id="cf722-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="cf722-119">No devuelve ningún miembro que herede la clase, incluso si la clase proporciona una implementación para esos miembros heredados.</span><span class="sxs-lookup"><span data-stu-id="cf722-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="cf722-120">Para enumerar los miembros heredados, el llamador debe recorrer explícitamente la cadena de herencia.</span><span class="sxs-lookup"><span data-stu-id="cf722-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="cf722-121">Tenga en cuenta que las reglas de la cadena de herencia pueden variar en función del lenguaje o compilador que emitió los metadatos originales.</span><span class="sxs-lookup"><span data-stu-id="cf722-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>

 <span data-ttu-id="cf722-122">Las propiedades y los `EnumMembers`eventos no se enumeran mediante .</span><span class="sxs-lookup"><span data-stu-id="cf722-122">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="cf722-123">Para enumerarlos, utilice [EnumProperties](imetadataimport-enumproperties-method.md) o [EnumEvents](imetadataimport-enumevents-method.md).</span><span class="sxs-lookup"><span data-stu-id="cf722-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="cf722-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf722-124">Requirements</span></span>  
 <span data-ttu-id="cf722-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf722-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf722-126">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cf722-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cf722-127">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cf722-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cf722-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf722-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf722-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cf722-129">See also</span></span>

- [<span data-ttu-id="cf722-130">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf722-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="cf722-131">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf722-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
