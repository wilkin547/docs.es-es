---
description: 'Más información sobre: enumeración Cornativetype ('
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
ms.openlocfilehash: d2313eef124f3308c4792b47da8b7c8bba984597
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784332"
---
# <a name="cornativetype-enumeration"></a><span data-ttu-id="54748-103">CorNativeType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="54748-103">CorNativeType Enumeration</span></span>

<span data-ttu-id="54748-104">Contiene valores que describen los tipos nativos no administrados.</span><span class="sxs-lookup"><span data-stu-id="54748-104">Contains values that describe native unmanaged types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54748-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54748-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="54748-106">Members</span><span class="sxs-lookup"><span data-stu-id="54748-106">Members</span></span>  
  
|<span data-ttu-id="54748-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="54748-107">Member</span></span>|<span data-ttu-id="54748-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="54748-108">Description</span></span>|  
|------------|-----------------|  
|`NATIVE_TYPE_END`|<span data-ttu-id="54748-109">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="54748-109">Obsolete.</span></span>|  
|`NATIVE_TYPE_VOID`|<span data-ttu-id="54748-110">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="54748-110">Obsolete.</span></span>|  
|`NATIVE_TYPE_BOOLEAN`|<span data-ttu-id="54748-111">Valor booleano de 4 bytes, donde TRUE es distinto de cero y FALSE es cero.</span><span class="sxs-lookup"><span data-stu-id="54748-111">A 4-byte Boolean value, where TRUE is non-zero and FALSE is zero.</span></span>|  
|`NATIVE_TYPE_I1`|<span data-ttu-id="54748-112">Valor entero de 8 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="54748-112">A signed 8-bit integer value.</span></span>|  
|`NATIVE_TYPE_U1`|<span data-ttu-id="54748-113">Valor entero de 8 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="54748-113">An unsigned 8-bit integer value.</span></span>|  
|`NATIVE_TYPE_I2`|<span data-ttu-id="54748-114">Valor entero de 16 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="54748-114">A signed 16-bit integer value.</span></span>|  
|`NATIVE_TYPE_U2`|<span data-ttu-id="54748-115">Valor entero de 16 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="54748-115">An unsigned 16-bit integer value.</span></span>|  
|`NATIVE_TYPE_I4`|<span data-ttu-id="54748-116">Un valor entero de 32 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="54748-116">A signed 32-bit integer value.</span></span>|  
|`NATIVE_TYPE_U4`|<span data-ttu-id="54748-117">Valor entero de 32 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="54748-117">An unsigned 32-bit integer value.</span></span>|  
|`NATIVE_TYPE_I8`|<span data-ttu-id="54748-118">Valor entero de 64 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="54748-118">A signed 64-bit integer value.</span></span>|  
|`NATIVE_TYPE_U8`|<span data-ttu-id="54748-119">Valor entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="54748-119">An unsigned 64-bit integer value.</span></span>|  
|`NATIVE_TYPE_R4`|<span data-ttu-id="54748-120">Valor numérico de punto flotante de 4 bytes.</span><span class="sxs-lookup"><span data-stu-id="54748-120">A 4-byte floating-point numeric value.</span></span>|  
|`NATIVE_TYPE_R8`|<span data-ttu-id="54748-121">Valor numérico de punto flotante de 8 bytes.</span><span class="sxs-lookup"><span data-stu-id="54748-121">An 8-byte floating-point numeric value.</span></span>|  
|`NATIVE_TYPE_SYSCHAR`|<span data-ttu-id="54748-122">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="54748-122">Obsolete.</span></span>|  
|`NATIVE_TYPE_VARIANT`|<span data-ttu-id="54748-123">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="54748-123">Obsolete.</span></span>|  
|`NATIVE_TYPE_CURRENCY`|<span data-ttu-id="54748-124">Tipo COM numérico que corresponde al <xref:System.Decimal> tipo administrado.</span><span class="sxs-lookup"><span data-stu-id="54748-124">A numeric COM type that corresponds to the managed <xref:System.Decimal> type.</span></span>|  
|`NATIVE_TYPE_PTR`|<span data-ttu-id="54748-125">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="54748-125">Obsolete.</span></span>|  
|`NATIVE_TYPE_DECIMAL`|<span data-ttu-id="54748-126">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="54748-126">Obsolete.</span></span>|  
|`NATIVE_TYPE_DATE`|<span data-ttu-id="54748-127">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="54748-127">Obsolete.</span></span>|  
|`NATIVE_TYPE_BSTR`|<span data-ttu-id="54748-128">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="54748-128">COM Interop.</span></span>|  
|`NATIVE_TYPE_LPSTR`|<span data-ttu-id="54748-129">Valor de cadena LPSTR.</span><span class="sxs-lookup"><span data-stu-id="54748-129">An LPSTR string value.</span></span>|  
|`NATIVE_TYPE_LPWSTR`|<span data-ttu-id="54748-130">Valor de cadena LPWSTR.</span><span class="sxs-lookup"><span data-stu-id="54748-130">An LPWSTR string value.</span></span>|  
|`NATIVE_TYPE_LPTSTR`|<span data-ttu-id="54748-131">Valor de cadena LPTSTR.</span><span class="sxs-lookup"><span data-stu-id="54748-131">An LPTSTR string value.</span></span>|  
|`NATIVE_TYPE_FIXEDSYSSTRING`|<span data-ttu-id="54748-132">Valor de cadena fijo definido por el sistema.</span><span class="sxs-lookup"><span data-stu-id="54748-132">A fixed, system-defined string value.</span></span>|  
|`NATIVE_TYPE_OBJECTREF`|<span data-ttu-id="54748-133">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="54748-133">Obsolete.</span></span>|  
|`NATIVE_TYPE_IUNKNOWN`|<span data-ttu-id="54748-134">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="54748-134">COM Interop.</span></span>|  
|`NATIVE_TYPE_IDISPATCH`|<span data-ttu-id="54748-135">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="54748-135">COM Interop.</span></span>|  
|`NATIVE_TYPE_STRUCT`|<span data-ttu-id="54748-136">Valor de estructura nativa.</span><span class="sxs-lookup"><span data-stu-id="54748-136">A native structure value.</span></span>|  
|`NATIVE_TYPE_INTF`|<span data-ttu-id="54748-137">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="54748-137">COM Interop.</span></span>|  
|`NATIVE_TYPE_SAFEARRAY`|<span data-ttu-id="54748-138">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="54748-138">COM Interop.</span></span>|  
|`NATIVE_TYPE_FIXEDARRAY`|<span data-ttu-id="54748-139">Valor de matriz de longitud fija.</span><span class="sxs-lookup"><span data-stu-id="54748-139">A fixed-length array value.</span></span>|  
|`NATIVE_TYPE_INT`|<span data-ttu-id="54748-140">Valor entero de 16 bits con signo nativo.</span><span class="sxs-lookup"><span data-stu-id="54748-140">A native 16-bit signed integer value.</span></span>|  
|`NATIVE_TYPE_UINT`|<span data-ttu-id="54748-141">Valor entero de 16 bits sin signo nativo.</span><span class="sxs-lookup"><span data-stu-id="54748-141">A native 16-bit unsigned integer value.</span></span>|  
|`NATIVE_TYPE_NESTEDSTRUCT`|<span data-ttu-id="54748-142">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="54748-142">Obsolete.</span></span><br /><br /> <span data-ttu-id="54748-143">Use NATIVE_TYPE_STRUCT.</span><span class="sxs-lookup"><span data-stu-id="54748-143">Use NATIVE_TYPE_STRUCT.</span></span>|  
|`NATIVE_TYPE_BYVALSTR`|<span data-ttu-id="54748-144">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="54748-144">COM Interop.</span></span>|  
|`NATIVE_TYPE_ANSIBSTR`|<span data-ttu-id="54748-145">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="54748-145">COM Interop.</span></span>|  
|`NATIVE_TYPE_TBSTR`|<span data-ttu-id="54748-146">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="54748-146">COM Interop.</span></span><br /><br /> <span data-ttu-id="54748-147">Seleccione BSTR o ANSIBSTR en función de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="54748-147">Select BSTR or ANSIBSTR depending on the platform.</span></span>|  
|`NATIVE_TYPE_VARIANTBOOL`|<span data-ttu-id="54748-148">Valor booleano de 2 bytes, donde TRUE es-1 y FALSE es cero.</span><span class="sxs-lookup"><span data-stu-id="54748-148">A 2-byte Boolean value, where TRUE is -1 and FALSE is zero.</span></span>|  
|`NATIVE_TYPE_FUNC`|<span data-ttu-id="54748-149">Puntero de función.</span><span class="sxs-lookup"><span data-stu-id="54748-149">A function pointer.</span></span>|  
|`NATIVE_TYPE_ASANY`|<span data-ttu-id="54748-150">Referencia a cualquier tipo nativo.</span><span class="sxs-lookup"><span data-stu-id="54748-150">A reference to any native type.</span></span>|  
|`NATIVE_TYPE_ARRAY`|<span data-ttu-id="54748-151">Referencia a una matriz con miembros de un tipo no especificado.</span><span class="sxs-lookup"><span data-stu-id="54748-151">A reference to an array with members of an unspecified type.</span></span>|  
|`NATIVE_TYPE_LPSTRUCT`|<span data-ttu-id="54748-152">Un puntero entero de 32 bits a una estructura.</span><span class="sxs-lookup"><span data-stu-id="54748-152">A 32-bit integer pointer to a structure.</span></span>|  
|`NATIVE_TYPE_CUSTOMMARSHALER`|<span data-ttu-id="54748-153">Un tipo nativo de contador de referencias personalizado.</span><span class="sxs-lookup"><span data-stu-id="54748-153">A custom marshaler native type.</span></span><br /><br /> <span data-ttu-id="54748-154">Debe ir seguido de una cadena con el formato siguiente: "nombre de tipo nativo/nombre de tipo de contador de referencias de 0Custom/cookie de 0Optional/0" o "{GUID de tipo nativo}/0Custom de contador de referencias nombre de tipo/0Optional cookie/0"</span><span class="sxs-lookup"><span data-stu-id="54748-154">This must be followed by a string of the following format: "Native type name/0Custom marshaler type name/0Optional cookie/0" or "{Native type GUID}/0Custom marshaler type name/0Optional cookie/0"</span></span>|  
|`NATIVE_TYPE_ERROR`|<span data-ttu-id="54748-155">Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="54748-155">COM Interop.</span></span><br /><br /> <span data-ttu-id="54748-156">Con ELEMENT_TYPE_I4 este tipo se asigna a VT_HRESULT.</span><span class="sxs-lookup"><span data-stu-id="54748-156">With ELEMENT_TYPE_I4 this type maps to VT_HRESULT.</span></span>|  
|`NATIVE_TYPE_IINSPECTABLE`|<span data-ttu-id="54748-157">Tipo nativo `IInspectable` .</span><span class="sxs-lookup"><span data-stu-id="54748-157">A native `IInspectable` type.</span></span>|  
|`NATIVE_TYPE_HSTRING`|<span data-ttu-id="54748-158">Un nativo `HString` .</span><span class="sxs-lookup"><span data-stu-id="54748-158">A native `HString`.</span></span>|  
|`NATIVE_TYPE_MAX`|<span data-ttu-id="54748-159">Valor no válido.</span><span class="sxs-lookup"><span data-stu-id="54748-159">An invalid value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="54748-160">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54748-160">Requirements</span></span>  

 <span data-ttu-id="54748-161">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54748-161">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54748-162">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="54748-162">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="54748-163">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54748-163">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54748-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="54748-164">See also</span></span>

- <xref:System.Runtime.InteropServices.UnmanagedType>
- [<span data-ttu-id="54748-165">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="54748-165">Metadata Enumerations</span></span>](metadata-enumerations.md)
