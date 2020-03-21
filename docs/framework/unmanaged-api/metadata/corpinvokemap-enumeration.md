---
title: CorPinvokeMap (Enumeración)
ms.date: 03/30/2017
api_name:
- CorPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPinvokeMap
helpviewer_keywords:
- CorPinvokeMap enumeration [.NET Framework metadata]
ms.assetid: f14f986e-f6ce-42bc-aa23-18150c46d28c
topic_type:
- apiref
ms.openlocfilehash: 8216dc3030b18428ab52fbf8385d392f81057aa0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176154"
---
# <a name="corpinvokemap-enumeration"></a><span data-ttu-id="26e63-102">CorPinvokeMap (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="26e63-102">CorPinvokeMap Enumeration</span></span>
<span data-ttu-id="26e63-103">Especifica las opciones de una llamada PInvoke.</span><span class="sxs-lookup"><span data-stu-id="26e63-103">Specifies options for a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26e63-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26e63-104">Syntax</span></span>  
  
```cpp  
typedef enum  CorPinvokeMap {  
  
    pmNoMangle          = 0x0001,  
  
    pmCharSetMask       = 0x0006,  
    pmCharSetNotSpec    = 0x0000,  
    pmCharSetAnsi       = 0x0002,  
    pmCharSetUnicode    = 0x0004,  
    pmCharSetAuto       = 0x0006,  
  
    pmBestFitUseAssem   = 0x0000,  
    pmBestFitEnabled    = 0x0010,  
    pmBestFitDisabled   = 0x0020,  
    pmBestFitMask       = 0x0030,  
  
    pmThrowOnUnmappableCharUseAssem   = 0x0000,  
    pmThrowOnUnmappableCharEnabled    = 0x1000,  
    pmThrowOnUnmappableCharDisabled   = 0x2000,  
    pmThrowOnUnmappableCharMask       = 0x3000,  
  
    pmSupportsLastError = 0x0040,
  
    pmCallConvMask      = 0x0700,  
    pmCallConvWinapi    = 0x0100,  
    pmCallConvCdecl     = 0x0200,  
    pmCallConvStdcall   = 0x0300,  
    pmCallConvThiscall  = 0x0400,  
    pmCallConvFastcall  = 0x0500,  
  
    pmMaxValue          = 0xFFFF  
  
} CorPinvokeMap;  
```  
  
## <a name="members"></a><span data-ttu-id="26e63-105">Members</span><span class="sxs-lookup"><span data-stu-id="26e63-105">Members</span></span>  
  
|<span data-ttu-id="26e63-106">Member</span><span class="sxs-lookup"><span data-stu-id="26e63-106">Member</span></span>|<span data-ttu-id="26e63-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="26e63-107">Description</span></span>|  
|------------|-----------------|  
|`pmNoMangle`|<span data-ttu-id="26e63-108">Utilice cada nombre de miembro según lo especificado.</span><span class="sxs-lookup"><span data-stu-id="26e63-108">Use each member name as specified.</span></span>|  
|`pmCharSetMask`|<span data-ttu-id="26e63-109">Reservado.</span><span class="sxs-lookup"><span data-stu-id="26e63-109">Reserved.</span></span>|  
|`pmCharSetNotSpec`|<span data-ttu-id="26e63-110">Reservado.</span><span class="sxs-lookup"><span data-stu-id="26e63-110">Reserved.</span></span>|  
|`pmCharSetAnsi`|<span data-ttu-id="26e63-111">Calcula las referencias de las cadenas como cadenas de caracteres de varios bytes.</span><span class="sxs-lookup"><span data-stu-id="26e63-111">Marshal strings as multiple-byte character strings.</span></span>|  
|`pmCharSetUnicode`|<span data-ttu-id="26e63-112">Calcula referencias de las cadenas como caracteres Unicode de 2 bytes.</span><span class="sxs-lookup"><span data-stu-id="26e63-112">Marshal strings as Unicode 2-byte characters.</span></span>|  
|`pmCharSetAuto`|<span data-ttu-id="26e63-113">Calcula automáticamente las referencias de las cadenas como corresponde al sistema operativo de destino.</span><span class="sxs-lookup"><span data-stu-id="26e63-113">Automatically marshal strings appropriately for the target operating system.</span></span> <span data-ttu-id="26e63-114">El valor predeterminado es Unicode en Windows NT, Windows 2000, Windows XP y la familia Windows Server 2003; el valor predeterminado es ANSI en Windows 98 y Windows Me.</span><span class="sxs-lookup"><span data-stu-id="26e63-114">The default is Unicode on Windows NT, Windows 2000, Windows XP, and the Windows Server 2003 family; the default is ANSI on Windows 98 and Windows Me.</span></span>|  
|`pmBestFitUseAssem`|<span data-ttu-id="26e63-115">Reservado.</span><span class="sxs-lookup"><span data-stu-id="26e63-115">Reserved.</span></span>|  
|`pmBestFitEnabled`|<span data-ttu-id="26e63-116">Realice la asignación de mejor ajuste de caracteres Unicode que carecen de una coincidencia exacta en el juego de caracteres ANSI.</span><span class="sxs-lookup"><span data-stu-id="26e63-116">Perform best-fit mapping of Unicode characters that lack an exact match in the ANSI character set.</span></span>|  
|`pmBestFitDisabled`|<span data-ttu-id="26e63-117">No realice la asignación de mejor ajuste de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="26e63-117">Do not perform best-fit mapping of Unicode characters.</span></span> <span data-ttu-id="26e63-118">En este caso, todos los caracteres no manejables serán reemplazados por un '?'.</span><span class="sxs-lookup"><span data-stu-id="26e63-118">In this case, all unmappable characters will be replaced by a ‘?’.</span></span>|  
|`pmBestFitMask`|<span data-ttu-id="26e63-119">Reservado.</span><span class="sxs-lookup"><span data-stu-id="26e63-119">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharUseAssem`|<span data-ttu-id="26e63-120">Reservado.</span><span class="sxs-lookup"><span data-stu-id="26e63-120">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharEnabled`|<span data-ttu-id="26e63-121">Producir una excepción cuando el serializador de interoperabilidad encuentra un carácter que no se puede asignar.</span><span class="sxs-lookup"><span data-stu-id="26e63-121">Throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharDisabled`|<span data-ttu-id="26e63-122">No produzca una excepción cuando el serializador de interoperabilidad encuentre un carácter que no se pueda aplicar.</span><span class="sxs-lookup"><span data-stu-id="26e63-122">Do not throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharMask`|<span data-ttu-id="26e63-123">Reserved</span><span class="sxs-lookup"><span data-stu-id="26e63-123">Reserved</span></span>|  
|`pmSupportsLastError`|<span data-ttu-id="26e63-124">Permita que el destinatario llame `SetLastError` a la función Win32 antes de volver desde el método con atributos.</span><span class="sxs-lookup"><span data-stu-id="26e63-124">Allow the callee to call the Win32 `SetLastError` function before returning from the attributed method.</span></span>|  
|`pmCallConvMask`|<span data-ttu-id="26e63-125">Reserved</span><span class="sxs-lookup"><span data-stu-id="26e63-125">Reserved</span></span>|  
|`pmCallConvWinapi`|<span data-ttu-id="26e63-126">Use la convención de llamada de plataforma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="26e63-126">Use the default platform calling convention.</span></span> <span data-ttu-id="26e63-127">Por ejemplo, en Windows `StdCall` el valor predeterminado es `Cdecl`y en Windows CE .NET es .</span><span class="sxs-lookup"><span data-stu-id="26e63-127">For example, on Windows the default is `StdCall` and on Windows CE .NET it is `Cdecl`.</span></span>|  
|`pmCallConvCdecl`|<span data-ttu-id="26e63-128">Use `Cdecl` la convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="26e63-128">Use the `Cdecl` calling convention.</span></span> <span data-ttu-id="26e63-129">En este caso, el autor de la llamada limpia la pila.</span><span class="sxs-lookup"><span data-stu-id="26e63-129">In this case, the caller cleans the stack.</span></span> <span data-ttu-id="26e63-130">Esto permite llamar `varargs` a funciones con (es decir, funciones que aceptan un número variable de parámetros).</span><span class="sxs-lookup"><span data-stu-id="26e63-130">This enables calling functions with `varargs` (that is, functions that accept a variable number of parameters).</span></span>|  
|`pmCallConvStdcall`|<span data-ttu-id="26e63-131">Use `StdCall` la convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="26e63-131">Use the `StdCall` calling convention.</span></span> <span data-ttu-id="26e63-132">En este caso, el destinatario limpia la pila.</span><span class="sxs-lookup"><span data-stu-id="26e63-132">In this case, the callee cleans the stack.</span></span> <span data-ttu-id="26e63-133">Esta es la convención predeterminada para la llamada a funciones no administradas con invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="26e63-133">This is the default convention for calling unmanaged functions with platform invoke.</span></span>|  
|`pmCallConvThiscall`|<span data-ttu-id="26e63-134">Use `ThisCall` la convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="26e63-134">Use the `ThisCall` calling convention.</span></span> <span data-ttu-id="26e63-135">En este caso, el `this` primer parámetro es el puntero y se almacena en el registro ECX.</span><span class="sxs-lookup"><span data-stu-id="26e63-135">In this case, the first parameter is the `this` pointer and is stored in register ECX.</span></span> <span data-ttu-id="26e63-136">Los demás parámetros se insertan en la pila.</span><span class="sxs-lookup"><span data-stu-id="26e63-136">Other parameters are pushed on the stack.</span></span> <span data-ttu-id="26e63-137">La `ThisCall` convención de llamada se usa para llamar a métodos en clases exportadas desde un archivo DLL no administrado.</span><span class="sxs-lookup"><span data-stu-id="26e63-137">The `ThisCall` calling convention is used to call methods on classes exported from an unmanaged DLL.</span></span>|  
|`pmCallConvFastcall`|<span data-ttu-id="26e63-138">Reservado.</span><span class="sxs-lookup"><span data-stu-id="26e63-138">Reserved.</span></span>|  
|`pmMaxValue`|<span data-ttu-id="26e63-139">Reservado.</span><span class="sxs-lookup"><span data-stu-id="26e63-139">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="26e63-140">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26e63-140">Requirements</span></span>  
 <span data-ttu-id="26e63-141">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26e63-141">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26e63-142">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="26e63-142">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="26e63-143">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26e63-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26e63-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="26e63-144">See also</span></span>

- [<span data-ttu-id="26e63-145">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="26e63-145">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
