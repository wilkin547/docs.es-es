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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d71d2a5b3007d4e877900443af426a9643b29125
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045232"
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="9df04-102">CorThreadSafetyOptions (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="9df04-102">CorThreadSafetyOptions Enumeration</span></span>

<span data-ttu-id="9df04-103">Especifica marcas para seleccionar opciones de seguridad para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="9df04-103">Specifies flags to select options for thread safety.</span></span>

## <a name="syntax"></a><span data-ttu-id="9df04-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9df04-104">Syntax</span></span>

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a><span data-ttu-id="9df04-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9df04-105">Members</span></span>

|<span data-ttu-id="9df04-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9df04-106">Member</span></span>|<span data-ttu-id="9df04-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9df04-107">Description</span></span>|
|------------|-----------------|
|`MDThreadSafetyDefault`|<span data-ttu-id="9df04-108">Valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9df04-108">Default value.</span></span> <span data-ttu-id="9df04-109">Igual a `MDThreadSafetyOff`.</span><span class="sxs-lookup"><span data-stu-id="9df04-109">Same as `MDThreadSafetyOff`.</span></span>|
|`MDThreadSafetyOff`|<span data-ttu-id="9df04-110">Indica que no se puede establecer un bloqueo de lector/escritor.</span><span class="sxs-lookup"><span data-stu-id="9df04-110">Indicates that a reader/writer lock cannot be set.</span></span>|
|`MDThreadSafetyOn`|<span data-ttu-id="9df04-111">Indica que se puede establecer un bloqueo de lector/escritor.</span><span class="sxs-lookup"><span data-stu-id="9df04-111">Indicates that a reader/writer lock can be set.</span></span>|

## <a name="requirements"></a><span data-ttu-id="9df04-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9df04-112">Requirements</span></span>

<span data-ttu-id="9df04-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9df04-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="9df04-114">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="9df04-114">**Header:** CorHdr.h</span></span>

<span data-ttu-id="9df04-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9df04-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="9df04-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9df04-116">See also</span></span>

- [<span data-ttu-id="9df04-117">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="9df04-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
