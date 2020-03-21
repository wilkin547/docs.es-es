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
ms.openlocfilehash: 09a351db65c7ed310d3eb68c71a5207ed6040dd4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177968"
---
# <a name="cornativetype-enumeration"></a><span data-ttu-id="ef9ad-102">CorNativeType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ef9ad-102">CorNativeType Enumeration</span></span>
<span data-ttu-id="ef9ad-103">Contiene valores que describen los tipos nativos no administrados.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-103">Contains values that describe native unmanaged types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef9ad-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef9ad-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ef9ad-105">Members</span><span class="sxs-lookup"><span data-stu-id="ef9ad-105">Members</span></span>  
  
|<span data-ttu-id="ef9ad-106">Member</span><span class="sxs-lookup"><span data-stu-id="ef9ad-106">Member</span></span>|<span data-ttu-id="ef9ad-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef9ad-107">Description</span></span>|  
|------------|-----------------|  
|`NATIVE_TYPE_END`|<span data-ttu-id="ef9ad-108">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-108">Obsolete.</span></span>|  
|`NATIVE_TYPE_VOID`|<span data-ttu-id="ef9ad-109">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-109">Obsolete.</span></span>|  
|`NATIVE_TYPE_BOOLEAN`|<span data-ttu-id="ef9ad-110">Un valor booleano de 4 bytes, donde TRUE es distinto de cero y FALSE es cero.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-110">A 4-byte Boolean value, where TRUE is non-zero and FALSE is zero.</span></span>|  
|`NATIVE_TYPE_I1`|<span data-ttu-id="ef9ad-111">Un valor entero de 8 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-111">A signed 8-bit integer value.</span></span>|  
|`NATIVE_TYPE_U1`|<span data-ttu-id="ef9ad-112">Un valor entero de 8 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-112">An unsigned 8-bit integer value.</span></span>|  
|`NATIVE_TYPE_I2`|<span data-ttu-id="ef9ad-113">Un valor entero de 16 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-113">A signed 16-bit integer value.</span></span>|  
|`NATIVE_TYPE_U2`|<span data-ttu-id="ef9ad-114">Un valor entero de 16 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-114">An unsigned 16-bit integer value.</span></span>|  
|`NATIVE_TYPE_I4`|<span data-ttu-id="ef9ad-115">Un valor entero de 32 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-115">A signed 32-bit integer value.</span></span>|  
|`NATIVE_TYPE_U4`|<span data-ttu-id="ef9ad-116">Valor entero de 32 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-116">An unsigned 32-bit integer value.</span></span>|  
|`NATIVE_TYPE_I8`|<span data-ttu-id="ef9ad-117">Un valor entero de 64 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-117">A signed 64-bit integer value.</span></span>|  
|`NATIVE_TYPE_U8`|<span data-ttu-id="ef9ad-118">Un valor entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-118">An unsigned 64-bit integer value.</span></span>|  
|`NATIVE_TYPE_R4`|<span data-ttu-id="ef9ad-119">Un valor numérico de punto flotante de 4 bytes.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-119">A 4-byte floating-point numeric value.</span></span>|  
|`NATIVE_TYPE_R8`|<span data-ttu-id="ef9ad-120">Un valor numérico de punto flotante de 8 bytes.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-120">An 8-byte floating-point numeric value.</span></span>|  
|`NATIVE_TYPE_SYSCHAR`|<span data-ttu-id="ef9ad-121">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-121">Obsolete.</span></span>|  
|`NATIVE_TYPE_VARIANT`|<span data-ttu-id="ef9ad-122">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-122">Obsolete.</span></span>|  
|`NATIVE_TYPE_CURRENCY`|<span data-ttu-id="ef9ad-123">Un tipo COM numérico que <xref:System.Decimal> corresponde al tipo administrado.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-123">A numeric COM type that corresponds to the managed <xref:System.Decimal> type.</span></span>|  
|`NATIVE_TYPE_PTR`|<span data-ttu-id="ef9ad-124">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-124">Obsolete.</span></span>|  
|`NATIVE_TYPE_DECIMAL`|<span data-ttu-id="ef9ad-125">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-125">Obsolete.</span></span>|  
|`NATIVE_TYPE_DATE`|<span data-ttu-id="ef9ad-126">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-126">Obsolete.</span></span>|  
|`NATIVE_TYPE_BSTR`|<span data-ttu-id="ef9ad-127">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-127">COM Interop.</span></span>|  
|`NATIVE_TYPE_LPSTR`|<span data-ttu-id="ef9ad-128">Un valor de cadena LPSTR.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-128">An LPSTR string value.</span></span>|  
|`NATIVE_TYPE_LPWSTR`|<span data-ttu-id="ef9ad-129">Un valor de cadena LPWSTR.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-129">An LPWSTR string value.</span></span>|  
|`NATIVE_TYPE_LPTSTR`|<span data-ttu-id="ef9ad-130">Un valor de cadena LPTSTR.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-130">An LPTSTR string value.</span></span>|  
|`NATIVE_TYPE_FIXEDSYSSTRING`|<span data-ttu-id="ef9ad-131">Un valor de cadena fijo definido por el sistema.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-131">A fixed, system-defined string value.</span></span>|  
|`NATIVE_TYPE_OBJECTREF`|<span data-ttu-id="ef9ad-132">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-132">Obsolete.</span></span>|  
|`NATIVE_TYPE_IUNKNOWN`|<span data-ttu-id="ef9ad-133">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-133">COM Interop.</span></span>|  
|`NATIVE_TYPE_IDISPATCH`|<span data-ttu-id="ef9ad-134">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-134">COM Interop.</span></span>|  
|`NATIVE_TYPE_STRUCT`|<span data-ttu-id="ef9ad-135">Un valor de estructura nativa.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-135">A native structure value.</span></span>|  
|`NATIVE_TYPE_INTF`|<span data-ttu-id="ef9ad-136">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-136">COM Interop.</span></span>|  
|`NATIVE_TYPE_SAFEARRAY`|<span data-ttu-id="ef9ad-137">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-137">COM Interop.</span></span>|  
|`NATIVE_TYPE_FIXEDARRAY`|<span data-ttu-id="ef9ad-138">Un valor de matriz de longitud fija.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-138">A fixed-length array value.</span></span>|  
|`NATIVE_TYPE_INT`|<span data-ttu-id="ef9ad-139">Un valor entero nativo de 16 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-139">A native 16-bit signed integer value.</span></span>|  
|`NATIVE_TYPE_UINT`|<span data-ttu-id="ef9ad-140">Un valor entero nativo de 16 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-140">A native 16-bit unsigned integer value.</span></span>|  
|`NATIVE_TYPE_NESTEDSTRUCT`|<span data-ttu-id="ef9ad-141">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-141">Obsolete.</span></span><br /><br /> <span data-ttu-id="ef9ad-142">Usa NATIVE_TYPE_STRUCT.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-142">Use NATIVE_TYPE_STRUCT.</span></span>|  
|`NATIVE_TYPE_BYVALSTR`|<span data-ttu-id="ef9ad-143">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-143">COM Interop.</span></span>|  
|`NATIVE_TYPE_ANSIBSTR`|<span data-ttu-id="ef9ad-144">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-144">COM Interop.</span></span>|  
|`NATIVE_TYPE_TBSTR`|<span data-ttu-id="ef9ad-145">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-145">COM Interop.</span></span><br /><br /> <span data-ttu-id="ef9ad-146">Seleccione BSTR o ANSIBSTR dependiendo de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-146">Select BSTR or ANSIBSTR depending on the platform.</span></span>|  
|`NATIVE_TYPE_VARIANTBOOL`|<span data-ttu-id="ef9ad-147">Un valor booleano de 2 bytes, donde TRUE es -1 y FALSE es cero.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-147">A 2-byte Boolean value, where TRUE is -1 and FALSE is zero.</span></span>|  
|`NATIVE_TYPE_FUNC`|<span data-ttu-id="ef9ad-148">Puntero de función.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-148">A function pointer.</span></span>|  
|`NATIVE_TYPE_ASANY`|<span data-ttu-id="ef9ad-149">Una referencia a cualquier tipo nativo.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-149">A reference to any native type.</span></span>|  
|`NATIVE_TYPE_ARRAY`|<span data-ttu-id="ef9ad-150">Una referencia a una matriz con miembros de un tipo no especificado.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-150">A reference to an array with members of an unspecified type.</span></span>|  
|`NATIVE_TYPE_LPSTRUCT`|<span data-ttu-id="ef9ad-151">Un puntero entero de 32 bits a una estructura.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-151">A 32-bit integer pointer to a structure.</span></span>|  
|`NATIVE_TYPE_CUSTOMMARSHALER`|<span data-ttu-id="ef9ad-152">Un tipo nativo de serializador personalizado.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-152">A custom marshaler native type.</span></span><br /><br /> <span data-ttu-id="ef9ad-153">Esto debe ir seguido de una cadena con el siguiente formato: "Nombre de tipo nativo/0Nombre de tipo de serializador personalizado nombre/0Cookie opcional/0" o ".Nombre de tipo de cálculo de referencias personalizados nombre/0Cookie opcional/0"</span><span class="sxs-lookup"><span data-stu-id="ef9ad-153">This must be followed by a string of the following format: "Native type name/0Custom marshaler type name/0Optional cookie/0" or "{Native type GUID}/0Custom marshaler type name/0Optional cookie/0"</span></span>|  
|`NATIVE_TYPE_ERROR`|<span data-ttu-id="ef9ad-154">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-154">COM Interop.</span></span><br /><br /> <span data-ttu-id="ef9ad-155">Con ELEMENT_TYPE_I4 este tipo se asigna a VT_HRESULT.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-155">With ELEMENT_TYPE_I4 this type maps to VT_HRESULT.</span></span>|  
|`NATIVE_TYPE_IINSPECTABLE`|<span data-ttu-id="ef9ad-156">Un `IInspectable` tipo nativo.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-156">A native `IInspectable` type.</span></span>|  
|`NATIVE_TYPE_HSTRING`|<span data-ttu-id="ef9ad-157">Un `HString`nativo .</span><span class="sxs-lookup"><span data-stu-id="ef9ad-157">A native `HString`.</span></span>|  
|`NATIVE_TYPE_MAX`|<span data-ttu-id="ef9ad-158">Valor no válido.</span><span class="sxs-lookup"><span data-stu-id="ef9ad-158">An invalid value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ef9ad-159">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef9ad-159">Requirements</span></span>  
 <span data-ttu-id="ef9ad-160">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef9ad-160">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef9ad-161">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ef9ad-161">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ef9ad-162">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef9ad-162">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef9ad-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef9ad-163">See also</span></span>

- <xref:System.Runtime.InteropServices.UnmanagedType>
- [<span data-ttu-id="ef9ad-164">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="ef9ad-164">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
