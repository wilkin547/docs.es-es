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
ms.openlocfilehash: a0fd3fdb6dde9fd6b88ea6c64ed907c8a3e9e46d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175803"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="02aa4-102">IMetaDataEmit::DefinePermissionSet (Método)</span><span class="sxs-lookup"><span data-stu-id="02aa4-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="02aa4-103">Crea una definición para un conjunto de permisos con la firma de metadatos especificada y obtiene un token a esa definición de conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="02aa4-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02aa4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02aa4-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,
    [in]  DWORD          dwAction,
    [in]  void const     *pvPermission,
    [in]  ULONG          cbPermission,
    [out] mdPermission   *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02aa4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="02aa4-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="02aa4-106">[en] El objeto que se va a decorar.</span><span class="sxs-lookup"><span data-stu-id="02aa4-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="02aa4-107">[en] Un [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) valor que especifica el tipo de seguridad declarativa que se usará.</span><span class="sxs-lookup"><span data-stu-id="02aa4-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="02aa4-108">[en] El permiso BLOB.</span><span class="sxs-lookup"><span data-stu-id="02aa4-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="02aa4-109">[en] El tamaño, en `pvPermission`bytes, de .</span><span class="sxs-lookup"><span data-stu-id="02aa4-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="02aa4-110">[fuera] El token de permiso devuelto.</span><span class="sxs-lookup"><span data-stu-id="02aa4-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02aa4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02aa4-111">Requirements</span></span>  
 <span data-ttu-id="02aa4-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02aa4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02aa4-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="02aa4-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="02aa4-114">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="02aa4-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02aa4-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02aa4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02aa4-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="02aa4-116">See also</span></span>

- [<span data-ttu-id="02aa4-117">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="02aa4-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="02aa4-118">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="02aa4-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
