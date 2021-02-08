---
description: 'Más información sobre: enumeración CorPinvokeMap ('
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
ms.openlocfilehash: 8285632725096b4e6afc85fe54a89f12fc899dd1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784267"
---
# <a name="corpinvokemap-enumeration"></a><span data-ttu-id="2ef3b-103">CorPinvokeMap (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="2ef3b-103">CorPinvokeMap Enumeration</span></span>

<span data-ttu-id="2ef3b-104">Especifica las opciones de una llamada PInvoke.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-104">Specifies options for a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ef3b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ef3b-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="2ef3b-106">Members</span><span class="sxs-lookup"><span data-stu-id="2ef3b-106">Members</span></span>  
  
|<span data-ttu-id="2ef3b-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="2ef3b-107">Member</span></span>|<span data-ttu-id="2ef3b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ef3b-108">Description</span></span>|  
|------------|-----------------|  
|`pmNoMangle`|<span data-ttu-id="2ef3b-109">Use cada nombre de miembro como se especifica.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-109">Use each member name as specified.</span></span>|  
|`pmCharSetMask`|<span data-ttu-id="2ef3b-110">Reservado.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-110">Reserved.</span></span>|  
|`pmCharSetNotSpec`|<span data-ttu-id="2ef3b-111">Reservado.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-111">Reserved.</span></span>|  
|`pmCharSetAnsi`|<span data-ttu-id="2ef3b-112">Calcula las referencias de las cadenas como cadenas de caracteres de varios bytes.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-112">Marshal strings as multiple-byte character strings.</span></span>|  
|`pmCharSetUnicode`|<span data-ttu-id="2ef3b-113">Calcula referencias de las cadenas como caracteres Unicode de 2 bytes.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-113">Marshal strings as Unicode 2-byte characters.</span></span>|  
|`pmCharSetAuto`|<span data-ttu-id="2ef3b-114">Calcula automáticamente las referencias de las cadenas como corresponde al sistema operativo de destino.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-114">Automatically marshal strings appropriately for the target operating system.</span></span> <span data-ttu-id="2ef3b-115">El valor predeterminado es Unicode en Windows NT, Windows 2000, Windows XP y la familia Windows Server 2003. el valor predeterminado es ANSI en Windows 98 y Windows me.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-115">The default is Unicode on Windows NT, Windows 2000, Windows XP, and the Windows Server 2003 family; the default is ANSI on Windows 98 and Windows Me.</span></span>|  
|`pmBestFitUseAssem`|<span data-ttu-id="2ef3b-116">Reservado.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-116">Reserved.</span></span>|  
|`pmBestFitEnabled`|<span data-ttu-id="2ef3b-117">Realice la asignación con ajuste perfecto de caracteres Unicode que no tienen una coincidencia exacta en el juego de caracteres ANSI.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-117">Perform best-fit mapping of Unicode characters that lack an exact match in the ANSI character set.</span></span>|  
|`pmBestFitDisabled`|<span data-ttu-id="2ef3b-118">No realice la asignación con ajuste perfecto de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-118">Do not perform best-fit mapping of Unicode characters.</span></span> <span data-ttu-id="2ef3b-119">En este caso, todos los caracteres no asignables se reemplazarán por un carácter "?".</span><span class="sxs-lookup"><span data-stu-id="2ef3b-119">In this case, all unmappable characters will be replaced by a ‘?’.</span></span>|  
|`pmBestFitMask`|<span data-ttu-id="2ef3b-120">Reservado.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-120">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharUseAssem`|<span data-ttu-id="2ef3b-121">Reservado.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-121">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharEnabled`|<span data-ttu-id="2ef3b-122">Produce una excepción cuando el serializador de interoperabilidad encuentra un carácter que no se pudo asignar.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-122">Throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharDisabled`|<span data-ttu-id="2ef3b-123">No inicie una excepción cuando el serializador de interoperabilidad encuentre un carácter no asignable.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-123">Do not throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharMask`|<span data-ttu-id="2ef3b-124">Reservado</span><span class="sxs-lookup"><span data-stu-id="2ef3b-124">Reserved</span></span>|  
|`pmSupportsLastError`|<span data-ttu-id="2ef3b-125">Permita que el destinatario llame a la `SetLastError` función de Win32 antes de volver del método con atributos.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-125">Allow the callee to call the Win32 `SetLastError` function before returning from the attributed method.</span></span>|  
|`pmCallConvMask`|<span data-ttu-id="2ef3b-126">Reservado</span><span class="sxs-lookup"><span data-stu-id="2ef3b-126">Reserved</span></span>|  
|`pmCallConvWinapi`|<span data-ttu-id="2ef3b-127">Usar la Convención de llamada de plataforma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-127">Use the default platform calling convention.</span></span> <span data-ttu-id="2ef3b-128">Por ejemplo, en Windows el valor predeterminado es `StdCall` y en Windows CE .net es `Cdecl` .</span><span class="sxs-lookup"><span data-stu-id="2ef3b-128">For example, on Windows the default is `StdCall` and on Windows CE .NET it is `Cdecl`.</span></span>|  
|`pmCallConvCdecl`|<span data-ttu-id="2ef3b-129">Utilice la `Cdecl` Convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-129">Use the `Cdecl` calling convention.</span></span> <span data-ttu-id="2ef3b-130">En este caso, el autor de la llamada limpia la pila.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-130">In this case, the caller cleans the stack.</span></span> <span data-ttu-id="2ef3b-131">Esto permite llamar a funciones con `varargs` (es decir, funciones que aceptan un número variable de parámetros).</span><span class="sxs-lookup"><span data-stu-id="2ef3b-131">This enables calling functions with `varargs` (that is, functions that accept a variable number of parameters).</span></span>|  
|`pmCallConvStdcall`|<span data-ttu-id="2ef3b-132">Utilice la `StdCall` Convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-132">Use the `StdCall` calling convention.</span></span> <span data-ttu-id="2ef3b-133">En este caso, el destinatario limpia la pila.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-133">In this case, the callee cleans the stack.</span></span> <span data-ttu-id="2ef3b-134">Esta es la convención predeterminada para la llamada a funciones no administradas con invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-134">This is the default convention for calling unmanaged functions with platform invoke.</span></span>|  
|`pmCallConvThiscall`|<span data-ttu-id="2ef3b-135">Utilice la `ThisCall` Convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-135">Use the `ThisCall` calling convention.</span></span> <span data-ttu-id="2ef3b-136">En este caso, el primer parámetro es el `this` puntero y se almacena en la ECx de registro.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-136">In this case, the first parameter is the `this` pointer and is stored in register ECX.</span></span> <span data-ttu-id="2ef3b-137">Los demás parámetros se insertan en la pila.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-137">Other parameters are pushed on the stack.</span></span> <span data-ttu-id="2ef3b-138">La `ThisCall` Convención de llamada se usa para llamar a métodos en clases exportadas desde un archivo dll no administrado.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-138">The `ThisCall` calling convention is used to call methods on classes exported from an unmanaged DLL.</span></span>|  
|`pmCallConvFastcall`|<span data-ttu-id="2ef3b-139">Reservado.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-139">Reserved.</span></span>|  
|`pmMaxValue`|<span data-ttu-id="2ef3b-140">Reservado.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-140">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2ef3b-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ef3b-141">Requirements</span></span>  

 <span data-ttu-id="2ef3b-142">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ef3b-142">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ef3b-143">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="2ef3b-143">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="2ef3b-144">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ef3b-144">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ef3b-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ef3b-145">See also</span></span>

- [<span data-ttu-id="2ef3b-146">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="2ef3b-146">Metadata Enumerations</span></span>](metadata-enumerations.md)
