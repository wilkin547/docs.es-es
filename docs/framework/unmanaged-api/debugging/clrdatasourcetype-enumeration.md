---
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
ms.openlocfilehash: 7ace405e2624f15b1cdb6d383222ae87c93289bb
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274095"
---
# <a name="clrdatasourcetype-enumeration"></a><span data-ttu-id="d007f-102">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="d007f-102">CLRDataSourceType Enumeration</span></span>

<span data-ttu-id="d007f-103">Proporciona valores que se usan en la estructura CLRDATA_IL_ADDRESS_MAP.</span><span class="sxs-lookup"><span data-stu-id="d007f-103">Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="d007f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d007f-104">Syntax</span></span>

```cpp
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a><span data-ttu-id="d007f-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="d007f-105">Members</span></span>

| <span data-ttu-id="d007f-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="d007f-106">Member</span></span>                        | <span data-ttu-id="d007f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d007f-107">Description</span></span>                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | <span data-ttu-id="d007f-108">Para indicar que no se aplica nada más</span><span class="sxs-lookup"><span data-stu-id="d007f-108">To indicate that nothing else applies</span></span> |

## <a name="remarks"></a><span data-ttu-id="d007f-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d007f-109">Remarks</span></span>

<span data-ttu-id="d007f-110">Esta enumeración reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="d007f-110">This enumeration lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="d007f-111">Para usarlo, defina una enumeración tal y como se definió anteriormente en el código.</span><span class="sxs-lookup"><span data-stu-id="d007f-111">To use it, define an enumeration as defined above in your code.</span></span> <span data-ttu-id="d007f-112">También se puede aplicar un alias `CLRDATA_ENUM` a como se mencionó en [tipos de datos comunes](../common-data-types-unmanaged-api-reference.md).</span><span class="sxs-lookup"><span data-stu-id="d007f-112">This is also aliased to `CLRDATA_ENUM` as mentioned in [Common Data Types](../common-data-types-unmanaged-api-reference.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="d007f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d007f-113">Requirements</span></span>

<span data-ttu-id="d007f-114">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d007f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="d007f-115">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="d007f-115">**Header:** None</span></span>  
<span data-ttu-id="d007f-116">**Biblioteca** Ninguna</span><span class="sxs-lookup"><span data-stu-id="d007f-116">**Library:** None</span></span>  
<span data-ttu-id="d007f-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d007f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d007f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d007f-118">See also</span></span>

- [<span data-ttu-id="d007f-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="d007f-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="d007f-120">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="d007f-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
