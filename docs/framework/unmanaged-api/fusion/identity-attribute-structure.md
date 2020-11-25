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
ms.openlocfilehash: da4b1d6f2a7079ef33859fce29c9555ac06fcfc2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725656"
---
# <a name="identity_attribute-structure"></a><span data-ttu-id="25a02-102">IDENTITY_ATTRIBUTE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="25a02-102">IDENTITY_ATTRIBUTE Structure</span></span>

<span data-ttu-id="25a02-103">Contiene información de atributos de metadatos sobre una instancia de [IDefinitionIdentity](idefinitionidentity-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="25a02-103">Contains metadata attribute information about an [IDefinitionIdentity](idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25a02-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25a02-104">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="25a02-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="25a02-105">Members</span></span>  
  
|<span data-ttu-id="25a02-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="25a02-106">Member</span></span>|<span data-ttu-id="25a02-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="25a02-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="25a02-108">Un puntero a una cadena de caracteres terminada en null que contiene el espacio de nombres en el que se encuentra el atributo.</span><span class="sxs-lookup"><span data-stu-id="25a02-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="25a02-109">Puntero a una cadena de caracteres terminada en null que contiene el nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="25a02-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="25a02-110">Puntero a una cadena de caracteres terminada en null que contiene el valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="25a02-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25a02-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="25a02-111">Remarks</span></span>  

 <span data-ttu-id="25a02-112">La `IDENTITY_ATTRIBUTE` estructura contiene tres punteros a cadenas de caracteres terminadas en NULL.</span><span class="sxs-lookup"><span data-stu-id="25a02-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="25a02-113">Estas tres cadenas describen un atributo.</span><span class="sxs-lookup"><span data-stu-id="25a02-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="25a02-114">Una instancia de una `IDENTITY_ATTRIBUTE` estructura está asociada a una instancia de una estructura de [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="25a02-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="25a02-115">La `IDENTITY_ATTRIBUTE` estructura contiene las cadenas reales y la estructura correspondiente `IDENTITY_ATTRIBUTE_BLOB` muestra los desplazamientos a las tres cadenas enumeradas en la `IDENTITY_ATTRIBUTE` estructura.</span><span class="sxs-lookup"><span data-stu-id="25a02-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25a02-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="25a02-116">Requirements</span></span>  

 <span data-ttu-id="25a02-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25a02-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25a02-118">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="25a02-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="25a02-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25a02-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25a02-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="25a02-120">See also</span></span>

- [<span data-ttu-id="25a02-121">IDefinitionIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="25a02-121">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
- [<span data-ttu-id="25a02-122">IDENTITY_ATTRIBUTE_BLOB (Estructura)</span><span class="sxs-lookup"><span data-stu-id="25a02-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](identity-attribute-blob-structure.md)
- [<span data-ttu-id="25a02-123">Estructuras de fusión</span><span class="sxs-lookup"><span data-stu-id="25a02-123">Fusion Structures</span></span>](fusion-structures.md)
