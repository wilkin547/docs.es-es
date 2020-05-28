---
title: CorThreadSafetyOptions (Enumeración)
ms.date: 03/30/2017
api_name:
- CorThreadSafetyOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorThreadSafetyOptions
helpviewer_keywords:
- CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type:
- apiref
ms.openlocfilehash: 8c0527a7bc3cde7344bf809dc8e6f5a3fac04852
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007512"
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="a9914-102">CorThreadSafetyOptions (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a9914-102">CorThreadSafetyOptions Enumeration</span></span>

<span data-ttu-id="a9914-103">Especifica marcas para seleccionar opciones de seguridad para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="a9914-103">Specifies flags to select options for thread safety.</span></span>

## <a name="syntax"></a><span data-ttu-id="a9914-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9914-104">Syntax</span></span>

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a><span data-ttu-id="a9914-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a9914-105">Members</span></span>

|<span data-ttu-id="a9914-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a9914-106">Member</span></span>|<span data-ttu-id="a9914-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9914-107">Description</span></span>|
|------------|-----------------|
|`MDThreadSafetyDefault`|<span data-ttu-id="a9914-108">Valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a9914-108">Default value.</span></span> <span data-ttu-id="a9914-109">Igual a `MDThreadSafetyOff`.</span><span class="sxs-lookup"><span data-stu-id="a9914-109">Same as `MDThreadSafetyOff`.</span></span>|
|`MDThreadSafetyOff`|<span data-ttu-id="a9914-110">Indica que no se puede establecer un bloqueo de lector/escritor.</span><span class="sxs-lookup"><span data-stu-id="a9914-110">Indicates that a reader/writer lock cannot be set.</span></span>|
|`MDThreadSafetyOn`|<span data-ttu-id="a9914-111">Indica que se puede establecer un bloqueo de lectura/escritura.</span><span class="sxs-lookup"><span data-stu-id="a9914-111">Indicates that a reader/writer lock can be set.</span></span>|

## <a name="requirements"></a><span data-ttu-id="a9914-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9914-112">Requirements</span></span>

<span data-ttu-id="a9914-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9914-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="a9914-114">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="a9914-114">**Header:** CorHdr.h</span></span>

<span data-ttu-id="a9914-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9914-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a9914-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9914-116">See also</span></span>

- [<span data-ttu-id="a9914-117">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="a9914-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
