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
ms.openlocfilehash: e8d871f2ecbd96d5bda781b2ae11b94efd409442
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128406"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="df07d-102">IMetaDataImport::EnumMembers (Método)</span><span class="sxs-lookup"><span data-stu-id="df07d-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="df07d-103">Enumera los tokens de MemberDef que representan a miembros del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="df07d-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df07d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df07d-104">Syntax</span></span>  
  
```  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df07d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="df07d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="df07d-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="df07d-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="df07d-107">[in] Un token de TypeDef que representa el tipo cuyos miembros se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="df07d-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="df07d-108">[out] Matriz utilizada para almacenar los tokens de MemberDef.</span><span class="sxs-lookup"><span data-stu-id="df07d-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="df07d-109">[in] Tamaño máximo de la matriz `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="df07d-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="df07d-110">[out] El número real de los tokens de MemberDef devueltos en `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="df07d-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df07d-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="df07d-111">Return Value</span></span>  
  
|<span data-ttu-id="df07d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df07d-112">HRESULT</span></span>|<span data-ttu-id="df07d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="df07d-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumMembers` <span data-ttu-id="df07d-114">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="df07d-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="df07d-115">No hay ningún token MemberDef para enumerar.</span><span class="sxs-lookup"><span data-stu-id="df07d-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="df07d-116">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="df07d-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df07d-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="df07d-117">Remarks</span></span>  
 <span data-ttu-id="df07d-118">Al enumerar las colecciones de miembros para una clase, `EnumMembers` devuelve solo los miembros (campos y métodos, pero **no** propiedades o eventos) definidos directamente en la clase.</span><span class="sxs-lookup"><span data-stu-id="df07d-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="df07d-119">No devuelve a los miembros que hereda de la clase, incluso si la clase proporciona una implementación para esos miembros heredados.</span><span class="sxs-lookup"><span data-stu-id="df07d-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="df07d-120">Para enumerar los miembros heredados, el llamador debe recorrer explícitamente la cadena de herencia.</span><span class="sxs-lookup"><span data-stu-id="df07d-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="df07d-121">Tenga en cuenta que las reglas para la cadena de herencia pueden variar dependiendo del lenguaje o del compilador que genera los metadatos originales.</span><span class="sxs-lookup"><span data-stu-id="df07d-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>
 
 <span data-ttu-id="df07d-122">No se enumeran las propiedades y eventos mediante `EnumMembers`.</span><span class="sxs-lookup"><span data-stu-id="df07d-122">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="df07d-123">Para enumerarlos, utilice [EnumProperties](imetadataimport-enumproperties-method.md) o [EnumEvents](imetadataimport-enumevents-method.md).</span><span class="sxs-lookup"><span data-stu-id="df07d-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="df07d-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df07d-124">Requirements</span></span>  
 <span data-ttu-id="df07d-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df07d-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df07d-126">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="df07d-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="df07d-127">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="df07d-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="df07d-128">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="df07d-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="df07d-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="df07d-129">See also</span></span>

- [<span data-ttu-id="df07d-130">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="df07d-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="df07d-131">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="df07d-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
