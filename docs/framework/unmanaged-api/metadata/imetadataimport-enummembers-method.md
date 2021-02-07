---
description: 'Más información sobre: IMetaDataImport:: EnumMembers ((método)'
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
ms.openlocfilehash: 3b56b25c6c581f6bfc3303a55a49a12ffcc73494
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670819"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="86734-103">IMetaDataImport::EnumMembers (Método)</span><span class="sxs-lookup"><span data-stu-id="86734-103">IMetaDataImport::EnumMembers Method</span></span>

<span data-ttu-id="86734-104">Enumera los tokens de MemberDef que representan a miembros del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="86734-104">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86734-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86734-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembers (
   [in, out]  HCORENUM    *phEnum,
   [in]  mdTypeDef   cl,
   [out] mdToken     rMembers[],
   [in]  ULONG       cMax,
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86734-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="86734-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="86734-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="86734-107">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="86734-108">de Un token de TypeDef que representa el tipo cuyos miembros se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="86734-108">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="86734-109">enuncia Matriz usada para contener los tokens de MemberDef.</span><span class="sxs-lookup"><span data-stu-id="86734-109">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="86734-110">[in] Tamaño máximo de la matriz `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="86734-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="86734-111">enuncia Número real de tokens de MemberDef devueltos en `rMembers` .</span><span class="sxs-lookup"><span data-stu-id="86734-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86734-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="86734-112">Return Value</span></span>  
  
|<span data-ttu-id="86734-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="86734-113">HRESULT</span></span>|<span data-ttu-id="86734-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="86734-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="86734-115">`EnumMembers` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="86734-115">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="86734-116">No hay tokens de MemberDef que enumerar.</span><span class="sxs-lookup"><span data-stu-id="86734-116">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="86734-117">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="86734-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86734-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="86734-118">Remarks</span></span>  

 <span data-ttu-id="86734-119">Al enumerar colecciones de miembros para una clase, `EnumMembers` solo devuelve los miembros (campos y métodos, pero **no** propiedades o eventos) definidos directamente en la clase.</span><span class="sxs-lookup"><span data-stu-id="86734-119">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="86734-120">No devuelve ningún miembro que la clase herede, aunque la clase proporcione una implementación para esos miembros heredados.</span><span class="sxs-lookup"><span data-stu-id="86734-120">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="86734-121">Para enumerar los miembros heredados, el llamador debe recorrer explícitamente la cadena de herencia.</span><span class="sxs-lookup"><span data-stu-id="86734-121">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="86734-122">Tenga en cuenta que las reglas para la cadena de herencia pueden variar en función del lenguaje o del compilador que emitió los metadatos originales.</span><span class="sxs-lookup"><span data-stu-id="86734-122">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>

 <span data-ttu-id="86734-123">No enumera las propiedades y los eventos `EnumMembers` .</span><span class="sxs-lookup"><span data-stu-id="86734-123">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="86734-124">Para enumerarlos, use [EnumProperties (](imetadataimport-enumproperties-method.md) o [enumevents (](imetadataimport-enumevents-method.md).</span><span class="sxs-lookup"><span data-stu-id="86734-124">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="86734-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="86734-125">Requirements</span></span>  

 <span data-ttu-id="86734-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86734-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86734-127">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="86734-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="86734-128">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="86734-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="86734-129">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86734-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86734-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="86734-130">See also</span></span>

- [<span data-ttu-id="86734-131">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="86734-131">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="86734-132">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="86734-132">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
