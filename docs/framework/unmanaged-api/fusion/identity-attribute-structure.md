---
description: 'Más información acerca de: estructura de IDENTITY_ATTRIBUTE'
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
ms.openlocfilehash: 52610961ab202fc79351073eac1846a1a63889e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800180"
---
# <a name="identity_attribute-structure"></a><span data-ttu-id="b95f9-103">IDENTITY_ATTRIBUTE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="b95f9-103">IDENTITY_ATTRIBUTE Structure</span></span>

<span data-ttu-id="b95f9-104">Contiene información de atributos de metadatos sobre una instancia de [IDefinitionIdentity](idefinitionidentity-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="b95f9-104">Contains metadata attribute information about an [IDefinitionIdentity](idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b95f9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b95f9-105">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="b95f9-106">Members</span><span class="sxs-lookup"><span data-stu-id="b95f9-106">Members</span></span>  
  
|<span data-ttu-id="b95f9-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="b95f9-107">Member</span></span>|<span data-ttu-id="b95f9-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b95f9-108">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="b95f9-109">Un puntero a una cadena de caracteres terminada en null que contiene el espacio de nombres en el que se encuentra el atributo.</span><span class="sxs-lookup"><span data-stu-id="b95f9-109">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="b95f9-110">Puntero a una cadena de caracteres terminada en null que contiene el nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="b95f9-110">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="b95f9-111">Puntero a una cadena de caracteres terminada en null que contiene el valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="b95f9-111">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b95f9-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b95f9-112">Remarks</span></span>  

 <span data-ttu-id="b95f9-113">La `IDENTITY_ATTRIBUTE` estructura contiene tres punteros a cadenas de caracteres terminadas en NULL.</span><span class="sxs-lookup"><span data-stu-id="b95f9-113">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="b95f9-114">Estas tres cadenas describen un atributo.</span><span class="sxs-lookup"><span data-stu-id="b95f9-114">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="b95f9-115">Una instancia de una `IDENTITY_ATTRIBUTE` estructura está asociada a una instancia de una estructura de [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="b95f9-115">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="b95f9-116">La `IDENTITY_ATTRIBUTE` estructura contiene las cadenas reales y la estructura correspondiente `IDENTITY_ATTRIBUTE_BLOB` muestra los desplazamientos a las tres cadenas enumeradas en la `IDENTITY_ATTRIBUTE` estructura.</span><span class="sxs-lookup"><span data-stu-id="b95f9-116">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b95f9-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b95f9-117">Requirements</span></span>  

 <span data-ttu-id="b95f9-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b95f9-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b95f9-119">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="b95f9-119">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="b95f9-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b95f9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b95f9-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="b95f9-121">See also</span></span>

- [<span data-ttu-id="b95f9-122">IDefinitionIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b95f9-122">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
- [<span data-ttu-id="b95f9-123">IDENTITY_ATTRIBUTE_BLOB (Estructura)</span><span class="sxs-lookup"><span data-stu-id="b95f9-123">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](identity-attribute-blob-structure.md)
- [<span data-ttu-id="b95f9-124">Estructuras de fusión</span><span class="sxs-lookup"><span data-stu-id="b95f9-124">Fusion Structures</span></span>](fusion-structures.md)
