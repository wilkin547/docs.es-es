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
ms.openlocfilehash: c8b3f338659e2784db8deca3e1776e7926c30c32
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506089"
---
# <a name="clrdatasourcetype-enumeration"></a><span data-ttu-id="58d38-102">Enumeración CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="58d38-102">CLRDataSourceType Enumeration</span></span>

<span data-ttu-id="58d38-103">Proporciona valores que son usados por la estructura CLRDATA_IL_ADDRESS_MAP.</span><span class="sxs-lookup"><span data-stu-id="58d38-103">Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="58d38-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58d38-104">Syntax</span></span>

```
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a><span data-ttu-id="58d38-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="58d38-105">Members</span></span>

| <span data-ttu-id="58d38-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="58d38-106">Member</span></span>                        | <span data-ttu-id="58d38-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="58d38-107">Description</span></span>                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | <span data-ttu-id="58d38-108">Para indicar que se aplica nada más</span><span class="sxs-lookup"><span data-stu-id="58d38-108">To indicate that nothing else applies</span></span> |

## <a name="remarks"></a><span data-ttu-id="58d38-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="58d38-109">Remarks</span></span>

<span data-ttu-id="58d38-110">Esta enumeración reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="58d38-110">This enumeration lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="58d38-111">Para ello, definir una enumeración definida anteriormente en el código.</span><span class="sxs-lookup"><span data-stu-id="58d38-111">To use it, define an enumeration as defined above in your code.</span></span> <span data-ttu-id="58d38-112">Esto también es un alias para `CLRDATA_ENUM` como se mencionó en [tipos de datos comunes](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span><span class="sxs-lookup"><span data-stu-id="58d38-112">This is also aliased to `CLRDATA_ENUM` as mentioned in [Common Data Types](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="58d38-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58d38-113">Requirements</span></span>

<span data-ttu-id="58d38-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58d38-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="58d38-115">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="58d38-115">**Header:** None</span></span>  
<span data-ttu-id="58d38-116">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="58d38-116">**Library:** None</span></span>  
<span data-ttu-id="58d38-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="58d38-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="58d38-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="58d38-118">See also</span></span>

- [<span data-ttu-id="58d38-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="58d38-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="58d38-120">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="58d38-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
