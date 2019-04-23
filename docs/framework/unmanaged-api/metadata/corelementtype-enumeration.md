---
title: CorElementType (enumeración1)
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
ms.openlocfilehash: 581c5517144dbc94e16acb777b5c272b8390b212
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091140"
---
# <a name="corelementtype-enumeration1"></a><span data-ttu-id="f7ec2-102">CorElementType (enumeración1)</span><span class="sxs-lookup"><span data-stu-id="f7ec2-102">CorElementType Enumeration1</span></span>
<span data-ttu-id="f7ec2-103">Especifica un common language runtime <xref:System.Type>, un modificador de tipo o información sobre un tipo en una signatura de tipo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-103">Specifies a common language runtime <xref:System.Type>, a type modifier, or information about a type in a metadata type signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7ec2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7ec2-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="f7ec2-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="f7ec2-105">Members</span></span>  
  
|<span data-ttu-id="f7ec2-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="f7ec2-106">Member</span></span>|<span data-ttu-id="f7ec2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7ec2-107">Description</span></span>|  
|------------|-----------------|  
|`ELEMENT_TYPE_END`|<span data-ttu-id="f7ec2-108">Lo utiliza internamente.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-108">Used internally.</span></span>|  
|`ELEMENT_TYPE_VOID`|<span data-ttu-id="f7ec2-109">Un tipo void.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-109">A void type.</span></span>|  
|`ELEMENT_TYPE_BOOLEAN`|<span data-ttu-id="f7ec2-110">Un tipo booleano</span><span class="sxs-lookup"><span data-stu-id="f7ec2-110">A Boolean type</span></span>|  
|`ELEMENT_TYPE_CHAR`|<span data-ttu-id="f7ec2-111">Tipo de carácter.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-111">A character type.</span></span>|  
|`ELEMENT_TYPE_I1`|<span data-ttu-id="f7ec2-112">Un entero de 1 byte con signo.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-112">A signed 1-byte integer.</span></span>|  
|`ELEMENT_TYPE_U1`|<span data-ttu-id="f7ec2-113">Entero de 1 bit sin signo.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-113">An unsigned 1-byte integer.</span></span>|  
|`ELEMENT_TYPE_I2`|<span data-ttu-id="f7ec2-114">Un entero con signo de 2 bytes.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-114">A signed 2-byte integer.</span></span>|  
|`ELEMENT_TYPE_U2`|<span data-ttu-id="f7ec2-115">Entero sin signo de 2 bytes.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-115">An unsigned 2-byte integer.</span></span>|  
|`ELEMENT_TYPE_I4`|<span data-ttu-id="f7ec2-116">Un entero de 4 bytes con signo.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-116">A signed 4-byte integer.</span></span>|  
|`ELEMENT_TYPE_U4`|<span data-ttu-id="f7ec2-117">Un entero de 4 bytes sin signo.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-117">An unsigned 4-byte integer.</span></span>|  
|`ELEMENT_TYPE_I8`|<span data-ttu-id="f7ec2-118">Un entero de 8 bytes con signo.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-118">A signed 8-byte integer.</span></span>|  
|`ELEMENT_TYPE_U8`|<span data-ttu-id="f7ec2-119">Entero sin signo de 8 bytes.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-119">An unsigned 8-byte integer.</span></span>|  
|`ELEMENT_TYPE_R4`|<span data-ttu-id="f7ec2-120">Un punto flotante de 4 bytes.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-120">A 4-byte floating point.</span></span>|  
|`ELEMENT_TYPE_R8`|<span data-ttu-id="f7ec2-121">Un punto flotante de 8 bytes.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-121">An 8-byte floating point.</span></span>|  
|`ELEMENT_TYPE_STRING`|<span data-ttu-id="f7ec2-122">Un tipo System.String.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-122">A System.String type.</span></span>|  
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="f7ec2-123">Un modificador de tipo de puntero.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-123">A pointer type modifier.</span></span>|  
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="f7ec2-124">Un modificador de tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-124">A reference type modifier.</span></span>|  
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="f7ec2-125">Un modificador de tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-125">A value type modifier.</span></span>|  
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="f7ec2-126">Un modificador de tipo de clase.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-126">A class type modifier.</span></span>|  
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="f7ec2-127">Un modificador de tipo de variable de clase.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-127">A class variable type modifier.</span></span>|  
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="f7ec2-128">Un modificador de tipo de matriz multidimensional.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-128">A multi-dimensional array type modifier.</span></span>|  
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="f7ec2-129">Un modificador de tipo para tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-129">A type modifier for generic types.</span></span>|  
|`ELEMENT_TYPE_TYPEDBYREF`|<span data-ttu-id="f7ec2-130">Referencia con tipo.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-130">A typed reference.</span></span>|  
|`ELEMENT_TYPE_I`|<span data-ttu-id="f7ec2-131">Tamaño de un entero nativo.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-131">Size of a native integer.</span></span>|  
|`ELEMENT_TYPE_U`|<span data-ttu-id="f7ec2-132">Tamaño de un entero nativo sin signo.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-132">Size of an unsigned native integer.</span></span>|  
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="f7ec2-133">Un puntero a una función.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-133">A pointer to a function.</span></span>|  
|`ELEMENT_TYPE_OBJECT`|<span data-ttu-id="f7ec2-134">Un tipo System.Object.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-134">A System.Object type.</span></span>|  
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="f7ec2-135">Una sola dimensión, cero modificador de tipo matriz de límite inferior.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-135">A single-dimensional, zero lower-bound array type modifier.</span></span>|  
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="f7ec2-136">Un modificador de tipo de variable del método.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-136">A method variable type modifier.</span></span>|  
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="f7ec2-137">Un lenguaje de C requiere el modificador.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-137">A C language required modifier.</span></span>|  
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="f7ec2-138">Un modificador opcional de lenguaje C.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-138">A C language optional modifier.</span></span>|  
|`ELEMENT_TYPE_INTERNAL`|<span data-ttu-id="f7ec2-139">Lo utiliza internamente.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-139">Used internally.</span></span>|  
|`ELEMENT_TYPE_MAX`|<span data-ttu-id="f7ec2-140">Tipo no válido.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-140">An invalid type.</span></span>|  
|`ELEMENT_TYPE_MODIFIER`|<span data-ttu-id="f7ec2-141">Lo utiliza internamente.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-141">Used internally.</span></span>|  
|`ELEMENT_TYPE_SENTINEL`|<span data-ttu-id="f7ec2-142">Un modificador de tipo que es un valor de Centinela para obtener una lista de un número variable de parámetros.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-142">A type modifier that is a sentinel for a list of a variable number of parameters.</span></span>|  
|`ELEMENT_TYPE_PINNED`|<span data-ttu-id="f7ec2-143">Lo utiliza internamente.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-143">Used internally.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7ec2-144">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7ec2-144">Remarks</span></span>  
 <span data-ttu-id="f7ec2-145">Los modificadores de tipo forman la base para representar tipos más complejos.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-145">The type modifiers form the basis for representing more complex types.</span></span> <span data-ttu-id="f7ec2-146">Un `CorElementType` se aplica el valor del modificador de tipo para el valor que le sigue inmediatamente en la signatura de tipo.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-146">A `CorElementType` type modifier value is applied to the value that immediately follows it in the type signature.</span></span> <span data-ttu-id="f7ec2-147">El valor que sigue el `CorElementType` valor del modificador de tipo puede ser un `CorElementType` otro valor, como se especifica en la tabla siguiente, un token de metadatos o el valor de tipo simple.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-147">The value that follows the `CorElementType` type modifier value can be a `CorElementType` simple type value, a metadata token, or other value, as specified in the following table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7ec2-148">Todos los números (*número*, *argumento Count*, *token de metadatos*, *rango*, *recuento*y *enlazados*) se almacenan como enteros comprimidos.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-148">All numbers (*number*, *argument Count*, *metadata token*, *rank*, *count*, and *bound*) are stored as compressed integers.</span></span> <span data-ttu-id="f7ec2-149">Consulte [estándar ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=116487) en el sitio Web de ECMA para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f7ec2-149">See [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=116487) on the ECMA Web site for details.</span></span>  
  
|<span data-ttu-id="f7ec2-150">Modificador de tipo</span><span class="sxs-lookup"><span data-stu-id="f7ec2-150">Type modifier</span></span>|<span data-ttu-id="f7ec2-151">Formato</span><span class="sxs-lookup"><span data-stu-id="f7ec2-151">Format</span></span>|  
|-------------------|------------|  
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="f7ec2-152">ELEMENT_TYPE_PTR < un `CorElementType` valor ></span><span class="sxs-lookup"><span data-stu-id="f7ec2-152">ELEMENT_TYPE_PTR <a `CorElementType` value></span></span>|  
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="f7ec2-153">ELEMENT_TYPE_BYREF < un `CorElementType` valor ></span><span class="sxs-lookup"><span data-stu-id="f7ec2-153">ELEMENT_TYPE_BYREF <a `CorElementType` value></span></span>|  
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="f7ec2-154">ELEMENT_TYPE_VALUETYPE < una `mdTypeDef` token de metadatos ></span><span class="sxs-lookup"><span data-stu-id="f7ec2-154">ELEMENT_TYPE_VALUETYPE <an `mdTypeDef` metadata token></span></span>|  
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="f7ec2-155">ELEMENT_TYPE_CLASS < una `mdTypeDef` token de metadatos ></span><span class="sxs-lookup"><span data-stu-id="f7ec2-155">ELEMENT_TYPE_CLASS <an `mdTypeDef` metadata token></span></span>|  
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="f7ec2-156">ELEMENT_TYPE_VAR \<número ></span><span class="sxs-lookup"><span data-stu-id="f7ec2-156">ELEMENT_TYPE_VAR \<number></span></span>|  
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="f7ec2-157">ELEMENT_TYPE_ARRAY < un `CorElementType` valor > \<rango > \<count1 > \<bound1 >... \<countN > \<boundN ></span><span class="sxs-lookup"><span data-stu-id="f7ec2-157">ELEMENT_TYPE_ARRAY <a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN> \<boundN></span></span>|  
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="f7ec2-158">ELEMENT_TYPE_GENERICINST < una `mdTypeDef` token de metadatos > \<argumento Count > \<arg1 >... \<argN ></span><span class="sxs-lookup"><span data-stu-id="f7ec2-158">ELEMENT_TYPE_GENERICINST <an `mdTypeDef` metadata token> \<argument Count> \<arg1> ... \<argN></span></span>|  
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="f7ec2-159">ELEMENT_TYPE_FNPTR \<firma completa de la función, incluida la convención de llamada ></span><span class="sxs-lookup"><span data-stu-id="f7ec2-159">ELEMENT_TYPE_FNPTR \<complete signature for the function, including calling convention></span></span>|  
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="f7ec2-160">ELEMENT_TYPE_SZARRAY < un `CorElementType` valor ></span><span class="sxs-lookup"><span data-stu-id="f7ec2-160">ELEMENT_TYPE_SZARRAY <a `CorElementType` value></span></span>|  
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="f7ec2-161">ELEMENT_TYPE_MVAR \<number></span><span class="sxs-lookup"><span data-stu-id="f7ec2-161">ELEMENT_TYPE_MVAR \<number></span></span>|  
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="f7ec2-162">ELEMENT_TYPE_ < un `mdTypeRef` o `mdTypeDef` token de metadatos ></span><span class="sxs-lookup"><span data-stu-id="f7ec2-162">ELEMENT_TYPE_<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|  
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="f7ec2-163">E_T_CMOD_OPT < un `mdTypeRef` o `mdTypeDef` token de metadatos ></span><span class="sxs-lookup"><span data-stu-id="f7ec2-163">E_T_CMOD_OPT <a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f7ec2-164">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7ec2-164">Requirements</span></span>  
 <span data-ttu-id="f7ec2-165">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7ec2-165">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7ec2-166">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="f7ec2-166">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f7ec2-167">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7ec2-167">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7ec2-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7ec2-168">See also</span></span>

- [<span data-ttu-id="f7ec2-169">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="f7ec2-169">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
