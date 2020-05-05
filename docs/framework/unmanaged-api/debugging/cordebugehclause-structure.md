---
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
ms.openlocfilehash: a889d6ba00c4a0eb96a9923a7dbe52f3b93aaba5
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795966"
---
# <a name="cordebugehclause-structure"></a><span data-ttu-id="b9514-102">CorDebugEHClause (Estructura)</span><span class="sxs-lookup"><span data-stu-id="b9514-102">CorDebugEHClause Structure</span></span>
<span data-ttu-id="b9514-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="b9514-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b9514-104">Representa una cláusula de control de excepciones (EH) para una parte determinada de código de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="b9514-104">Represents an exception handling (EH) clause for a given piece of intermediate language (IL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9514-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9514-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="b9514-106">Members</span><span class="sxs-lookup"><span data-stu-id="b9514-106">Members</span></span>  
  
|<span data-ttu-id="b9514-107">Member</span><span class="sxs-lookup"><span data-stu-id="b9514-107">Member</span></span>|<span data-ttu-id="b9514-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b9514-108">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="b9514-109">Campo de bits que describe la información de la excepción en la cláusula EH.</span><span class="sxs-lookup"><span data-stu-id="b9514-109">A bit field that describes the exception information in the EH clause.</span></span> <span data-ttu-id="b9514-110">Para obtener más información, vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="b9514-110">For more information, see the Remarks section.</span></span>|  
|`TryOffset`|<span data-ttu-id="b9514-111">Desplazamiento, en bytes, del bloque `try` desde el comienzo del cuerpo del método.</span><span class="sxs-lookup"><span data-stu-id="b9514-111">The offset, in bytes, of the `try` block from the start of the method body.</span></span>|  
|`TryLength`|<span data-ttu-id="b9514-112">Longitud, en bytes, del bloque `try`.</span><span class="sxs-lookup"><span data-stu-id="b9514-112">The length, in bytes, of the `try` block.</span></span>|  
|`HandlerOffset`|<span data-ttu-id="b9514-113">Ubicación del controlador para este bloque `try`.</span><span class="sxs-lookup"><span data-stu-id="b9514-113">The location of the handler for this `try` block.</span></span>|  
|`HandlerLength`|<span data-ttu-id="b9514-114">Tamaño del código de controlador, en bytes.</span><span class="sxs-lookup"><span data-stu-id="b9514-114">The size of the handler code in bytes.</span></span>|  
|`ClassToken`|<span data-ttu-id="b9514-115">Token de metadatos para un controlador de excepciones basado en tipos.</span><span class="sxs-lookup"><span data-stu-id="b9514-115">The metadata token for a type-based exception handler.</span></span>|  
|`FilterOffset`|<span data-ttu-id="b9514-116">Desplazamiento, en bytes, desde el principio del cuerpo del método para un controlador de excepciones basado en filtros.</span><span class="sxs-lookup"><span data-stu-id="b9514-116">The offset, in bytes, from the start of the method body for a filter-based exception handler.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9514-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b9514-117">Remarks</span></span>  
 <span data-ttu-id="b9514-118">El método `CoreDebugEHClause` [getehclauses (](icordebugilcode-getehclauses-method.md) devuelve una matriz de valores.</span><span class="sxs-lookup"><span data-stu-id="b9514-118">An array of `CoreDebugEHClause` values is returned by the [GetEHClauses](icordebugilcode-getehclauses-method.md) method.</span></span>  
  
 <span data-ttu-id="b9514-119">La información de la cláusula EH se define mediante la especificación de CLI.</span><span class="sxs-lookup"><span data-stu-id="b9514-119">The EH clause information is defined by the CLI specification.</span></span> <span data-ttu-id="b9514-120">Para obtener más información, consulte [el estándar ECMA-355: Common Language Infrastructure (CLI), 6ª edición](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="b9514-120">For more information, see [Standard ECMA-355: Common Language Infrastructure (CLI), 6th Edition](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
 <span data-ttu-id="b9514-121">El campo `flags` puede contener las siguientes marcas.</span><span class="sxs-lookup"><span data-stu-id="b9514-121">The `flags` field can contain the following flags.</span></span> <span data-ttu-id="b9514-122">Tenga en cuenta que no están definidas en CorDebug.idl ni en CorDebug.h.</span><span class="sxs-lookup"><span data-stu-id="b9514-122">Note that they are not defined in CorDebug.idl or CorDebug.h.</span></span>  
  
|<span data-ttu-id="b9514-123">Marca</span><span class="sxs-lookup"><span data-stu-id="b9514-123">Flag</span></span>|<span data-ttu-id="b9514-124">Valor</span><span class="sxs-lookup"><span data-stu-id="b9514-124">Value</span></span>|<span data-ttu-id="b9514-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="b9514-125">Description</span></span>|  
|----------|-----------|-----------------|  
|`COR_ILEXCEPTION_CLAUSE_EXCEPTION`|<span data-ttu-id="b9514-126">0x00000000</span><span class="sxs-lookup"><span data-stu-id="b9514-126">0x00000000</span></span>|<span data-ttu-id="b9514-127">Cláusula de excepción tipada.</span><span class="sxs-lookup"><span data-stu-id="b9514-127">A typed exception clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FILTER`|<span data-ttu-id="b9514-128">0x00000001</span><span class="sxs-lookup"><span data-stu-id="b9514-128">0x00000001</span></span>|<span data-ttu-id="b9514-129">Filtro de excepción y cláusula de controlador.</span><span class="sxs-lookup"><span data-stu-id="b9514-129">An exception filter and handler clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FINALLY`|<span data-ttu-id="b9514-130">0x00000002</span><span class="sxs-lookup"><span data-stu-id="b9514-130">0x00000002</span></span>|<span data-ttu-id="b9514-131">Cláusula `finally`.</span><span class="sxs-lookup"><span data-stu-id="b9514-131">A `finally` clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FAULT`|<span data-ttu-id="b9514-132">0x00000004</span><span class="sxs-lookup"><span data-stu-id="b9514-132">0x00000004</span></span>|<span data-ttu-id="b9514-133">Cláusula fault (cláusula `finally` a la que se llama solo cuando se inicia una excepción).</span><span class="sxs-lookup"><span data-stu-id="b9514-133">A fault clause (a `finally` clause that is called only when an exception is thrown).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b9514-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9514-134">Requirements</span></span>  
 <span data-ttu-id="b9514-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9514-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9514-136">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9514-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9514-137">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9514-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9514-138">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9514-138">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9514-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9514-139">See also</span></span>

- [<span data-ttu-id="b9514-140">Método GetEHClauses</span><span class="sxs-lookup"><span data-stu-id="b9514-140">GetEHClauses Method</span></span>](icordebugilcode-getehclauses-method.md)
- [<span data-ttu-id="b9514-141">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="b9514-141">Debugging Structures</span></span>](debugging-structures.md)
