---
title: CorElementType Enumeration1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorElementType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorElementType
helpviewer_keywords: CorElementType enumeration [.NET Framework metadata]
ms.assetid: c3809c8f-1737-4f0f-9442-0c01ee689871
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8932e295aa1a6c6cf961e7b3a218e76984da02cb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corelementtype-enumeration1"></a><span data-ttu-id="5fc36-102">CorElementType Enumeration1</span><span class="sxs-lookup"><span data-stu-id="5fc36-102">CorElementType Enumeration1</span></span>
<span data-ttu-id="5fc36-103">Especifica un common language runtime <xref:System.Type>, un modificador de tipo o información sobre un tipo en una signatura de tipo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="5fc36-103">Specifies a common language runtime <xref:System.Type>, a type modifier, or information about a type in a metadata type signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fc36-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5fc36-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="5fc36-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="5fc36-105">Members</span></span>  
  
|<span data-ttu-id="5fc36-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="5fc36-106">Member</span></span>|<span data-ttu-id="5fc36-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5fc36-107">Description</span></span>|  
|------------|-----------------|  
|`ELEMENT_TYPE_END`|<span data-ttu-id="5fc36-108">Se utiliza internamente.</span><span class="sxs-lookup"><span data-stu-id="5fc36-108">Used internally.</span></span>|  
|`ELEMENT_TYPE_VOID`|<span data-ttu-id="5fc36-109">Un tipo void.</span><span class="sxs-lookup"><span data-stu-id="5fc36-109">A void type.</span></span>|  
|`ELEMENT_TYPE_BOOLEAN`|<span data-ttu-id="5fc36-110">Un tipo booleano</span><span class="sxs-lookup"><span data-stu-id="5fc36-110">A Boolean type</span></span>|  
|`ELEMENT_TYPE_CHAR`|<span data-ttu-id="5fc36-111">Tipo de carácter.</span><span class="sxs-lookup"><span data-stu-id="5fc36-111">A character type.</span></span>|  
|`ELEMENT_TYPE_I1`|<span data-ttu-id="5fc36-112">Un entero de 1 byte con signo.</span><span class="sxs-lookup"><span data-stu-id="5fc36-112">A signed 1-byte integer.</span></span>|  
|`ELEMENT_TYPE_U1`|<span data-ttu-id="5fc36-113">Entero de 1 bit sin signo.</span><span class="sxs-lookup"><span data-stu-id="5fc36-113">An unsigned 1-byte integer.</span></span>|  
|`ELEMENT_TYPE_I2`|<span data-ttu-id="5fc36-114">Un entero de 2 bytes con signo.</span><span class="sxs-lookup"><span data-stu-id="5fc36-114">A signed 2-byte integer.</span></span>|  
|`ELEMENT_TYPE_U2`|<span data-ttu-id="5fc36-115">Un entero de 2 bytes sin signo.</span><span class="sxs-lookup"><span data-stu-id="5fc36-115">An unsigned 2-byte integer.</span></span>|  
|`ELEMENT_TYPE_I4`|<span data-ttu-id="5fc36-116">Un entero de 4 bytes con signo.</span><span class="sxs-lookup"><span data-stu-id="5fc36-116">A signed 4-byte integer.</span></span>|  
|`ELEMENT_TYPE_U4`|<span data-ttu-id="5fc36-117">Un entero de 4 bytes sin signo.</span><span class="sxs-lookup"><span data-stu-id="5fc36-117">An unsigned 4-byte integer.</span></span>|  
|`ELEMENT_TYPE_I8`|<span data-ttu-id="5fc36-118">Un entero de 8 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="5fc36-118">A signed 8-byte integer.</span></span>|  
|`ELEMENT_TYPE_U8`|<span data-ttu-id="5fc36-119">Un entero de 8 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="5fc36-119">An unsigned 8-byte integer.</span></span>|  
|`ELEMENT_TYPE_R4`|<span data-ttu-id="5fc36-120">Un punto flotante de 4 bytes.</span><span class="sxs-lookup"><span data-stu-id="5fc36-120">A 4-byte floating point.</span></span>|  
|`ELEMENT_TYPE_R8`|<span data-ttu-id="5fc36-121">Un punto flotante de 8 bytes.</span><span class="sxs-lookup"><span data-stu-id="5fc36-121">An 8-byte floating point.</span></span>|  
|`ELEMENT_TYPE_STRING`|<span data-ttu-id="5fc36-122">Un tipo System.String.</span><span class="sxs-lookup"><span data-stu-id="5fc36-122">A System.String type.</span></span>|  
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="5fc36-123">Un modificador de tipo de puntero.</span><span class="sxs-lookup"><span data-stu-id="5fc36-123">A pointer type modifier.</span></span>|  
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="5fc36-124">Un modificador de tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="5fc36-124">A reference type modifier.</span></span>|  
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="5fc36-125">Un modificador de tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="5fc36-125">A value type modifier.</span></span>|  
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="5fc36-126">Un modificador de tipo de clase.</span><span class="sxs-lookup"><span data-stu-id="5fc36-126">A class type modifier.</span></span>|  
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="5fc36-127">Un modificador de tipo de variable de clase.</span><span class="sxs-lookup"><span data-stu-id="5fc36-127">A class variable type modifier.</span></span>|  
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="5fc36-128">Un modificador de tipo matriz multidimensional.</span><span class="sxs-lookup"><span data-stu-id="5fc36-128">A multi-dimensional array type modifier.</span></span>|  
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="5fc36-129">Un modificador de tipo para tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="5fc36-129">A type modifier for generic types.</span></span>|  
|`ELEMENT_TYPE_TYPEDBYREF`|<span data-ttu-id="5fc36-130">Referencia con tipo.</span><span class="sxs-lookup"><span data-stu-id="5fc36-130">A typed reference.</span></span>|  
|`ELEMENT_TYPE_I`|<span data-ttu-id="5fc36-131">Tamaño de un entero nativo.</span><span class="sxs-lookup"><span data-stu-id="5fc36-131">Size of a native integer.</span></span>|  
|`ELEMENT_TYPE_U`|<span data-ttu-id="5fc36-132">Tamaño de un entero nativo sin signo.</span><span class="sxs-lookup"><span data-stu-id="5fc36-132">Size of an unsigned native integer.</span></span>|  
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="5fc36-133">Un puntero a una función.</span><span class="sxs-lookup"><span data-stu-id="5fc36-133">A pointer to a function.</span></span>|  
|`ELEMENT_TYPE_OBJECT`|<span data-ttu-id="5fc36-134">Un tipo System.Object.</span><span class="sxs-lookup"><span data-stu-id="5fc36-134">A System.Object type.</span></span>|  
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="5fc36-135">Una sola dimensión, cero modificador de tipo de matriz de límite inferior.</span><span class="sxs-lookup"><span data-stu-id="5fc36-135">A single-dimensional, zero lower-bound array type modifier.</span></span>|  
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="5fc36-136">Un modificador de tipo de variable de método.</span><span class="sxs-lookup"><span data-stu-id="5fc36-136">A method variable type modifier.</span></span>|  
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="5fc36-137">Modificador requerido por el lenguaje c.</span><span class="sxs-lookup"><span data-stu-id="5fc36-137">A C language required modifier.</span></span>|  
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="5fc36-138">Un modificador opcional de lenguaje C.</span><span class="sxs-lookup"><span data-stu-id="5fc36-138">A C language optional modifier.</span></span>|  
|`ELEMENT_TYPE_INTERNAL`|<span data-ttu-id="5fc36-139">Se utiliza internamente.</span><span class="sxs-lookup"><span data-stu-id="5fc36-139">Used internally.</span></span>|  
|`ELEMENT_TYPE_MAX`|<span data-ttu-id="5fc36-140">Tipo no válido.</span><span class="sxs-lookup"><span data-stu-id="5fc36-140">An invalid type.</span></span>|  
|`ELEMENT_TYPE_MODIFIER`|<span data-ttu-id="5fc36-141">Se utiliza internamente.</span><span class="sxs-lookup"><span data-stu-id="5fc36-141">Used internally.</span></span>|  
|`ELEMENT_TYPE_SENTINEL`|<span data-ttu-id="5fc36-142">Un modificador de tipo que es un Centinela para obtener una lista de un número variable de parámetros.</span><span class="sxs-lookup"><span data-stu-id="5fc36-142">A type modifier that is a sentinel for a list of a variable number of parameters.</span></span>|  
|`ELEMENT_TYPE_PINNED`|<span data-ttu-id="5fc36-143">Se utiliza internamente.</span><span class="sxs-lookup"><span data-stu-id="5fc36-143">Used internally.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5fc36-144">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5fc36-144">Remarks</span></span>  
 <span data-ttu-id="5fc36-145">Los modificadores de tipo forman la base para representar tipos más complejos.</span><span class="sxs-lookup"><span data-stu-id="5fc36-145">The type modifiers form the basis for representing more complex types.</span></span> <span data-ttu-id="5fc36-146">Un `CorElementType` valor del modificador de tipo se aplica al valor que le sigue inmediatamente en la signatura de tipo.</span><span class="sxs-lookup"><span data-stu-id="5fc36-146">A `CorElementType` type modifier value is applied to the value that immediately follows it in the type signature.</span></span> <span data-ttu-id="5fc36-147">El valor que sigue a la `CorElementType` valor de modificador de tipo puede ser un `CorElementType` valor de tipo simple, un token de metadatos u otro valor, como se especifica en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="5fc36-147">The value that follows the `CorElementType` type modifier value can be a `CorElementType` simple type value, a metadata token, or other value, as specified in the following table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5fc36-148">Todos los números (*número*, *argumento Count*, *token de metadatos*, *rango*, *recuento*y *enlazados*) se almacenan como enteros comprimidos.</span><span class="sxs-lookup"><span data-stu-id="5fc36-148">All numbers (*number*, *argument Count*, *metadata token*, *rank*, *count*, and *bound*) are stored as compressed integers.</span></span> <span data-ttu-id="5fc36-149">Vea [estándar ECMA-335: Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=116487) en el sitio Web de ECMA para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5fc36-149">See [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=116487) on the ECMA Web site for details.</span></span>  
  
|<span data-ttu-id="5fc36-150">Modificador de tipo</span><span class="sxs-lookup"><span data-stu-id="5fc36-150">Type modifier</span></span>|<span data-ttu-id="5fc36-151">Formato</span><span class="sxs-lookup"><span data-stu-id="5fc36-151">Format</span></span>|  
|-------------------|------------|  
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="5fc36-152">ELEMENT_TYPE_PTR < un `CorElementType` valor ></span><span class="sxs-lookup"><span data-stu-id="5fc36-152">ELEMENT_TYPE_PTR <a `CorElementType` value></span></span>|  
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="5fc36-153">ELEMENT_TYPE_BYREF < un `CorElementType` valor ></span><span class="sxs-lookup"><span data-stu-id="5fc36-153">ELEMENT_TYPE_BYREF <a `CorElementType` value></span></span>|  
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="5fc36-154">ELEMENT_TYPE_VALUETYPE < una `mdTypeDef` token de metadatos ></span><span class="sxs-lookup"><span data-stu-id="5fc36-154">ELEMENT_TYPE_VALUETYPE <an `mdTypeDef` metadata token></span></span>|  
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="5fc36-155">ELEMENT_TYPE_CLASS < una `mdTypeDef` token de metadatos ></span><span class="sxs-lookup"><span data-stu-id="5fc36-155">ELEMENT_TYPE_CLASS <an `mdTypeDef` metadata token></span></span>|  
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="5fc36-156">ELEMENT_TYPE_VAR \<número ></span><span class="sxs-lookup"><span data-stu-id="5fc36-156">ELEMENT_TYPE_VAR \<number></span></span>|  
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="5fc36-157">ELEMENT_TYPE_ARRAY < una `CorElementType` valor > \<rango > \<count1 > \<bound1 >... \<countN > \<boundN ></span><span class="sxs-lookup"><span data-stu-id="5fc36-157">ELEMENT_TYPE_ARRAY <a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN> \<boundN></span></span>|  
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="5fc36-158">ELEMENT_TYPE_GENERICINST < una `mdTypeDef` token de metadatos > \<argumento Count > \<arg1 >... \<argN ></span><span class="sxs-lookup"><span data-stu-id="5fc36-158">ELEMENT_TYPE_GENERICINST <an `mdTypeDef` metadata token> \<argument Count> \<arg1> ... \<argN></span></span>|  
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="5fc36-159">ELEMENT_TYPE_FNPTR \<firma completa de la función, incluida la convención de llamada ></span><span class="sxs-lookup"><span data-stu-id="5fc36-159">ELEMENT_TYPE_FNPTR \<complete signature for the function, including calling convention></span></span>|  
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="5fc36-160">ELEMENT_TYPE_SZARRAY < un `CorElementType` valor ></span><span class="sxs-lookup"><span data-stu-id="5fc36-160">ELEMENT_TYPE_SZARRAY <a `CorElementType` value></span></span>|  
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="5fc36-161">ELEMENT_TYPE_MVAR \<número ></span><span class="sxs-lookup"><span data-stu-id="5fc36-161">ELEMENT_TYPE_MVAR \<number></span></span>|  
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="5fc36-162">ELEMENT_TYPE_ < una `mdTypeRef` o `mdTypeDef` token de metadatos ></span><span class="sxs-lookup"><span data-stu-id="5fc36-162">ELEMENT_TYPE_<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|  
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="5fc36-163">E_T_CMOD_OPT < una `mdTypeRef` o `mdTypeDef` token de metadatos ></span><span class="sxs-lookup"><span data-stu-id="5fc36-163">E_T_CMOD_OPT <a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5fc36-164">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5fc36-164">Requirements</span></span>  
 <span data-ttu-id="5fc36-165">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fc36-165">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fc36-166">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="5fc36-166">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="5fc36-167">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fc36-167">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fc36-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fc36-168">See Also</span></span>  
 [<span data-ttu-id="5fc36-169">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="5fc36-169">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
