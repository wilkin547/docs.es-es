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
ms.openlocfilehash: 8b7edf1cc642228c4a79c855b51727264f31741c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107981"
---
# <a name="identity_attribute-structure"></a><span data-ttu-id="18016-102">IDENTITY_ATTRIBUTE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="18016-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="18016-103">Contiene información de atributos de metadatos sobre una instancia de [IDefinitionIdentity](idefinitionidentity-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="18016-103">Contains metadata attribute information about an [IDefinitionIdentity](idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18016-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="18016-104">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="18016-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="18016-105">Members</span></span>  
  
|<span data-ttu-id="18016-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="18016-106">Member</span></span>|<span data-ttu-id="18016-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="18016-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="18016-108">Un puntero a una cadena de caracteres terminada en null que contiene el espacio de nombres en el que se encuentra el atributo.</span><span class="sxs-lookup"><span data-stu-id="18016-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="18016-109">Puntero a una cadena de caracteres terminada en null que contiene el nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="18016-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="18016-110">Puntero a una cadena de caracteres terminada en null que contiene el valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="18016-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18016-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="18016-111">Remarks</span></span>  
 <span data-ttu-id="18016-112">La estructura `IDENTITY_ATTRIBUTE` contiene tres punteros a cadenas de caracteres terminadas en NULL.</span><span class="sxs-lookup"><span data-stu-id="18016-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="18016-113">Estas tres cadenas describen un atributo.</span><span class="sxs-lookup"><span data-stu-id="18016-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="18016-114">Una instancia de una estructura de `IDENTITY_ATTRIBUTE` está asociada a una instancia de una estructura [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="18016-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="18016-115">La estructura `IDENTITY_ATTRIBUTE` contiene las cadenas reales y la estructura `IDENTITY_ATTRIBUTE_BLOB` correspondiente muestra los desplazamientos a las tres cadenas enumeradas en la estructura `IDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="18016-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18016-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="18016-116">Requirements</span></span>  
 <span data-ttu-id="18016-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18016-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18016-118">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="18016-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="18016-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18016-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18016-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="18016-120">See also</span></span>

- [<span data-ttu-id="18016-121">IDefinitionIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="18016-121">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
- [<span data-ttu-id="18016-122">IDENTITY_ATTRIBUTE_BLOB (estructura)</span><span class="sxs-lookup"><span data-stu-id="18016-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](identity-attribute-blob-structure.md)
- [<span data-ttu-id="18016-123">Estructuras de fusión</span><span class="sxs-lookup"><span data-stu-id="18016-123">Fusion Structures</span></span>](fusion-structures.md)
