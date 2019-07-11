---
title: CorNativeType (Enumeración)
ms.date: 03/30/2017
api_name:
- CorNativeType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeType
helpviewer_keywords:
- CorNativeType enumeration [.NET Framework metadata]
ms.assetid: e47a72f1-9609-48ed-bb34-97170d7f6890
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 846c754aeb0a710fa70e906e666f694eaa77c576
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781709"
---
# <a name="cornativetype-enumeration"></a><span data-ttu-id="38d71-102">CorNativeType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="38d71-102">CorNativeType Enumeration</span></span>
<span data-ttu-id="38d71-103">Contiene valores que describen los tipos nativos no administrados.</span><span class="sxs-lookup"><span data-stu-id="38d71-103">Contains values that describe native unmanaged types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38d71-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38d71-104">Syntax</span></span>  
  
```cpp  
typedef enum CorNativeType {  
  
    NATIVE_TYPE_END                  = 0x0,  
    NATIVE_TYPE_VOID                 = 0x1,  
    NATIVE_TYPE_BOOLEAN              = 0x2,  
    NATIVE_TYPE_I1                   = 0x3,  
    NATIVE_TYPE_U1                   = 0x4,  
    NATIVE_TYPE_I2                   = 0x5,  
    NATIVE_TYPE_U2                   = 0x6,  
    NATIVE_TYPE_I4                   = 0x7,  
    NATIVE_TYPE_U4                   = 0x8,  
    NATIVE_TYPE_I8                   = 0x9,  
    NATIVE_TYPE_U8                   = 0xa,  
    NATIVE_TYPE_R4                   = 0xb,  
    NATIVE_TYPE_R8                   = 0xc,  
    NATIVE_TYPE_SYSCHAR              = 0xd,  
    NATIVE_TYPE_VARIANT              = 0xe,  
    NATIVE_TYPE_CURRENCY             = 0xf,  
    NATIVE_TYPE_PTR                  = 0x10,  
  
    NATIVE_TYPE_DECIMAL              = 0x11,  
    NATIVE_TYPE_DATE                 = 0x12,  
    NATIVE_TYPE_BSTR                 = 0x13,  
    NATIVE_TYPE_LPSTR                = 0x14,  
    NATIVE_TYPE_LPWSTR               = 0x15,  
    NATIVE_TYPE_LPTSTR               = 0x16,  
    NATIVE_TYPE_FIXEDSYSSTRING       = 0x17,  
    NATIVE_TYPE_OBJECTREF            = 0x18,  
    NATIVE_TYPE_IUNKNOWN             = 0x19,  
    NATIVE_TYPE_IDISPATCH            = 0x1a,  
    NATIVE_TYPE_STRUCT               = 0x1b,  
    NATIVE_TYPE_INTF                 = 0x1c,  
    NATIVE_TYPE_SAFEARRAY            = 0x1d,  
    NATIVE_TYPE_FIXEDARRAY           = 0x1e,  
    NATIVE_TYPE_INT                  = 0x1f,  
    NATIVE_TYPE_UINT                 = 0x20,  
  
    NATIVE_TYPE_NESTEDSTRUCT         = 0x21,  
    NATIVE_TYPE_BYVALSTR             = 0x22,  
    NATIVE_TYPE_ANSIBSTR             = 0x23,  
    NATIVE_TYPE_TBSTR                = 0x24,  
    NATIVE_TYPE_VARIANTBOOL          = 0x25,  
    NATIVE_TYPE_FUNC                 = 0x26,  
  
    NATIVE_TYPE_ASANY                = 0x28,  
    NATIVE_TYPE_ARRAY                = 0x2a,  
    NATIVE_TYPE_LPSTRUCT             = 0x2b,  
    NATIVE_TYPE_CUSTOMMARSHALER      = 0x2c,  
    NATIVE_TYPE_IINSPECTABLE         = 0x2e,  
    NATIVE_TYPE_HSTRING              = 0x2f,  
  
    NATIVE_TYPE_ERROR                = 0x2d,   
  
    NATIVE_TYPE_MAX                  = 0x50  
  
} CorNativeType;  
```  
  
## <a name="members"></a><span data-ttu-id="38d71-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="38d71-105">Members</span></span>  
  
|<span data-ttu-id="38d71-106">Member</span><span class="sxs-lookup"><span data-stu-id="38d71-106">Member</span></span>|<span data-ttu-id="38d71-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="38d71-107">Description</span></span>|  
|------------|-----------------|  
|`NATIVE_TYPE_END`|<span data-ttu-id="38d71-108">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="38d71-108">Obsolete.</span></span>|  
|`NATIVE_TYPE_VOID`|<span data-ttu-id="38d71-109">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="38d71-109">Obsolete.</span></span>|  
|`NATIVE_TYPE_BOOLEAN`|<span data-ttu-id="38d71-110">Un valor booleano de 4 bytes, donde TRUE es distinto de cero y FALSE es cero.</span><span class="sxs-lookup"><span data-stu-id="38d71-110">A 4-byte Boolean value, where TRUE is non-zero and FALSE is zero.</span></span>|  
|`NATIVE_TYPE_I1`|<span data-ttu-id="38d71-111">Un valor entero de 8 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="38d71-111">A signed 8-bit integer value.</span></span>|  
|`NATIVE_TYPE_U1`|<span data-ttu-id="38d71-112">Un valor entero de 8 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="38d71-112">An unsigned 8-bit integer value.</span></span>|  
|`NATIVE_TYPE_I2`|<span data-ttu-id="38d71-113">Un valor entero de 16 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="38d71-113">A signed 16-bit integer value.</span></span>|  
|`NATIVE_TYPE_U2`|<span data-ttu-id="38d71-114">Un valor entero de 16 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="38d71-114">An unsigned 16-bit integer value.</span></span>|  
|`NATIVE_TYPE_I4`|<span data-ttu-id="38d71-115">Un valor entero de 32 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="38d71-115">A signed 32-bit integer value.</span></span>|  
|`NATIVE_TYPE_U4`|<span data-ttu-id="38d71-116">Valor entero de 32 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="38d71-116">An unsigned 32-bit integer value.</span></span>|  
|`NATIVE_TYPE_I8`|<span data-ttu-id="38d71-117">Un valor entero de 64 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="38d71-117">A signed 64-bit integer value.</span></span>|  
|`NATIVE_TYPE_U8`|<span data-ttu-id="38d71-118">Un valor entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="38d71-118">An unsigned 64-bit integer value.</span></span>|  
|`NATIVE_TYPE_R4`|<span data-ttu-id="38d71-119">Un valor numérico punto flotante de 4 bytes.</span><span class="sxs-lookup"><span data-stu-id="38d71-119">A 4-byte floating-point numeric value.</span></span>|  
|`NATIVE_TYPE_R8`|<span data-ttu-id="38d71-120">Un valor numérico punto flotante de 8 bytes.</span><span class="sxs-lookup"><span data-stu-id="38d71-120">An 8-byte floating-point numeric value.</span></span>|  
|`NATIVE_TYPE_SYSCHAR`|<span data-ttu-id="38d71-121">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="38d71-121">Obsolete.</span></span>|  
|`NATIVE_TYPE_VARIANT`|<span data-ttu-id="38d71-122">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="38d71-122">Obsolete.</span></span>|  
|`NATIVE_TYPE_CURRENCY`|<span data-ttu-id="38d71-123">Un tipo COM numérico que corresponde a los recursos administrados <xref:System.Decimal> tipo.</span><span class="sxs-lookup"><span data-stu-id="38d71-123">A numeric COM type that corresponds to the managed <xref:System.Decimal> type.</span></span>|  
|`NATIVE_TYPE_PTR`|<span data-ttu-id="38d71-124">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="38d71-124">Obsolete.</span></span>|  
|`NATIVE_TYPE_DECIMAL`|<span data-ttu-id="38d71-125">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="38d71-125">Obsolete.</span></span>|  
|`NATIVE_TYPE_DATE`|<span data-ttu-id="38d71-126">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="38d71-126">Obsolete.</span></span>|  
|`NATIVE_TYPE_BSTR`|<span data-ttu-id="38d71-127">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="38d71-127">COM Interop.</span></span>|  
|`NATIVE_TYPE_LPSTR`|<span data-ttu-id="38d71-128">Un valor de cadena LPSTR.</span><span class="sxs-lookup"><span data-stu-id="38d71-128">An LPSTR string value.</span></span>|  
|`NATIVE_TYPE_LPWSTR`|<span data-ttu-id="38d71-129">Un valor de cadena LPWSTR.</span><span class="sxs-lookup"><span data-stu-id="38d71-129">An LPWSTR string value.</span></span>|  
|`NATIVE_TYPE_LPTSTR`|<span data-ttu-id="38d71-130">Un valor de cadena LPTSTR.</span><span class="sxs-lookup"><span data-stu-id="38d71-130">An LPTSTR string value.</span></span>|  
|`NATIVE_TYPE_FIXEDSYSSTRING`|<span data-ttu-id="38d71-131">Valor de cadena fija, definido por el sistema.</span><span class="sxs-lookup"><span data-stu-id="38d71-131">A fixed, system-defined string value.</span></span>|  
|`NATIVE_TYPE_OBJECTREF`|<span data-ttu-id="38d71-132">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="38d71-132">Obsolete.</span></span>|  
|`NATIVE_TYPE_IUNKNOWN`|<span data-ttu-id="38d71-133">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="38d71-133">COM Interop.</span></span>|  
|`NATIVE_TYPE_IDISPATCH`|<span data-ttu-id="38d71-134">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="38d71-134">COM Interop.</span></span>|  
|`NATIVE_TYPE_STRUCT`|<span data-ttu-id="38d71-135">Un valor de la estructura nativa.</span><span class="sxs-lookup"><span data-stu-id="38d71-135">A native structure value.</span></span>|  
|`NATIVE_TYPE_INTF`|<span data-ttu-id="38d71-136">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="38d71-136">COM Interop.</span></span>|  
|`NATIVE_TYPE_SAFEARRAY`|<span data-ttu-id="38d71-137">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="38d71-137">COM Interop.</span></span>|  
|`NATIVE_TYPE_FIXEDARRAY`|<span data-ttu-id="38d71-138">Un valor de matriz de longitud fija.</span><span class="sxs-lookup"><span data-stu-id="38d71-138">A fixed-length array value.</span></span>|  
|`NATIVE_TYPE_INT`|<span data-ttu-id="38d71-139">Un valor entero de 16 bits con signo nativo.</span><span class="sxs-lookup"><span data-stu-id="38d71-139">A native 16-bit signed integer value.</span></span>|  
|`NATIVE_TYPE_UINT`|<span data-ttu-id="38d71-140">Un valor entero sin signo de 16 bits nativo.</span><span class="sxs-lookup"><span data-stu-id="38d71-140">A native 16-bit unsigned integer value.</span></span>|  
|`NATIVE_TYPE_NESTEDSTRUCT`|<span data-ttu-id="38d71-141">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="38d71-141">Obsolete.</span></span><br /><br /> <span data-ttu-id="38d71-142">Utilice NATIVE_TYPE_STRUCT.</span><span class="sxs-lookup"><span data-stu-id="38d71-142">Use NATIVE_TYPE_STRUCT.</span></span>|  
|`NATIVE_TYPE_BYVALSTR`|<span data-ttu-id="38d71-143">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="38d71-143">COM Interop.</span></span>|  
|`NATIVE_TYPE_ANSIBSTR`|<span data-ttu-id="38d71-144">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="38d71-144">COM Interop.</span></span>|  
|`NATIVE_TYPE_TBSTR`|<span data-ttu-id="38d71-145">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="38d71-145">COM Interop.</span></span><br /><br /> <span data-ttu-id="38d71-146">Seleccione BSTR o ANSIBSTR, dependiendo de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="38d71-146">Select BSTR or ANSIBSTR depending on the platform.</span></span>|  
|`NATIVE_TYPE_VARIANTBOOL`|<span data-ttu-id="38d71-147">Valor booleano de 2 bytes donde TRUE es -1 y FALSE es cero.</span><span class="sxs-lookup"><span data-stu-id="38d71-147">A 2-byte Boolean value, where TRUE is -1 and FALSE is zero.</span></span>|  
|`NATIVE_TYPE_FUNC`|<span data-ttu-id="38d71-148">Puntero de función.</span><span class="sxs-lookup"><span data-stu-id="38d71-148">A function pointer.</span></span>|  
|`NATIVE_TYPE_ASANY`|<span data-ttu-id="38d71-149">Una referencia a cualquier tipo nativo.</span><span class="sxs-lookup"><span data-stu-id="38d71-149">A reference to any native type.</span></span>|  
|`NATIVE_TYPE_ARRAY`|<span data-ttu-id="38d71-150">Una referencia a una matriz con los miembros de un tipo no especificado.</span><span class="sxs-lookup"><span data-stu-id="38d71-150">A reference to an array with members of an unspecified type.</span></span>|  
|`NATIVE_TYPE_LPSTRUCT`|<span data-ttu-id="38d71-151">Puntero a una estructura de entero de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="38d71-151">A 32-bit integer pointer to a structure.</span></span>|  
|`NATIVE_TYPE_CUSTOMMARSHALER`|<span data-ttu-id="38d71-152">Un tipo nativo del contador de referencias personalizado.</span><span class="sxs-lookup"><span data-stu-id="38d71-152">A custom marshaler native type.</span></span><br /><br /> <span data-ttu-id="38d71-153">Esto debe ir seguido por una cadena el formato siguiente: "El contador de referencias de tipo nativo 0Nombre/nombre escriba nombre/0Cookie opcional/0" o "{nativo GUID de tipo} / tipo de contador de referencias 0Nombre nombre/0Cookie opcional/0"</span><span class="sxs-lookup"><span data-stu-id="38d71-153">This must be followed by a string of the following format: "Native type name/0Custom marshaler type name/0Optional cookie/0" or "{Native type GUID}/0Custom marshaler type name/0Optional cookie/0"</span></span>|  
|`NATIVE_TYPE_ERROR`|<span data-ttu-id="38d71-154">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="38d71-154">COM Interop.</span></span><br /><br /> <span data-ttu-id="38d71-155">Con ELEMENT_TYPE_I4 este tipo se asigna a VT_HRESULT.</span><span class="sxs-lookup"><span data-stu-id="38d71-155">With ELEMENT_TYPE_I4 this type maps to VT_HRESULT.</span></span>|  
|`NATIVE_TYPE_IINSPECTABLE`|<span data-ttu-id="38d71-156">Nativo `IInspectable` tipo.</span><span class="sxs-lookup"><span data-stu-id="38d71-156">A native `IInspectable` type.</span></span>|  
|`NATIVE_TYPE_HSTRING`|<span data-ttu-id="38d71-157">Nativo `HString`.</span><span class="sxs-lookup"><span data-stu-id="38d71-157">A native `HString`.</span></span>|  
|`NATIVE_TYPE_MAX`|<span data-ttu-id="38d71-158">Un valor no válido.</span><span class="sxs-lookup"><span data-stu-id="38d71-158">An invalid value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38d71-159">Requisitos</span><span class="sxs-lookup"><span data-stu-id="38d71-159">Requirements</span></span>  
 <span data-ttu-id="38d71-160">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38d71-160">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38d71-161">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="38d71-161">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="38d71-162">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38d71-162">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38d71-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="38d71-163">See also</span></span>

- <xref:System.Runtime.InteropServices.UnmanagedType>
- [<span data-ttu-id="38d71-164">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="38d71-164">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
