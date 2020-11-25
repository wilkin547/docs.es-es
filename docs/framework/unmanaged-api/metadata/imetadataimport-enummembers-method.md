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
ms.openlocfilehash: 92503df60ae44dfd44819fe3eda8e6a0549b2b66
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721000"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="114e5-102">IMetaDataImport::EnumMembers (Método)</span><span class="sxs-lookup"><span data-stu-id="114e5-102">IMetaDataImport::EnumMembers Method</span></span>

<span data-ttu-id="114e5-103">Enumera los tokens de MemberDef que representan a miembros del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="114e5-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="114e5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="114e5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembers (
   [in, out]  HCORENUM    *phEnum,
   [in]  mdTypeDef   cl,
   [out] mdToken     rMembers[],
   [in]  ULONG       cMax,
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="114e5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="114e5-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="114e5-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="114e5-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="114e5-107">de Un token de TypeDef que representa el tipo cuyos miembros se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="114e5-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="114e5-108">enuncia Matriz usada para contener los tokens de MemberDef.</span><span class="sxs-lookup"><span data-stu-id="114e5-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="114e5-109">[in] Tamaño máximo de la matriz `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="114e5-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="114e5-110">enuncia Número real de tokens de MemberDef devueltos en `rMembers` .</span><span class="sxs-lookup"><span data-stu-id="114e5-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="114e5-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="114e5-111">Return Value</span></span>  
  
|<span data-ttu-id="114e5-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="114e5-112">HRESULT</span></span>|<span data-ttu-id="114e5-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="114e5-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="114e5-114">`EnumMembers` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="114e5-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="114e5-115">No hay tokens de MemberDef que enumerar.</span><span class="sxs-lookup"><span data-stu-id="114e5-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="114e5-116">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="114e5-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="114e5-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="114e5-117">Remarks</span></span>  

 <span data-ttu-id="114e5-118">Al enumerar colecciones de miembros para una clase, `EnumMembers` solo devuelve los miembros (campos y métodos, pero **no** propiedades o eventos) definidos directamente en la clase.</span><span class="sxs-lookup"><span data-stu-id="114e5-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="114e5-119">No devuelve ningún miembro que la clase herede, aunque la clase proporcione una implementación para esos miembros heredados.</span><span class="sxs-lookup"><span data-stu-id="114e5-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="114e5-120">Para enumerar los miembros heredados, el llamador debe recorrer explícitamente la cadena de herencia.</span><span class="sxs-lookup"><span data-stu-id="114e5-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="114e5-121">Tenga en cuenta que las reglas para la cadena de herencia pueden variar en función del lenguaje o del compilador que emitió los metadatos originales.</span><span class="sxs-lookup"><span data-stu-id="114e5-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>

 <span data-ttu-id="114e5-122">No enumera las propiedades y los eventos `EnumMembers` .</span><span class="sxs-lookup"><span data-stu-id="114e5-122">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="114e5-123">Para enumerarlos, use [EnumProperties (](imetadataimport-enumproperties-method.md) o [enumevents (](imetadataimport-enumevents-method.md).</span><span class="sxs-lookup"><span data-stu-id="114e5-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="114e5-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="114e5-124">Requirements</span></span>  

 <span data-ttu-id="114e5-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="114e5-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="114e5-126">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="114e5-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="114e5-127">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="114e5-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="114e5-128">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="114e5-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="114e5-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="114e5-129">See also</span></span>

- [<span data-ttu-id="114e5-130">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="114e5-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="114e5-131">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="114e5-131">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
