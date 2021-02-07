---
description: 'Más información sobre: enumeración CLRDataSourceType'
title: Enumeración CLRDataSourceType
ms.date: 01/16/2019
api.name:
- CLRDataSourceType Enumeration
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDataSourceType Enumeration
helpviewer.keywords:
- CLRDataSourceType Enumeration [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 06590e21aa4cdf6e89977a79da36a413d5ff4f1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747247"
---
# <a name="clrdatasourcetype-enumeration"></a><span data-ttu-id="b33c5-103">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="b33c5-103">CLRDataSourceType Enumeration</span></span>

<span data-ttu-id="b33c5-104">Proporciona valores utilizados por la estructura de CLRDATA_IL_ADDRESS_MAP.</span><span class="sxs-lookup"><span data-stu-id="b33c5-104">Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b33c5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b33c5-105">Syntax</span></span>

```cpp
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a><span data-ttu-id="b33c5-106">Members</span><span class="sxs-lookup"><span data-stu-id="b33c5-106">Members</span></span>

| <span data-ttu-id="b33c5-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="b33c5-107">Member</span></span>                        | <span data-ttu-id="b33c5-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b33c5-108">Description</span></span>                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | <span data-ttu-id="b33c5-109">Para indicar que no se aplica nada más</span><span class="sxs-lookup"><span data-stu-id="b33c5-109">To indicate that nothing else applies</span></span> |

## <a name="remarks"></a><span data-ttu-id="b33c5-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b33c5-110">Remarks</span></span>

<span data-ttu-id="b33c5-111">Esta enumeración reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="b33c5-111">This enumeration lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="b33c5-112">Para usarlo, defina una enumeración tal y como se definió anteriormente en el código.</span><span class="sxs-lookup"><span data-stu-id="b33c5-112">To use it, define an enumeration as defined above in your code.</span></span> <span data-ttu-id="b33c5-113">También se puede aplicar un alias a `CLRDATA_ENUM` como se mencionó en [tipos de datos comunes](../common-data-types-unmanaged-api-reference.md).</span><span class="sxs-lookup"><span data-stu-id="b33c5-113">This is also aliased to `CLRDATA_ENUM` as mentioned in [Common Data Types](../common-data-types-unmanaged-api-reference.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="b33c5-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b33c5-114">Requirements</span></span>

<span data-ttu-id="b33c5-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b33c5-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b33c5-116">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="b33c5-116">**Header:** None</span></span>  
<span data-ttu-id="b33c5-117">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="b33c5-117">**Library:** None</span></span>  
<span data-ttu-id="b33c5-118">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b33c5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b33c5-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b33c5-119">See also</span></span>

- [<span data-ttu-id="b33c5-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="b33c5-120">Debugging</span></span>](index.md)
- [<span data-ttu-id="b33c5-121">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="b33c5-121">Debugging Enumerations</span></span>](debugging-enumerations.md)
