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
ms.openlocfilehash: 17b7af7016cf88fd3ae263dd952502d515b0c833
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441558"
---
# <a name="corpinvokemap-enumeration"></a><span data-ttu-id="31bbd-102">CorPinvokeMap (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="31bbd-102">CorPinvokeMap Enumeration</span></span>
<span data-ttu-id="31bbd-103">Especifica las opciones de una llamada PInvoke.</span><span class="sxs-lookup"><span data-stu-id="31bbd-103">Specifies options for a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31bbd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31bbd-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="31bbd-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="31bbd-105">Members</span></span>  
  
|<span data-ttu-id="31bbd-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="31bbd-106">Member</span></span>|<span data-ttu-id="31bbd-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="31bbd-107">Description</span></span>|  
|------------|-----------------|  
|`pmNoMangle`|<span data-ttu-id="31bbd-108">Use cada nombre de miembro como se especifica.</span><span class="sxs-lookup"><span data-stu-id="31bbd-108">Use each member name as specified.</span></span>|  
|`pmCharSetMask`|<span data-ttu-id="31bbd-109">Reservado.</span><span class="sxs-lookup"><span data-stu-id="31bbd-109">Reserved.</span></span>|  
|`pmCharSetNotSpec`|<span data-ttu-id="31bbd-110">Reservado.</span><span class="sxs-lookup"><span data-stu-id="31bbd-110">Reserved.</span></span>|  
|`pmCharSetAnsi`|<span data-ttu-id="31bbd-111">Calcula las referencias de cadenas como cadenas de caracteres de varios bytes.</span><span class="sxs-lookup"><span data-stu-id="31bbd-111">Marshal strings as multiple-byte character strings.</span></span>|  
|`pmCharSetUnicode`|<span data-ttu-id="31bbd-112">Calcula las referencias de cadenas como caracteres Unicode de 2 bytes.</span><span class="sxs-lookup"><span data-stu-id="31bbd-112">Marshal strings as Unicode 2-byte characters.</span></span>|  
|`pmCharSetAuto`|<span data-ttu-id="31bbd-113">Calcula automáticamente las referencias de las cadenas para el sistema operativo de destino.</span><span class="sxs-lookup"><span data-stu-id="31bbd-113">Automatically marshal strings appropriately for the target operating system.</span></span> <span data-ttu-id="31bbd-114">El valor predeterminado es Unicode en Windows NT, Windows 2000, Windows XP y la familia Windows Server 2003. el valor predeterminado es ANSI en Windows 98 y Windows me.</span><span class="sxs-lookup"><span data-stu-id="31bbd-114">The default is Unicode on Windows NT, Windows 2000, Windows XP, and the Windows Server 2003 family; the default is ANSI on Windows 98 and Windows Me.</span></span>|  
|`pmBestFitUseAssem`|<span data-ttu-id="31bbd-115">Reservado.</span><span class="sxs-lookup"><span data-stu-id="31bbd-115">Reserved.</span></span>|  
|`pmBestFitEnabled`|<span data-ttu-id="31bbd-116">Realice la asignación con ajuste perfecto de caracteres Unicode que no tienen una coincidencia exacta en el juego de caracteres ANSI.</span><span class="sxs-lookup"><span data-stu-id="31bbd-116">Perform best-fit mapping of Unicode characters that lack an exact match in the ANSI character set.</span></span>|  
|`pmBestFitDisabled`|<span data-ttu-id="31bbd-117">No realice la asignación con ajuste perfecto de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="31bbd-117">Do not perform best-fit mapping of Unicode characters.</span></span> <span data-ttu-id="31bbd-118">En este caso, todos los caracteres no asignables se reemplazarán por un carácter "?".</span><span class="sxs-lookup"><span data-stu-id="31bbd-118">In this case, all unmappable characters will be replaced by a ‘?’.</span></span>|  
|`pmBestFitMask`|<span data-ttu-id="31bbd-119">Reservado.</span><span class="sxs-lookup"><span data-stu-id="31bbd-119">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharUseAssem`|<span data-ttu-id="31bbd-120">Reservado.</span><span class="sxs-lookup"><span data-stu-id="31bbd-120">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharEnabled`|<span data-ttu-id="31bbd-121">Produce una excepción cuando el serializador de interoperabilidad encuentra un carácter que no se pudo asignar.</span><span class="sxs-lookup"><span data-stu-id="31bbd-121">Throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharDisabled`|<span data-ttu-id="31bbd-122">No inicie una excepción cuando el serializador de interoperabilidad encuentre un carácter no asignable.</span><span class="sxs-lookup"><span data-stu-id="31bbd-122">Do not throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharMask`|<span data-ttu-id="31bbd-123">Reservada</span><span class="sxs-lookup"><span data-stu-id="31bbd-123">Reserved</span></span>|  
|`pmSupportsLastError`|<span data-ttu-id="31bbd-124">Permita que el destinatario llame a la función `SetLastError` de Win32 antes de volver del método con atributos.</span><span class="sxs-lookup"><span data-stu-id="31bbd-124">Allow the callee to call the Win32 `SetLastError` function before returning from the attributed method.</span></span>|  
|`pmCallConvMask`|<span data-ttu-id="31bbd-125">Reservada</span><span class="sxs-lookup"><span data-stu-id="31bbd-125">Reserved</span></span>|  
|`pmCallConvWinapi`|<span data-ttu-id="31bbd-126">Usar la Convención de llamada de plataforma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="31bbd-126">Use the default platform calling convention.</span></span> <span data-ttu-id="31bbd-127">Por ejemplo, en Windows, el valor predeterminado es `StdCall` y en Windows CE .NET es `Cdecl`.</span><span class="sxs-lookup"><span data-stu-id="31bbd-127">For example, on Windows the default is `StdCall` and on Windows CE .NET it is `Cdecl`.</span></span>|  
|`pmCallConvCdecl`|<span data-ttu-id="31bbd-128">Utilice la Convención de llamada de `Cdecl`.</span><span class="sxs-lookup"><span data-stu-id="31bbd-128">Use the `Cdecl` calling convention.</span></span> <span data-ttu-id="31bbd-129">En este caso, el autor de la llamada limpia la pila.</span><span class="sxs-lookup"><span data-stu-id="31bbd-129">In this case, the caller cleans the stack.</span></span> <span data-ttu-id="31bbd-130">Esto permite llamar a funciones con `varargs` (es decir, funciones que aceptan un número variable de parámetros).</span><span class="sxs-lookup"><span data-stu-id="31bbd-130">This enables calling functions with `varargs` (that is, functions that accept a variable number of parameters).</span></span>|  
|`pmCallConvStdcall`|<span data-ttu-id="31bbd-131">Utilice la Convención de llamada de `StdCall`.</span><span class="sxs-lookup"><span data-stu-id="31bbd-131">Use the `StdCall` calling convention.</span></span> <span data-ttu-id="31bbd-132">En este caso, el destinatario limpia la pila.</span><span class="sxs-lookup"><span data-stu-id="31bbd-132">In this case, the callee cleans the stack.</span></span> <span data-ttu-id="31bbd-133">Esta es la Convención predeterminada para llamar a funciones no administradas con invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="31bbd-133">This is the default convention for calling unmanaged functions with platform invoke.</span></span>|  
|`pmCallConvThiscall`|<span data-ttu-id="31bbd-134">Utilice la Convención de llamada de `ThisCall`.</span><span class="sxs-lookup"><span data-stu-id="31bbd-134">Use the `ThisCall` calling convention.</span></span> <span data-ttu-id="31bbd-135">En este caso, el primer parámetro es el puntero `this` y se almacena en la ECX de registro.</span><span class="sxs-lookup"><span data-stu-id="31bbd-135">In this case, the first parameter is the `this` pointer and is stored in register ECX.</span></span> <span data-ttu-id="31bbd-136">Otros parámetros se insertan en la pila.</span><span class="sxs-lookup"><span data-stu-id="31bbd-136">Other parameters are pushed on the stack.</span></span> <span data-ttu-id="31bbd-137">La Convención de llamada de `ThisCall` se usa para llamar a métodos en clases exportadas desde un archivo DLL no administrado.</span><span class="sxs-lookup"><span data-stu-id="31bbd-137">The `ThisCall` calling convention is used to call methods on classes exported from an unmanaged DLL.</span></span>|  
|`pmCallConvFastcall`|<span data-ttu-id="31bbd-138">Reservado.</span><span class="sxs-lookup"><span data-stu-id="31bbd-138">Reserved.</span></span>|  
|`pmMaxValue`|<span data-ttu-id="31bbd-139">Reservado.</span><span class="sxs-lookup"><span data-stu-id="31bbd-139">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="31bbd-140">Requisitos</span><span class="sxs-lookup"><span data-stu-id="31bbd-140">Requirements</span></span>  
 <span data-ttu-id="31bbd-141">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31bbd-141">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31bbd-142">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="31bbd-142">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="31bbd-143">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31bbd-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31bbd-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="31bbd-144">See also</span></span>

- [<span data-ttu-id="31bbd-145">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="31bbd-145">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
