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
ms.openlocfilehash: 25fb3278e576ebe4a538379918e868b2e5f87911
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007876"
---
# <a name="corelementtype-enumeration"></a><span data-ttu-id="f353a-102">CorElementType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f353a-102">CorElementType Enumeration</span></span>

<span data-ttu-id="f353a-103">Especifica un Common Language Runtime <xref:System.Type> , un modificador de tipo o información sobre un tipo en una firma de tipo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="f353a-103">Specifies a common language runtime <xref:System.Type>, a type modifier, or information about a type in a metadata type signature.</span></span>

## <a name="syntax"></a><span data-ttu-id="f353a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f353a-104">Syntax</span></span>

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

## <a name="members"></a><span data-ttu-id="f353a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="f353a-105">Members</span></span>

|<span data-ttu-id="f353a-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="f353a-106">Member</span></span>|<span data-ttu-id="f353a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f353a-107">Description</span></span>|
|------------|-----------------|
|`ELEMENT_TYPE_END`|<span data-ttu-id="f353a-108">Utilizado de forma interna.</span><span class="sxs-lookup"><span data-stu-id="f353a-108">Used internally.</span></span>|
|`ELEMENT_TYPE_VOID`|<span data-ttu-id="f353a-109">Un tipo void.</span><span class="sxs-lookup"><span data-stu-id="f353a-109">A void type.</span></span>|
|`ELEMENT_TYPE_BOOLEAN`|<span data-ttu-id="f353a-110">Un tipo booleano</span><span class="sxs-lookup"><span data-stu-id="f353a-110">A Boolean type</span></span>|
|`ELEMENT_TYPE_CHAR`|<span data-ttu-id="f353a-111">Tipo de carácter.</span><span class="sxs-lookup"><span data-stu-id="f353a-111">A character type.</span></span>|
|`ELEMENT_TYPE_I1`|<span data-ttu-id="f353a-112">Entero de 1 byte con signo.</span><span class="sxs-lookup"><span data-stu-id="f353a-112">A signed 1-byte integer.</span></span>|
|`ELEMENT_TYPE_U1`|<span data-ttu-id="f353a-113">Entero de 1 bit sin signo.</span><span class="sxs-lookup"><span data-stu-id="f353a-113">An unsigned 1-byte integer.</span></span>|
|`ELEMENT_TYPE_I2`|<span data-ttu-id="f353a-114">Entero de 2 bytes con signo.</span><span class="sxs-lookup"><span data-stu-id="f353a-114">A signed 2-byte integer.</span></span>|
|`ELEMENT_TYPE_U2`|<span data-ttu-id="f353a-115">Entero de 2 bytes sin signo.</span><span class="sxs-lookup"><span data-stu-id="f353a-115">An unsigned 2-byte integer.</span></span>|
|`ELEMENT_TYPE_I4`|<span data-ttu-id="f353a-116">Entero de 4 bytes con signo.</span><span class="sxs-lookup"><span data-stu-id="f353a-116">A signed 4-byte integer.</span></span>|
|`ELEMENT_TYPE_U4`|<span data-ttu-id="f353a-117">Entero de 4 bytes sin signo.</span><span class="sxs-lookup"><span data-stu-id="f353a-117">An unsigned 4-byte integer.</span></span>|
|`ELEMENT_TYPE_I8`|<span data-ttu-id="f353a-118">Entero de 8 bytes con signo.</span><span class="sxs-lookup"><span data-stu-id="f353a-118">A signed 8-byte integer.</span></span>|
|`ELEMENT_TYPE_U8`|<span data-ttu-id="f353a-119">Entero de 8 bytes sin signo.</span><span class="sxs-lookup"><span data-stu-id="f353a-119">An unsigned 8-byte integer.</span></span>|
|`ELEMENT_TYPE_R4`|<span data-ttu-id="f353a-120">Punto flotante de 4 bytes.</span><span class="sxs-lookup"><span data-stu-id="f353a-120">A 4-byte floating point.</span></span>|
|`ELEMENT_TYPE_R8`|<span data-ttu-id="f353a-121">Punto flotante de 8 bytes.</span><span class="sxs-lookup"><span data-stu-id="f353a-121">An 8-byte floating point.</span></span>|
|`ELEMENT_TYPE_STRING`|<span data-ttu-id="f353a-122">Tipo System. String.</span><span class="sxs-lookup"><span data-stu-id="f353a-122">A System.String type.</span></span>|
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="f353a-123">Modificador de tipo de puntero.</span><span class="sxs-lookup"><span data-stu-id="f353a-123">A pointer type modifier.</span></span>|
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="f353a-124">Modificador de tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="f353a-124">A reference type modifier.</span></span>|
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="f353a-125">Modificador de tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="f353a-125">A value type modifier.</span></span>|
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="f353a-126">Modificador de tipo de clase.</span><span class="sxs-lookup"><span data-stu-id="f353a-126">A class type modifier.</span></span>|
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="f353a-127">Modificador de tipo variable de clase.</span><span class="sxs-lookup"><span data-stu-id="f353a-127">A class variable type modifier.</span></span>|
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="f353a-128">Modificador de tipo de matriz multidimensional.</span><span class="sxs-lookup"><span data-stu-id="f353a-128">A multi-dimensional array type modifier.</span></span>|
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="f353a-129">Modificador de tipo para tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="f353a-129">A type modifier for generic types.</span></span>|
|`ELEMENT_TYPE_TYPEDBYREF`|<span data-ttu-id="f353a-130">Referencia con tipo.</span><span class="sxs-lookup"><span data-stu-id="f353a-130">A typed reference.</span></span>|
|`ELEMENT_TYPE_I`|<span data-ttu-id="f353a-131">Tamaño de un entero nativo.</span><span class="sxs-lookup"><span data-stu-id="f353a-131">Size of a native integer.</span></span>|
|`ELEMENT_TYPE_U`|<span data-ttu-id="f353a-132">Tamaño de un entero nativo sin signo.</span><span class="sxs-lookup"><span data-stu-id="f353a-132">Size of an unsigned native integer.</span></span>|
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="f353a-133">Puntero a una función.</span><span class="sxs-lookup"><span data-stu-id="f353a-133">A pointer to a function.</span></span>|
|`ELEMENT_TYPE_OBJECT`|<span data-ttu-id="f353a-134">Tipo System. Object.</span><span class="sxs-lookup"><span data-stu-id="f353a-134">A System.Object type.</span></span>|
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="f353a-135">Modificador de tipo de matriz unidimensional y de límite inferior.</span><span class="sxs-lookup"><span data-stu-id="f353a-135">A single-dimensional, zero lower-bound array type modifier.</span></span>|
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="f353a-136">Modificador de tipo variable de método.</span><span class="sxs-lookup"><span data-stu-id="f353a-136">A method variable type modifier.</span></span>|
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="f353a-137">Modificador obligatorio en el lenguaje C.</span><span class="sxs-lookup"><span data-stu-id="f353a-137">A C language required modifier.</span></span>|
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="f353a-138">Modificador opcional del lenguaje C.</span><span class="sxs-lookup"><span data-stu-id="f353a-138">A C language optional modifier.</span></span>|
|`ELEMENT_TYPE_INTERNAL`|<span data-ttu-id="f353a-139">Utilizado de forma interna.</span><span class="sxs-lookup"><span data-stu-id="f353a-139">Used internally.</span></span>|
|`ELEMENT_TYPE_MAX`|<span data-ttu-id="f353a-140">Tipo no válido.</span><span class="sxs-lookup"><span data-stu-id="f353a-140">An invalid type.</span></span>|
|`ELEMENT_TYPE_MODIFIER`|<span data-ttu-id="f353a-141">Utilizado de forma interna.</span><span class="sxs-lookup"><span data-stu-id="f353a-141">Used internally.</span></span>|
|`ELEMENT_TYPE_SENTINEL`|<span data-ttu-id="f353a-142">Modificador de tipo que es un centinela para una lista de un número variable de parámetros.</span><span class="sxs-lookup"><span data-stu-id="f353a-142">A type modifier that is a sentinel for a list of a variable number of parameters.</span></span>|
|`ELEMENT_TYPE_PINNED`|<span data-ttu-id="f353a-143">Utilizado de forma interna.</span><span class="sxs-lookup"><span data-stu-id="f353a-143">Used internally.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f353a-144">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f353a-144">Remarks</span></span>

<span data-ttu-id="f353a-145">Los modificadores de tipo constituyen la base para representar tipos más complejos.</span><span class="sxs-lookup"><span data-stu-id="f353a-145">The type modifiers form the basis for representing more complex types.</span></span> <span data-ttu-id="f353a-146">Un `CorElementType` valor de modificador de tipo se aplica al valor que lo sigue inmediatamente en la signatura de tipo.</span><span class="sxs-lookup"><span data-stu-id="f353a-146">A `CorElementType` type modifier value is applied to the value that immediately follows it in the type signature.</span></span> <span data-ttu-id="f353a-147">El valor que sigue al `CorElementType` valor del modificador de tipo puede ser un `CorElementType` valor de tipo simple, un token de metadatos u otro valor, como se especifica en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f353a-147">The value that follows the `CorElementType` type modifier value can be a `CorElementType` simple type value, a metadata token, or other value, as specified in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="f353a-148">Todos los números *(número, número*de *argumentos*, *token de metadatos*, *rango*, *recuento*y *enlazado*) se almacenan como enteros comprimidos.</span><span class="sxs-lookup"><span data-stu-id="f353a-148">All numbers (*number*, *argument Count*, *metadata token*, *rank*, *count*, and *bound*) are stored as compressed integers.</span></span> <span data-ttu-id="f353a-149">Consulte el [estándar ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm) en el sitio web de ECMA para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f353a-149">See [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm) on the ECMA Web site for details.</span></span>

|<span data-ttu-id="f353a-150">Modificador de tipo</span><span class="sxs-lookup"><span data-stu-id="f353a-150">Type modifier</span></span>|<span data-ttu-id="f353a-151">Formato</span><span class="sxs-lookup"><span data-stu-id="f353a-151">Format</span></span>|
|-------------------|------------|
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="f353a-152">ELEMENT_TYPE_PTR\<a `CorElementType` value></span><span class="sxs-lookup"><span data-stu-id="f353a-152">ELEMENT_TYPE_PTR \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="f353a-153">ELEMENT_TYPE_BYREF\<a `CorElementType` value></span><span class="sxs-lookup"><span data-stu-id="f353a-153">ELEMENT_TYPE_BYREF \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="f353a-154">ELEMENT_TYPE_VALUETYPE\<an `mdTypeDef` metadata token></span><span class="sxs-lookup"><span data-stu-id="f353a-154">ELEMENT_TYPE_VALUETYPE \<an `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="f353a-155">ELEMENT_TYPE_CLASS\<an `mdTypeDef` metadata token></span><span class="sxs-lookup"><span data-stu-id="f353a-155">ELEMENT_TYPE_CLASS \<an `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="f353a-156">ELEMENT_TYPE_VAR\<number></span><span class="sxs-lookup"><span data-stu-id="f353a-156">ELEMENT_TYPE_VAR \<number></span></span>|
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="f353a-157">ELEMENT_TYPE_ARRAY \<a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN>\<boundN></span><span class="sxs-lookup"><span data-stu-id="f353a-157">ELEMENT_TYPE_ARRAY \<a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN> \<boundN></span></span>|
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="f353a-158">ELEMENT_TYPE_GENERICINST \<an `mdTypeDef` metadata token> \<argument Count> \<arg1> ...\<argN></span><span class="sxs-lookup"><span data-stu-id="f353a-158">ELEMENT_TYPE_GENERICINST \<an `mdTypeDef` metadata token> \<argument Count> \<arg1> ... \<argN></span></span>|
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="f353a-159">ELEMENT_TYPE_FNPTR\<complete signature for the function, including calling convention></span><span class="sxs-lookup"><span data-stu-id="f353a-159">ELEMENT_TYPE_FNPTR \<complete signature for the function, including calling convention></span></span>|
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="f353a-160">ELEMENT_TYPE_SZARRAY\<a `CorElementType` value></span><span class="sxs-lookup"><span data-stu-id="f353a-160">ELEMENT_TYPE_SZARRAY \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="f353a-161">ELEMENT_TYPE_MVAR\<number></span><span class="sxs-lookup"><span data-stu-id="f353a-161">ELEMENT_TYPE_MVAR \<number></span></span>|
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="f353a-162">ELEMENT_TYPE_\<a `mdTypeRef` or `mdTypeDef` metadata token></span><span class="sxs-lookup"><span data-stu-id="f353a-162">ELEMENT_TYPE_\<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="f353a-163">E_T_CMOD_OPT\<a `mdTypeRef` or `mdTypeDef` metadata token></span><span class="sxs-lookup"><span data-stu-id="f353a-163">E_T_CMOD_OPT \<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|

## <a name="requirements"></a><span data-ttu-id="f353a-164">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f353a-164">Requirements</span></span>

<span data-ttu-id="f353a-165">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f353a-165">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="f353a-166">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="f353a-166">**Header:** CorHdr.h</span></span>

<span data-ttu-id="f353a-167">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f353a-167">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f353a-168">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f353a-168">See also</span></span>

- [<span data-ttu-id="f353a-169">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="f353a-169">Metadata Enumerations</span></span>](metadata-enumerations.md)
