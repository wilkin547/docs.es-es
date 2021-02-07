---
description: 'Más información sobre: enumeración Corthreadsafetyoptions ('
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
ms.openlocfilehash: 7915bcf5e7b71fa84ea83642467c1600cd38712d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707324"
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="086d7-103">CorThreadSafetyOptions (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="086d7-103">CorThreadSafetyOptions Enumeration</span></span>

<span data-ttu-id="086d7-104">Especifica marcas para seleccionar opciones de seguridad para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="086d7-104">Specifies flags to select options for thread safety.</span></span>

## <a name="syntax"></a><span data-ttu-id="086d7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="086d7-105">Syntax</span></span>

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a><span data-ttu-id="086d7-106">Members</span><span class="sxs-lookup"><span data-stu-id="086d7-106">Members</span></span>

|<span data-ttu-id="086d7-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="086d7-107">Member</span></span>|<span data-ttu-id="086d7-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="086d7-108">Description</span></span>|
|------------|-----------------|
|`MDThreadSafetyDefault`|<span data-ttu-id="086d7-109">Valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="086d7-109">Default value.</span></span> <span data-ttu-id="086d7-110">Igual a `MDThreadSafetyOff`.</span><span class="sxs-lookup"><span data-stu-id="086d7-110">Same as `MDThreadSafetyOff`.</span></span>|
|`MDThreadSafetyOff`|<span data-ttu-id="086d7-111">Indica que no se puede establecer un bloqueo de lector/escritor.</span><span class="sxs-lookup"><span data-stu-id="086d7-111">Indicates that a reader/writer lock cannot be set.</span></span>|
|`MDThreadSafetyOn`|<span data-ttu-id="086d7-112">Indica que se puede establecer un bloqueo de lectura/escritura.</span><span class="sxs-lookup"><span data-stu-id="086d7-112">Indicates that a reader/writer lock can be set.</span></span>|

## <a name="requirements"></a><span data-ttu-id="086d7-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="086d7-113">Requirements</span></span>

<span data-ttu-id="086d7-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="086d7-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="086d7-115">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="086d7-115">**Header:** CorHdr.h</span></span>

<span data-ttu-id="086d7-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="086d7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="086d7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="086d7-117">See also</span></span>

- [<span data-ttu-id="086d7-118">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="086d7-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
