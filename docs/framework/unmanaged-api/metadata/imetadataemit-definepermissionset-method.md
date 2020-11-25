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
ms.openlocfilehash: 3698525c139ed52b59ca577c598e675b6c26eef4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719520"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="ed636-102">IMetaDataEmit::DefinePermissionSet (Método)</span><span class="sxs-lookup"><span data-stu-id="ed636-102">IMetaDataEmit::DefinePermissionSet Method</span></span>

<span data-ttu-id="ed636-103">Crea una definición para un conjunto de permisos con la firma de metadatos especificada y obtiene un token para esa definición de conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="ed636-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed636-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed636-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,
    [in]  DWORD          dwAction,
    [in]  void const     *pvPermission,
    [in]  ULONG          cbPermission,
    [out] mdPermission   *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed636-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ed636-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="ed636-106">de Objeto que se va a decorar.</span><span class="sxs-lookup"><span data-stu-id="ed636-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="ed636-107">de Valor [cordeclsecurity (](cordeclsecurity-enumeration.md) que especifica el tipo de seguridad declarativa que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="ed636-107">[in] A [CorDeclSecurity](cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="ed636-108">de El BLOB de permiso.</span><span class="sxs-lookup"><span data-stu-id="ed636-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="ed636-109">de Tamaño, en bytes, de `pvPermission` .</span><span class="sxs-lookup"><span data-stu-id="ed636-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="ed636-110">enuncia El token de permiso devuelto.</span><span class="sxs-lookup"><span data-stu-id="ed636-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed636-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed636-111">Requirements</span></span>  

 <span data-ttu-id="ed636-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed636-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed636-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ed636-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ed636-114">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ed636-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed636-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed636-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed636-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed636-116">See also</span></span>

- [<span data-ttu-id="ed636-117">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed636-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ed636-118">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed636-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
