---
title: IDENTITY_ATTRIBUTE (Estructura)
ms.date: 03/30/2017
api_name:
- IDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE
helpviewer_keywords:
- IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e26a90b6725d53774053293c04842b761da6ab12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717680"
---
# <a name="identityattribute-structure"></a><span data-ttu-id="52308-102">IDENTITY_ATTRIBUTE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="52308-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="52308-103">Contiene información de atributos de metadatos sobre un [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instancia.</span><span class="sxs-lookup"><span data-stu-id="52308-103">Contains metadata attribute information about an [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52308-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52308-104">Syntax</span></span>  
  
```  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="52308-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="52308-105">Members</span></span>  
  
|<span data-ttu-id="52308-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="52308-106">Member</span></span>|<span data-ttu-id="52308-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="52308-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="52308-108">Un puntero a una cadena de caracteres terminada en null que contiene el espacio de nombres del atributo está en.</span><span class="sxs-lookup"><span data-stu-id="52308-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="52308-109">Un puntero a una cadena de caracteres terminada en null que contiene el nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="52308-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="52308-110">Un puntero a una cadena de caracteres terminada en null que contiene el valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="52308-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52308-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="52308-111">Remarks</span></span>  
 <span data-ttu-id="52308-112">El `IDENTITY_ATTRIBUTE` estructura contiene tres punteros a cadenas de caracteres terminada en null.</span><span class="sxs-lookup"><span data-stu-id="52308-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="52308-113">Estas tres cadenas describen un atributo.</span><span class="sxs-lookup"><span data-stu-id="52308-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="52308-114">Una instancia de un `IDENTITY_ATTRIBUTE` estructura está asociada a una instancia de un [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="52308-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="52308-115">El `IDENTITY_ATTRIBUTE` estructura contiene las cadenas reales y la correspondiente `IDENTITY_ATTRIBUTE_BLOB` estructura enumera los desplazamientos a las tres cadenas enumeradas en la `IDENTITY_ATTRIBUTE` estructura.</span><span class="sxs-lookup"><span data-stu-id="52308-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52308-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52308-116">Requirements</span></span>  
 <span data-ttu-id="52308-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52308-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52308-118">**Encabezado**: Isolation.h</span><span class="sxs-lookup"><span data-stu-id="52308-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="52308-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52308-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52308-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="52308-120">See also</span></span>
- [<span data-ttu-id="52308-121">IDefinitionIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="52308-121">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
- [<span data-ttu-id="52308-122">IDENTITY_ATTRIBUTE_BLOB (estructura)</span><span class="sxs-lookup"><span data-stu-id="52308-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)
- [<span data-ttu-id="52308-123">Estructuras de fusión</span><span class="sxs-lookup"><span data-stu-id="52308-123">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
