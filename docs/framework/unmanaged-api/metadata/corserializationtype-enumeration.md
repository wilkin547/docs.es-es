---
title: CorSerializationType (Enumeración)
ms.date: 03/30/2017
api_name:
- CorSerializationType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSerializationType
helpviewer_keywords:
- CorSerializationType enumeration [.NET Framework metadata]
ms.assetid: 6b1fcd11-c7fb-4be2-8910-abc862d4caf4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b9b7138d403bc84ab377301b82d697fd137416c6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781594"
---
# <a name="corserializationtype-enumeration"></a><span data-ttu-id="cd4d9-102">CorSerializationType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="cd4d9-102">CorSerializationType Enumeration</span></span>
<span data-ttu-id="cd4d9-103">Especifica cómo se serializa un objeto por common language runtime.</span><span class="sxs-lookup"><span data-stu-id="cd4d9-103">Specifies how an object is serialized by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd4d9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd4d9-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSerializationType {  
  
    SERIALIZATION_TYPE_UNDEFINED     = 0,  
    SERIALIZATION_TYPE_BOOLEAN       = ELEMENT_TYPE_BOOLEAN,  
    SERIALIZATION_TYPE_CHAR          = ELEMENT_TYPE_CHAR,  
    SERIALIZATION_TYPE_I1            = ELEMENT_TYPE_I1,  
    SERIALIZATION_TYPE_U1            = ELEMENT_TYPE_U1,  
    SERIALIZATION_TYPE_I2            = ELEMENT_TYPE_I2,  
    SERIALIZATION_TYPE_U2            = ELEMENT_TYPE_U2,  
    SERIALIZATION_TYPE_I4            = ELEMENT_TYPE_I4,  
    SERIALIZATION_TYPE_U4            = ELEMENT_TYPE_U4,  
    SERIALIZATION_TYPE_I8            = ELEMENT_TYPE_I8,  
    SERIALIZATION_TYPE_U8            = ELEMENT_TYPE_U8,  
    SERIALIZATION_TYPE_R4            = ELEMENT_TYPE_R4,  
    SERIALIZATION_TYPE_R8            = ELEMENT_TYPE_R8,  
    SERIALIZATION_TYPE_STRING        = ELEMENT_TYPE_STRING,  
    SERIALIZATION_TYPE_SZARRAY       = ELEMENT_TYPE_SZARRAY,  
    SERIALIZATION_TYPE_TYPE          = 0x50,  
    SERIALIZATION_TYPE_TAGGED_OBJECT = 0x51,  
    SERIALIZATION_TYPE_FIELD         = 0x53,  
    SERIALIZATION_TYPE_PROPERTY      = 0x54,  
    SERIALIZATION_TYPE_ENUM          = 0x55  
  
} CorSerializationType;  
```  
  
## <a name="members"></a><span data-ttu-id="cd4d9-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="cd4d9-105">Members</span></span>  
  
|<span data-ttu-id="cd4d9-106">Member</span><span class="sxs-lookup"><span data-stu-id="cd4d9-106">Member</span></span>|<span data-ttu-id="cd4d9-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cd4d9-107">Description</span></span>|  
|------------|-----------------|  
|`SERIALIZATION_TYPE_UNDEFINED`|<span data-ttu-id="cd4d9-108">La serialización del objeto es indefinida.</span><span class="sxs-lookup"><span data-stu-id="cd4d9-108">Serialization of the object is undefined.</span></span>|  
|`SERIALIZATION_TYPE_BOOLEAN`|<span data-ttu-id="cd4d9-109">El objeto se serializa como un tipo booleano</span><span class="sxs-lookup"><span data-stu-id="cd4d9-109">Object is serialized as a Boolean type</span></span>|  
|`SERIALIZATION_TYPE_CHAR`|<span data-ttu-id="cd4d9-110">Objeto se serializa como un tipo de carácter.</span><span class="sxs-lookup"><span data-stu-id="cd4d9-110">Object is serialized as a character type.</span></span>|  
|`SERIALIZATION_TYPE_I1`|<span data-ttu-id="cd4d9-111">Objeto se serializa como un entero de 1 byte con signo.</span><span class="sxs-lookup"><span data-stu-id="cd4d9-111">Object is serialized as a signed 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U1`|<span data-ttu-id="cd4d9-112">Objeto se serializa como un entero de 1 byte sin signo.</span><span class="sxs-lookup"><span data-stu-id="cd4d9-112">Object is serialized as an unsigned 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I2`|<span data-ttu-id="cd4d9-113">Objeto se serializa como un entero de 2 bytes con signo.</span><span class="sxs-lookup"><span data-stu-id="cd4d9-113">Object is serialized as a signed 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U2`|<span data-ttu-id="cd4d9-114">Objeto se serializa como un entero de 2 bytes sin signo.</span><span class="sxs-lookup"><span data-stu-id="cd4d9-114">Object is serialized as an unsigned 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I4`|<span data-ttu-id="cd4d9-115">Objeto se serializa como un entero de 4 bytes con signo.</span><span class="sxs-lookup"><span data-stu-id="cd4d9-115">Object is serialized as a signed 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U4`|<span data-ttu-id="cd4d9-116">Objeto se serializa como un entero de 4 bytes sin signo.</span><span class="sxs-lookup"><span data-stu-id="cd4d9-116">Object is serialized as an unsigned 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I8`|<span data-ttu-id="cd4d9-117">Objeto se serializa como un entero de 8 bytes con signo.</span><span class="sxs-lookup"><span data-stu-id="cd4d9-117">Object is serialized as a signed 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U8`|<span data-ttu-id="cd4d9-118">Objeto se serializa como un entero de 8 bytes sin signo.</span><span class="sxs-lookup"><span data-stu-id="cd4d9-118">Object is serialized as an unsigned 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_R4`|<span data-ttu-id="cd4d9-119">Objeto se serializa como un punto flotante de 4 bytes.</span><span class="sxs-lookup"><span data-stu-id="cd4d9-119">Object is serialized as a 4-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_R8`|<span data-ttu-id="cd4d9-120">Objeto se serializa como un punto flotante de 8 bytes.</span><span class="sxs-lookup"><span data-stu-id="cd4d9-120">Object is serialized as an 8-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_STRING`|<span data-ttu-id="cd4d9-121">Objeto se serializa como un tipo System.String.</span><span class="sxs-lookup"><span data-stu-id="cd4d9-121">Object is serialized as a System.String type.</span></span>|  
|`SERIALIZATION_TYPE_SZARRAY`|<span data-ttu-id="cd4d9-122">El objeto se serializa como una sola dimensión, matriz de límite inferior cero.</span><span class="sxs-lookup"><span data-stu-id="cd4d9-122">Object is serialized as a single-dimensional, zero lower-bound array.</span></span>|  
|`SERIALIZATION_TYPE_TYPE`|<span data-ttu-id="cd4d9-123">Objeto se serializa como un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="cd4d9-123">Object is serialized as a generic type.</span></span>|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|<span data-ttu-id="cd4d9-124">Objeto se serializa como un objeto etiquetado.</span><span class="sxs-lookup"><span data-stu-id="cd4d9-124">Object is serialized as a tagged object.</span></span>|  
|`SERIALIZATION_TYPE_FIELD`|<span data-ttu-id="cd4d9-125">Objeto se serializa como un campo.</span><span class="sxs-lookup"><span data-stu-id="cd4d9-125">Object is serialized as a field.</span></span>|  
|`SERIALIZATION_TYPE_PROPERTY`|<span data-ttu-id="cd4d9-126">Objeto se serializa como una propiedad.</span><span class="sxs-lookup"><span data-stu-id="cd4d9-126">Object is serialized as a property.</span></span>|  
|`SERIALIZATION_TYPE_ENUM`|<span data-ttu-id="cd4d9-127">Objeto se serializa como una enumeración.</span><span class="sxs-lookup"><span data-stu-id="cd4d9-127">Object is serialized as an enumeration.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cd4d9-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd4d9-128">Requirements</span></span>  
 <span data-ttu-id="cd4d9-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd4d9-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd4d9-130">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="cd4d9-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="cd4d9-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd4d9-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd4d9-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd4d9-132">See also</span></span>

- [<span data-ttu-id="cd4d9-133">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="cd4d9-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
