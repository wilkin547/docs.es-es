---
title: CorElementType (Enumeración)
ms.date: 03/30/2017
api_name:
- CorElementType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorElementType
helpviewer_keywords:
- CorElementType enumeration [.NET Framework metadata]
ms.assetid: c3809c8f-1737-4f0f-9442-0c01ee689871
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6057bd48ff4fe3f852f82de2bab972d95fef138c
ms.sourcegitcommit: 9ee6cd851b6e176a5811ea28ed0d5935c71950f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/09/2019
ms.locfileid: "68868567"
---
# <a name="corelementtype-enumeration"></a><span data-ttu-id="8d834-102">CorElementType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="8d834-102">CorElementType Enumeration</span></span>

<span data-ttu-id="8d834-103">Especifica un Common Language Runtime <xref:System.Type>, un modificador de tipo o información sobre un tipo en una firma de tipo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="8d834-103">Specifies a common language runtime <xref:System.Type>, a type modifier, or information about a type in a metadata type signature.</span></span>

## <a name="syntax"></a><span data-ttu-id="8d834-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d834-104">Syntax</span></span>

```cpp
typedef enum CorElementType {
    ELEMENT_TYPE_END            = 0x0,
    ELEMENT_TYPE_VOID           = 0x1,
    ELEMENT_TYPE_BOOLEAN        = 0x2,
    ELEMENT_TYPE_CHAR           = 0x3,
    ELEMENT_TYPE_I1             = 0x4,
    ELEMENT_TYPE_U1             = 0x5,
    ELEMENT_TYPE_I2             = 0x6,
    ELEMENT_TYPE_U2             = 0x7,
    ELEMENT_TYPE_I4             = 0x8,
    ELEMENT_TYPE_U4             = 0x9,
    ELEMENT_TYPE_I8             = 0xa,
    ELEMENT_TYPE_U8             = 0xb,
    ELEMENT_TYPE_R4             = 0xc,
    ELEMENT_TYPE_R8             = 0xd,
    ELEMENT_TYPE_STRING         = 0xe,

    ELEMENT_TYPE_PTR            = 0xf,
    ELEMENT_TYPE_BYREF          = 0x10,

    ELEMENT_TYPE_VALUETYPE      = 0x11,
    ELEMENT_TYPE_CLASS          = 0x12,
    ELEMENT_TYPE_VAR            = 0x13,
    ELEMENT_TYPE_ARRAY          = 0x14,
    ELEMENT_TYPE_GENERICINST    = 0x15,
    ELEMENT_TYPE_TYPEDBYREF     = 0x16,

    ELEMENT_TYPE_I              = 0x18,
    ELEMENT_TYPE_U              = 0x19,
    ELEMENT_TYPE_FNPTR          = 0x1B,
    ELEMENT_TYPE_OBJECT         = 0x1C,
    ELEMENT_TYPE_SZARRAY        = 0x1D,
    ELEMENT_TYPE_MVAR           = 0x1e,

    ELEMENT_TYPE_CMOD_REQD      = 0x1F,
    ELEMENT_TYPE_CMOD_OPT       = 0x20,

    ELEMENT_TYPE_INTERNAL       = 0x21,
    ELEMENT_TYPE_MAX            = 0x22,

    ELEMENT_TYPE_MODIFIER       = 0x40,
    ELEMENT_TYPE_SENTINEL       = 0x01 | ELEMENT_TYPE_MODIFIER,
    ELEMENT_TYPE_PINNED         = 0x05 | ELEMENT_TYPE_MODIFIER

} CorElementType;
```

## <a name="members"></a><span data-ttu-id="8d834-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="8d834-105">Members</span></span>

|<span data-ttu-id="8d834-106">Member</span><span class="sxs-lookup"><span data-stu-id="8d834-106">Member</span></span>|<span data-ttu-id="8d834-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8d834-107">Description</span></span>|
|------------|-----------------|
|`ELEMENT_TYPE_END`|<span data-ttu-id="8d834-108">Se usa internamente.</span><span class="sxs-lookup"><span data-stu-id="8d834-108">Used internally.</span></span>|
|`ELEMENT_TYPE_VOID`|<span data-ttu-id="8d834-109">Un tipo void.</span><span class="sxs-lookup"><span data-stu-id="8d834-109">A void type.</span></span>|
|`ELEMENT_TYPE_BOOLEAN`|<span data-ttu-id="8d834-110">Un tipo booleano</span><span class="sxs-lookup"><span data-stu-id="8d834-110">A Boolean type</span></span>|
|`ELEMENT_TYPE_CHAR`|<span data-ttu-id="8d834-111">Tipo de carácter.</span><span class="sxs-lookup"><span data-stu-id="8d834-111">A character type.</span></span>|
|`ELEMENT_TYPE_I1`|<span data-ttu-id="8d834-112">Entero de 1 byte con signo.</span><span class="sxs-lookup"><span data-stu-id="8d834-112">A signed 1-byte integer.</span></span>|
|`ELEMENT_TYPE_U1`|<span data-ttu-id="8d834-113">Entero de 1 bit sin signo.</span><span class="sxs-lookup"><span data-stu-id="8d834-113">An unsigned 1-byte integer.</span></span>|
|`ELEMENT_TYPE_I2`|<span data-ttu-id="8d834-114">Entero de 2 bytes con signo.</span><span class="sxs-lookup"><span data-stu-id="8d834-114">A signed 2-byte integer.</span></span>|
|`ELEMENT_TYPE_U2`|<span data-ttu-id="8d834-115">Entero de 2 bytes sin signo.</span><span class="sxs-lookup"><span data-stu-id="8d834-115">An unsigned 2-byte integer.</span></span>|
|`ELEMENT_TYPE_I4`|<span data-ttu-id="8d834-116">Entero de 4 bytes con signo.</span><span class="sxs-lookup"><span data-stu-id="8d834-116">A signed 4-byte integer.</span></span>|
|`ELEMENT_TYPE_U4`|<span data-ttu-id="8d834-117">Entero de 4 bytes sin signo.</span><span class="sxs-lookup"><span data-stu-id="8d834-117">An unsigned 4-byte integer.</span></span>|
|`ELEMENT_TYPE_I8`|<span data-ttu-id="8d834-118">Entero de 8 bytes con signo.</span><span class="sxs-lookup"><span data-stu-id="8d834-118">A signed 8-byte integer.</span></span>|
|`ELEMENT_TYPE_U8`|<span data-ttu-id="8d834-119">Entero de 8 bytes sin signo.</span><span class="sxs-lookup"><span data-stu-id="8d834-119">An unsigned 8-byte integer.</span></span>|
|`ELEMENT_TYPE_R4`|<span data-ttu-id="8d834-120">Punto flotante de 4 bytes.</span><span class="sxs-lookup"><span data-stu-id="8d834-120">A 4-byte floating point.</span></span>|
|`ELEMENT_TYPE_R8`|<span data-ttu-id="8d834-121">Punto flotante de 8 bytes.</span><span class="sxs-lookup"><span data-stu-id="8d834-121">An 8-byte floating point.</span></span>|
|`ELEMENT_TYPE_STRING`|<span data-ttu-id="8d834-122">Tipo System. String.</span><span class="sxs-lookup"><span data-stu-id="8d834-122">A System.String type.</span></span>|
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="8d834-123">Modificador de tipo de puntero.</span><span class="sxs-lookup"><span data-stu-id="8d834-123">A pointer type modifier.</span></span>|
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="8d834-124">Modificador de tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="8d834-124">A reference type modifier.</span></span>|
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="8d834-125">Modificador de tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="8d834-125">A value type modifier.</span></span>|
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="8d834-126">Modificador de tipo de clase.</span><span class="sxs-lookup"><span data-stu-id="8d834-126">A class type modifier.</span></span>|
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="8d834-127">Modificador de tipo variable de clase.</span><span class="sxs-lookup"><span data-stu-id="8d834-127">A class variable type modifier.</span></span>|
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="8d834-128">Modificador de tipo de matriz multidimensional.</span><span class="sxs-lookup"><span data-stu-id="8d834-128">A multi-dimensional array type modifier.</span></span>|
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="8d834-129">Modificador de tipo para tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="8d834-129">A type modifier for generic types.</span></span>|
|`ELEMENT_TYPE_TYPEDBYREF`|<span data-ttu-id="8d834-130">Referencia con tipo.</span><span class="sxs-lookup"><span data-stu-id="8d834-130">A typed reference.</span></span>|
|`ELEMENT_TYPE_I`|<span data-ttu-id="8d834-131">Tamaño de un entero nativo.</span><span class="sxs-lookup"><span data-stu-id="8d834-131">Size of a native integer.</span></span>|
|`ELEMENT_TYPE_U`|<span data-ttu-id="8d834-132">Tamaño de un entero nativo sin signo.</span><span class="sxs-lookup"><span data-stu-id="8d834-132">Size of an unsigned native integer.</span></span>|
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="8d834-133">Puntero a una función.</span><span class="sxs-lookup"><span data-stu-id="8d834-133">A pointer to a function.</span></span>|
|`ELEMENT_TYPE_OBJECT`|<span data-ttu-id="8d834-134">Tipo System. Object.</span><span class="sxs-lookup"><span data-stu-id="8d834-134">A System.Object type.</span></span>|
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="8d834-135">Modificador de tipo de matriz unidimensional y de límite inferior.</span><span class="sxs-lookup"><span data-stu-id="8d834-135">A single-dimensional, zero lower-bound array type modifier.</span></span>|
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="8d834-136">Modificador de tipo variable de método.</span><span class="sxs-lookup"><span data-stu-id="8d834-136">A method variable type modifier.</span></span>|
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="8d834-137">Modificador obligatorio en el lenguaje C.</span><span class="sxs-lookup"><span data-stu-id="8d834-137">A C language required modifier.</span></span>|
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="8d834-138">Modificador opcional del lenguaje C.</span><span class="sxs-lookup"><span data-stu-id="8d834-138">A C language optional modifier.</span></span>|
|`ELEMENT_TYPE_INTERNAL`|<span data-ttu-id="8d834-139">Se usa internamente.</span><span class="sxs-lookup"><span data-stu-id="8d834-139">Used internally.</span></span>|
|`ELEMENT_TYPE_MAX`|<span data-ttu-id="8d834-140">Tipo no válido.</span><span class="sxs-lookup"><span data-stu-id="8d834-140">An invalid type.</span></span>|
|`ELEMENT_TYPE_MODIFIER`|<span data-ttu-id="8d834-141">Se usa internamente.</span><span class="sxs-lookup"><span data-stu-id="8d834-141">Used internally.</span></span>|
|`ELEMENT_TYPE_SENTINEL`|<span data-ttu-id="8d834-142">Modificador de tipo que es un centinela para una lista de un número variable de parámetros.</span><span class="sxs-lookup"><span data-stu-id="8d834-142">A type modifier that is a sentinel for a list of a variable number of parameters.</span></span>|
|`ELEMENT_TYPE_PINNED`|<span data-ttu-id="8d834-143">Se usa internamente.</span><span class="sxs-lookup"><span data-stu-id="8d834-143">Used internally.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8d834-144">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8d834-144">Remarks</span></span>

<span data-ttu-id="8d834-145">Los modificadores de tipo constituyen la base para representar tipos más complejos.</span><span class="sxs-lookup"><span data-stu-id="8d834-145">The type modifiers form the basis for representing more complex types.</span></span> <span data-ttu-id="8d834-146">Un `CorElementType` valor de modificador de tipo se aplica al valor que lo sigue inmediatamente en la signatura de tipo.</span><span class="sxs-lookup"><span data-stu-id="8d834-146">A `CorElementType` type modifier value is applied to the value that immediately follows it in the type signature.</span></span> <span data-ttu-id="8d834-147">El valor que sigue al `CorElementType` valor del modificador de tipo puede `CorElementType` ser un valor de tipo simple, un token de metadatos u otro valor, como se especifica en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="8d834-147">The value that follows the `CorElementType` type modifier value can be a `CorElementType` simple type value, a metadata token, or other value, as specified in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="8d834-148">Todos los números *(número, número*de *argumentos*, *token*de metadatos, *rango*, recuento y *enlazado*) se almacenan como enteros comprimidos.</span><span class="sxs-lookup"><span data-stu-id="8d834-148">All numbers (*number*, *argument Count*, *metadata token*, *rank*, *count*, and *bound*) are stored as compressed integers.</span></span> <span data-ttu-id="8d834-149">Consulte el [estándar ECMA-335-Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=116487) en el sitio web de ECMA para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8d834-149">See [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=116487) on the ECMA Web site for details.</span></span>

|<span data-ttu-id="8d834-150">Modificador de tipo</span><span class="sxs-lookup"><span data-stu-id="8d834-150">Type modifier</span></span>|<span data-ttu-id="8d834-151">Formato</span><span class="sxs-lookup"><span data-stu-id="8d834-151">Format</span></span>|
|-------------------|------------|
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="8d834-152">ELEMENT_TYPE_PTR \< un`CorElementType` valor ></span><span class="sxs-lookup"><span data-stu-id="8d834-152">ELEMENT_TYPE_PTR \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="8d834-153">ELEMENT_TYPE_BYREF \< un`CorElementType` valor ></span><span class="sxs-lookup"><span data-stu-id="8d834-153">ELEMENT_TYPE_BYREF \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="8d834-154">ELEMENT_TYPE_VALUETYPE \< un`mdTypeDef` token de metadatos ></span><span class="sxs-lookup"><span data-stu-id="8d834-154">ELEMENT_TYPE_VALUETYPE \<an `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="8d834-155">ELEMENT_TYPE_CLASS \< un`mdTypeDef` token de metadatos ></span><span class="sxs-lookup"><span data-stu-id="8d834-155">ELEMENT_TYPE_CLASS \<an `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="8d834-156">ELEMENT_TYPE_VAR \<número ></span><span class="sxs-lookup"><span data-stu-id="8d834-156">ELEMENT_TYPE_VAR \<number></span></span>|
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="8d834-157">ELEMENT_TYPE_ARRAY \<un `CorElementType` valor > \<rango > \<count1 >\<bound1 >... countn > \<boundn> \<</span><span class="sxs-lookup"><span data-stu-id="8d834-157">ELEMENT_TYPE_ARRAY \<a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN> \<boundN></span></span>|
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="8d834-158">ELEMENT_TYPE_GENERICINST \< \< \<un `mdTypeDef` token de metadatos > recuento de argumentos > arg1 >... \<> argn</span><span class="sxs-lookup"><span data-stu-id="8d834-158">ELEMENT_TYPE_GENERICINST \<an `mdTypeDef` metadata token> \<argument Count> \<arg1> ... \<argN></span></span>|
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="8d834-159">ELEMENT_TYPE_FNPTR \<completar firma para la función, incluida la Convención de llamada ></span><span class="sxs-lookup"><span data-stu-id="8d834-159">ELEMENT_TYPE_FNPTR \<complete signature for the function, including calling convention></span></span>|
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="8d834-160">ELEMENT_TYPE_SZARRAY \< un`CorElementType` valor ></span><span class="sxs-lookup"><span data-stu-id="8d834-160">ELEMENT_TYPE_SZARRAY \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="8d834-161">ELEMENT_TYPE_MVAR \<número ></span><span class="sxs-lookup"><span data-stu-id="8d834-161">ELEMENT_TYPE_MVAR \<number></span></span>|
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="8d834-162">ELEMENT_TYPE_\< `mdTypeDef` un `mdTypeRef` token de metadatos o ></span><span class="sxs-lookup"><span data-stu-id="8d834-162">ELEMENT_TYPE_\<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="8d834-163">E_T_CMOD_OPT \< `mdTypeDef` un `mdTypeRef` token de metadatos o ></span><span class="sxs-lookup"><span data-stu-id="8d834-163">E_T_CMOD_OPT \<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|

## <a name="requirements"></a><span data-ttu-id="8d834-164">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d834-164">Requirements</span></span>

<span data-ttu-id="8d834-165">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d834-165">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="8d834-166">**Encabezado**: CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="8d834-166">**Header:** CorHdr.h</span></span>

<span data-ttu-id="8d834-167">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d834-167">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8d834-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d834-168">See also</span></span>

- [<span data-ttu-id="8d834-169">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="8d834-169">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
