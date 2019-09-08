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
ms.openlocfilehash: e0bcabb32d50b236d42a555c073b50ba3a234dde
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796490"
---
# <a name="identity_attribute-structure"></a><span data-ttu-id="d7cc7-102">IDENTITY_ATTRIBUTE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="d7cc7-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="d7cc7-103">Contiene información de atributos de metadatos sobre una instancia de [IDefinitionIdentity](idefinitionidentity-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d7cc7-103">Contains metadata attribute information about an [IDefinitionIdentity](idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7cc7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d7cc7-104">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="d7cc7-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="d7cc7-105">Members</span></span>  
  
|<span data-ttu-id="d7cc7-106">Member</span><span class="sxs-lookup"><span data-stu-id="d7cc7-106">Member</span></span>|<span data-ttu-id="d7cc7-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d7cc7-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="d7cc7-108">Un puntero a una cadena de caracteres terminada en null que contiene el espacio de nombres en el que se encuentra el atributo.</span><span class="sxs-lookup"><span data-stu-id="d7cc7-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="d7cc7-109">Puntero a una cadena de caracteres terminada en null que contiene el nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="d7cc7-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="d7cc7-110">Puntero a una cadena de caracteres terminada en null que contiene el valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="d7cc7-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7cc7-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d7cc7-111">Remarks</span></span>  
 <span data-ttu-id="d7cc7-112">La `IDENTITY_ATTRIBUTE` estructura contiene tres punteros a cadenas de caracteres terminadas en NULL.</span><span class="sxs-lookup"><span data-stu-id="d7cc7-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="d7cc7-113">Estas tres cadenas describen un atributo.</span><span class="sxs-lookup"><span data-stu-id="d7cc7-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="d7cc7-114">Una instancia de una `IDENTITY_ATTRIBUTE` estructura está asociada a una instancia de una estructura [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="d7cc7-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="d7cc7-115">La `IDENTITY_ATTRIBUTE` estructura contiene las cadenas reales y la estructura correspondiente `IDENTITY_ATTRIBUTE_BLOB` muestra los desplazamientos a las tres cadenas enumeradas en `IDENTITY_ATTRIBUTE` la estructura.</span><span class="sxs-lookup"><span data-stu-id="d7cc7-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7cc7-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d7cc7-116">Requirements</span></span>  
 <span data-ttu-id="d7cc7-117">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7cc7-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7cc7-118">**Encabezado**: Isolation. h</span><span class="sxs-lookup"><span data-stu-id="d7cc7-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="d7cc7-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7cc7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7cc7-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7cc7-120">See also</span></span>

- [<span data-ttu-id="d7cc7-121">IDefinitionIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d7cc7-121">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
- [<span data-ttu-id="d7cc7-122">IDENTITY_ATTRIBUTE_BLOB (estructura)</span><span class="sxs-lookup"><span data-stu-id="d7cc7-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](identity-attribute-blob-structure.md)
- [<span data-ttu-id="d7cc7-123">Estructuras de fusión</span><span class="sxs-lookup"><span data-stu-id="d7cc7-123">Fusion Structures</span></span>](fusion-structures.md)
