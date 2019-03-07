---
title: IMetaDataEmit::DefinePermissionSet (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePermissionSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4188d1ef83f685bf39bdf951939e0ec6493b323d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466406"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="722ba-102">IMetaDataEmit::DefinePermissionSet (Método)</span><span class="sxs-lookup"><span data-stu-id="722ba-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="722ba-103">Crea una definición para un conjunto de permisos con la firma de metadatos especificado y obtiene un token para esa definición del conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="722ba-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="722ba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="722ba-104">Syntax</span></span>  
  
```  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,   
    [in]  DWORD          dwAction,   
    [in]  void const     *pvPermission,   
    [in]  ULONG          cbPermission,   
    [out] mdPermission   *ppm   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="722ba-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="722ba-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="722ba-106">[in] El objeto que va a ser representativo.</span><span class="sxs-lookup"><span data-stu-id="722ba-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="722ba-107">[in] Un [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) valor que especifica el tipo de seguridad declarativa para usarse.</span><span class="sxs-lookup"><span data-stu-id="722ba-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="722ba-108">[in] El permiso de BLOB.</span><span class="sxs-lookup"><span data-stu-id="722ba-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="722ba-109">[in] El tamaño, en bytes, de `pvPermission`.</span><span class="sxs-lookup"><span data-stu-id="722ba-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="722ba-110">[out] El token devuelto permiso.</span><span class="sxs-lookup"><span data-stu-id="722ba-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="722ba-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="722ba-111">Requirements</span></span>  
 <span data-ttu-id="722ba-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="722ba-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="722ba-113">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="722ba-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="722ba-114">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="722ba-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="722ba-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="722ba-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="722ba-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="722ba-116">See also</span></span>
- [<span data-ttu-id="722ba-117">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="722ba-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="722ba-118">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="722ba-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
