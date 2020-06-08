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
ms.openlocfilehash: cc3bc5140da0634b5172f6253de3de37bff487f1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492064"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="3ede6-102">IMetaDataImport::EnumMembers (Método)</span><span class="sxs-lookup"><span data-stu-id="3ede6-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="3ede6-103">Enumera los tokens de MemberDef que representan a miembros del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="3ede6-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ede6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ede6-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembers (
   [in, out]  HCORENUM    *phEnum,
   [in]  mdTypeDef   cl,
   [out] mdToken     rMembers[],
   [in]  ULONG       cMax,
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ede6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3ede6-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3ede6-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="3ede6-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="3ede6-107">de Un token de TypeDef que representa el tipo cuyos miembros se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="3ede6-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="3ede6-108">enuncia Matriz usada para contener los tokens de MemberDef.</span><span class="sxs-lookup"><span data-stu-id="3ede6-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3ede6-109">[in] Tamaño máximo de la matriz `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="3ede6-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="3ede6-110">enuncia Número real de tokens de MemberDef devueltos en `rMembers` .</span><span class="sxs-lookup"><span data-stu-id="3ede6-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ede6-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3ede6-111">Return Value</span></span>  
  
|<span data-ttu-id="3ede6-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3ede6-112">HRESULT</span></span>|<span data-ttu-id="3ede6-113">Description</span><span class="sxs-lookup"><span data-stu-id="3ede6-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3ede6-114">`EnumMembers`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3ede6-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3ede6-115">No hay tokens de MemberDef que enumerar.</span><span class="sxs-lookup"><span data-stu-id="3ede6-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="3ede6-116">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="3ede6-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ede6-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3ede6-117">Remarks</span></span>  
 <span data-ttu-id="3ede6-118">Al enumerar colecciones de miembros para una clase, `EnumMembers` solo devuelve los miembros (campos y métodos, pero **no** propiedades o eventos) definidos directamente en la clase.</span><span class="sxs-lookup"><span data-stu-id="3ede6-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="3ede6-119">No devuelve ningún miembro que la clase herede, aunque la clase proporcione una implementación para esos miembros heredados.</span><span class="sxs-lookup"><span data-stu-id="3ede6-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="3ede6-120">Para enumerar los miembros heredados, el llamador debe recorrer explícitamente la cadena de herencia.</span><span class="sxs-lookup"><span data-stu-id="3ede6-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="3ede6-121">Tenga en cuenta que las reglas para la cadena de herencia pueden variar en función del lenguaje o del compilador que emitió los metadatos originales.</span><span class="sxs-lookup"><span data-stu-id="3ede6-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>

 <span data-ttu-id="3ede6-122">No enumera las propiedades y los eventos `EnumMembers` .</span><span class="sxs-lookup"><span data-stu-id="3ede6-122">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="3ede6-123">Para enumerarlos, use [EnumProperties (](imetadataimport-enumproperties-method.md) o [enumevents (](imetadataimport-enumevents-method.md).</span><span class="sxs-lookup"><span data-stu-id="3ede6-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="3ede6-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3ede6-124">Requirements</span></span>  
 <span data-ttu-id="3ede6-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ede6-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ede6-126">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3ede6-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3ede6-127">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3ede6-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3ede6-128">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ede6-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ede6-129">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="3ede6-129">See also</span></span>

- [<span data-ttu-id="3ede6-130">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ede6-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="3ede6-131">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ede6-131">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
