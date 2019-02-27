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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de4bf2cf647682062fbacb4484ffae905d1b7995
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835374"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="eda56-102">IMetaDataImport::EnumMembers (Método)</span><span class="sxs-lookup"><span data-stu-id="eda56-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="eda56-103">Enumera los tokens de MemberDef que representan a miembros del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="eda56-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eda56-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eda56-104">Syntax</span></span>  
  
```  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eda56-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eda56-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="eda56-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="eda56-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="eda56-107">[in] Un token de TypeDef que representa el tipo cuyos miembros se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="eda56-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="eda56-108">[out] Matriz utilizada para almacenar los tokens de MemberDef.</span><span class="sxs-lookup"><span data-stu-id="eda56-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="eda56-109">[in] Tamaño máximo de la matriz `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="eda56-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="eda56-110">[out] El número real de los tokens de MemberDef devueltos en `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="eda56-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eda56-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="eda56-111">Return Value</span></span>  
  
|<span data-ttu-id="eda56-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eda56-112">HRESULT</span></span>|<span data-ttu-id="eda56-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="eda56-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="eda56-114">`EnumMembers` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="eda56-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="eda56-115">No hay ningún token MemberDef para enumerar.</span><span class="sxs-lookup"><span data-stu-id="eda56-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="eda56-116">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="eda56-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eda56-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eda56-117">Remarks</span></span>  
 <span data-ttu-id="eda56-118">Al enumerar las colecciones de miembros para una clase, `EnumMembers` devuelve solo los miembros (campos y métodos, pero **no** propiedades o eventos) definidos directamente en la clase.</span><span class="sxs-lookup"><span data-stu-id="eda56-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="eda56-119">No devuelve a los miembros que hereda de la clase, incluso si la clase proporciona una implementación para esos miembros heredados.</span><span class="sxs-lookup"><span data-stu-id="eda56-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="eda56-120">Para enumerar los miembros heredados, el llamador debe recorrer explícitamente la cadena de herencia.</span><span class="sxs-lookup"><span data-stu-id="eda56-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="eda56-121">Tenga en cuenta que las reglas para la cadena de herencia pueden variar dependiendo del lenguaje o del compilador que genera los metadatos originales.</span><span class="sxs-lookup"><span data-stu-id="eda56-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>
 
 <span data-ttu-id="eda56-122">No se enumeran las propiedades y eventos mediante `EnumMembers`.</span><span class="sxs-lookup"><span data-stu-id="eda56-122">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="eda56-123">Para enumerarlos, utilice [EnumProperties](imetadataimport-enumproperties-method.md) o [EnumEvents](imetadataimport-enumevents-method.md).</span><span class="sxs-lookup"><span data-stu-id="eda56-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="eda56-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eda56-124">Requirements</span></span>  
 <span data-ttu-id="eda56-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eda56-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eda56-126">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="eda56-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eda56-127">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eda56-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eda56-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eda56-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eda56-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="eda56-129">See also</span></span>
- [<span data-ttu-id="eda56-130">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="eda56-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="eda56-131">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="eda56-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
