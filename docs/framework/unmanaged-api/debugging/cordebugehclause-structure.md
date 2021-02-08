---
description: 'Más información acerca de: estructura Cordebugehclause ('
title: CorDebugEHClause (Estructura)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugEHClause
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0e350a1b-6997-46d0-bfc5-962a5011ef43
topic_type:
- apiref
ms.openlocfilehash: ecb00e2a110719ab82de32fb1f1c861e2033a528
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801675"
---
# <a name="cordebugehclause-structure"></a><span data-ttu-id="0013d-103">CorDebugEHClause (Estructura)</span><span class="sxs-lookup"><span data-stu-id="0013d-103">CorDebugEHClause Structure</span></span>

<span data-ttu-id="0013d-104">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="0013d-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="0013d-105">Representa una cláusula de control de excepciones (EH) para una parte determinada de código de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="0013d-105">Represents an exception handling (EH) clause for a given piece of intermediate language (IL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0013d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0013d-106">Syntax</span></span>  
  
```cpp
typedef struct _CorDebugEHClause {  
   ULONG32 Flags;  
   ULONG32 TryOffset;  
   ULONG32 TryLength;  
   ULONG32 HandlerOffset;  
   ULONG32 HandlerLength;  
   ULONG32 ClassToken;  
   ULONG32 FilterOffset;  
} CorDebugEHClause;  
```  
  
## <a name="members"></a><span data-ttu-id="0013d-107">Members</span><span class="sxs-lookup"><span data-stu-id="0013d-107">Members</span></span>  
  
|<span data-ttu-id="0013d-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="0013d-108">Member</span></span>|<span data-ttu-id="0013d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="0013d-109">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="0013d-110">Campo de bits que describe la información de la excepción en la cláusula EH.</span><span class="sxs-lookup"><span data-stu-id="0013d-110">A bit field that describes the exception information in the EH clause.</span></span> <span data-ttu-id="0013d-111">Para obtener más información, vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="0013d-111">For more information, see the Remarks section.</span></span>|  
|`TryOffset`|<span data-ttu-id="0013d-112">Desplazamiento, en bytes, del bloque `try` desde el comienzo del cuerpo del método.</span><span class="sxs-lookup"><span data-stu-id="0013d-112">The offset, in bytes, of the `try` block from the start of the method body.</span></span>|  
|`TryLength`|<span data-ttu-id="0013d-113">Longitud, en bytes, del bloque `try`.</span><span class="sxs-lookup"><span data-stu-id="0013d-113">The length, in bytes, of the `try` block.</span></span>|  
|`HandlerOffset`|<span data-ttu-id="0013d-114">Ubicación del controlador para este bloque `try`.</span><span class="sxs-lookup"><span data-stu-id="0013d-114">The location of the handler for this `try` block.</span></span>|  
|`HandlerLength`|<span data-ttu-id="0013d-115">Tamaño del código de controlador, en bytes.</span><span class="sxs-lookup"><span data-stu-id="0013d-115">The size of the handler code in bytes.</span></span>|  
|`ClassToken`|<span data-ttu-id="0013d-116">Token de metadatos para un controlador de excepciones basado en tipos.</span><span class="sxs-lookup"><span data-stu-id="0013d-116">The metadata token for a type-based exception handler.</span></span>|  
|`FilterOffset`|<span data-ttu-id="0013d-117">Desplazamiento, en bytes, desde el principio del cuerpo del método para un controlador de excepciones basado en filtros.</span><span class="sxs-lookup"><span data-stu-id="0013d-117">The offset, in bytes, from the start of the method body for a filter-based exception handler.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0013d-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0013d-118">Remarks</span></span>  

 <span data-ttu-id="0013d-119">`CoreDebugEHClause`El método [getehclauses (](icordebugilcode-getehclauses-method.md) devuelve una matriz de valores.</span><span class="sxs-lookup"><span data-stu-id="0013d-119">An array of `CoreDebugEHClause` values is returned by the [GetEHClauses](icordebugilcode-getehclauses-method.md) method.</span></span>  
  
 <span data-ttu-id="0013d-120">La información de la cláusula EH se define mediante la especificación de CLI.</span><span class="sxs-lookup"><span data-stu-id="0013d-120">The EH clause information is defined by the CLI specification.</span></span> <span data-ttu-id="0013d-121">Para obtener más información, consulte [el estándar ECMA-355: Common Language Infrastructure (CLI), 6ª edición](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="0013d-121">For more information, see [Standard ECMA-355: Common Language Infrastructure (CLI), 6th Edition](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
 <span data-ttu-id="0013d-122">El campo `flags` puede contener las siguientes marcas.</span><span class="sxs-lookup"><span data-stu-id="0013d-122">The `flags` field can contain the following flags.</span></span> <span data-ttu-id="0013d-123">Tenga en cuenta que no están definidas en CorDebug.idl ni en CorDebug.h.</span><span class="sxs-lookup"><span data-stu-id="0013d-123">Note that they are not defined in CorDebug.idl or CorDebug.h.</span></span>  
  
|<span data-ttu-id="0013d-124">Marca</span><span class="sxs-lookup"><span data-stu-id="0013d-124">Flag</span></span>|<span data-ttu-id="0013d-125">Value</span><span class="sxs-lookup"><span data-stu-id="0013d-125">Value</span></span>|<span data-ttu-id="0013d-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="0013d-126">Description</span></span>|  
|----------|-----------|-----------------|  
|`COR_ILEXCEPTION_CLAUSE_EXCEPTION`|<span data-ttu-id="0013d-127">0x00000000</span><span class="sxs-lookup"><span data-stu-id="0013d-127">0x00000000</span></span>|<span data-ttu-id="0013d-128">Cláusula de excepción tipada.</span><span class="sxs-lookup"><span data-stu-id="0013d-128">A typed exception clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FILTER`|<span data-ttu-id="0013d-129">0x00000001</span><span class="sxs-lookup"><span data-stu-id="0013d-129">0x00000001</span></span>|<span data-ttu-id="0013d-130">Filtro de excepción y cláusula de controlador.</span><span class="sxs-lookup"><span data-stu-id="0013d-130">An exception filter and handler clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FINALLY`|<span data-ttu-id="0013d-131">0x00000002</span><span class="sxs-lookup"><span data-stu-id="0013d-131">0x00000002</span></span>|<span data-ttu-id="0013d-132">Cláusula `finally`.</span><span class="sxs-lookup"><span data-stu-id="0013d-132">A `finally` clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FAULT`|<span data-ttu-id="0013d-133">0x00000004</span><span class="sxs-lookup"><span data-stu-id="0013d-133">0x00000004</span></span>|<span data-ttu-id="0013d-134">Cláusula fault (cláusula `finally` a la que se llama solo cuando se inicia una excepción).</span><span class="sxs-lookup"><span data-stu-id="0013d-134">A fault clause (a `finally` clause that is called only when an exception is thrown).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0013d-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0013d-135">Requirements</span></span>  

 <span data-ttu-id="0013d-136">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0013d-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0013d-137">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0013d-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0013d-138">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0013d-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0013d-139">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0013d-139">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0013d-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="0013d-140">See also</span></span>

- [<span data-ttu-id="0013d-141">Método GetEHClauses</span><span class="sxs-lookup"><span data-stu-id="0013d-141">GetEHClauses Method</span></span>](icordebugilcode-getehclauses-method.md)
- [<span data-ttu-id="0013d-142">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="0013d-142">Debugging Structures</span></span>](debugging-structures.md)
