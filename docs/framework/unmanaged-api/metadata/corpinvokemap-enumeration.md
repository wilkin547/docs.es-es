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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 951941092f67f66c5b17c8ae592569c2a8e6a675
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045401"
---
# <a name="corpinvokemap-enumeration"></a><span data-ttu-id="22570-102">CorPinvokeMap (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="22570-102">CorPinvokeMap Enumeration</span></span>
<span data-ttu-id="22570-103">Especifica opciones para una llamada PInvoke.</span><span class="sxs-lookup"><span data-stu-id="22570-103">Specifies options for a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22570-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22570-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="22570-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="22570-105">Members</span></span>  
  
|<span data-ttu-id="22570-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="22570-106">Member</span></span>|<span data-ttu-id="22570-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="22570-107">Description</span></span>|  
|------------|-----------------|  
|`pmNoMangle`|<span data-ttu-id="22570-108">Use cada nombre de miembro especificada.</span><span class="sxs-lookup"><span data-stu-id="22570-108">Use each member name as specified.</span></span>|  
|`pmCharSetMask`|<span data-ttu-id="22570-109">Reservado.</span><span class="sxs-lookup"><span data-stu-id="22570-109">Reserved.</span></span>|  
|`pmCharSetNotSpec`|<span data-ttu-id="22570-110">Reservado.</span><span class="sxs-lookup"><span data-stu-id="22570-110">Reserved.</span></span>|  
|`pmCharSetAnsi`|<span data-ttu-id="22570-111">Calcular las referencias de cadenas como cadenas de caracteres de varios bytes.</span><span class="sxs-lookup"><span data-stu-id="22570-111">Marshal strings as multiple-byte character strings.</span></span>|  
|`pmCharSetUnicode`|<span data-ttu-id="22570-112">Calcular las referencias de cadenas como caracteres de 2 bytes Unicode.</span><span class="sxs-lookup"><span data-stu-id="22570-112">Marshal strings as Unicode 2-byte characters.</span></span>|  
|`pmCharSetAuto`|<span data-ttu-id="22570-113">Serializar automáticamente las cadenas de forma apropiada para el sistema operativo de destino.</span><span class="sxs-lookup"><span data-stu-id="22570-113">Automatically marshal strings appropriately for the target operating system.</span></span> <span data-ttu-id="22570-114">El valor predeterminado es Unicode en Windows NT, Windows 2000, Windows XP y la familia Windows Server 2003; el valor predeterminado es ANSI en Windows 98 y Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="22570-114">The default is Unicode on Windows NT, Windows 2000, Windows XP, and the Windows Server 2003 family; the default is ANSI on Windows 98 and Windows Me.</span></span>|  
|`pmBestFitUseAssem`|<span data-ttu-id="22570-115">Reservado.</span><span class="sxs-lookup"><span data-stu-id="22570-115">Reserved.</span></span>|  
|`pmBestFitEnabled`|<span data-ttu-id="22570-116">Realizar una asignación con ajuste perfecto de caracteres Unicode que no tienen a una coincidencia exacta en el juego de caracteres ANSI.</span><span class="sxs-lookup"><span data-stu-id="22570-116">Perform best-fit mapping of Unicode characters that lack an exact match in the ANSI character set.</span></span>|  
|`pmBestFitDisabled`|<span data-ttu-id="22570-117">No realice la asignación con ajuste perfecto de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="22570-117">Do not perform best-fit mapping of Unicode characters.</span></span> <span data-ttu-id="22570-118">En este caso, se reemplazará por todos los caracteres no se puede asignar un '?'.</span><span class="sxs-lookup"><span data-stu-id="22570-118">In this case, all unmappable characters will be replaced by a ‘?’.</span></span>|  
|`pmBestFitMask`|<span data-ttu-id="22570-119">Reservado.</span><span class="sxs-lookup"><span data-stu-id="22570-119">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharUseAssem`|<span data-ttu-id="22570-120">Reservado.</span><span class="sxs-lookup"><span data-stu-id="22570-120">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharEnabled`|<span data-ttu-id="22570-121">Produce una excepción cuando el serializador de interoperabilidad encuentra un carácter no se puede asignar.</span><span class="sxs-lookup"><span data-stu-id="22570-121">Throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharDisabled`|<span data-ttu-id="22570-122">No producen una excepción cuando el serializador de interoperabilidad encuentra un carácter no asignable.</span><span class="sxs-lookup"><span data-stu-id="22570-122">Do not throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharMask`|<span data-ttu-id="22570-123">Reservada</span><span class="sxs-lookup"><span data-stu-id="22570-123">Reserved</span></span>|  
|`pmSupportsLastError`|<span data-ttu-id="22570-124">Permitir que el destinatario llamar a Win32 `SetLastError` función antes de volver del método con atributos.</span><span class="sxs-lookup"><span data-stu-id="22570-124">Allow the callee to call the Win32 `SetLastError` function before returning from the attributed method.</span></span>|  
|`pmCallConvMask`|<span data-ttu-id="22570-125">Reservada</span><span class="sxs-lookup"><span data-stu-id="22570-125">Reserved</span></span>|  
|`pmCallConvWinapi`|<span data-ttu-id="22570-126">Use la convención de llamada de plataforma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="22570-126">Use the default platform calling convention.</span></span> <span data-ttu-id="22570-127">Por ejemplo, en Windows, el valor predeterminado es `StdCall` y en Windows CE .NET es `Cdecl`.</span><span class="sxs-lookup"><span data-stu-id="22570-127">For example, on Windows the default is `StdCall` and on Windows CE .NET it is `Cdecl`.</span></span>|  
|`pmCallConvCdecl`|<span data-ttu-id="22570-128">Use el `Cdecl` convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="22570-128">Use the `Cdecl` calling convention.</span></span> <span data-ttu-id="22570-129">En este caso, el llamador limpia la pila.</span><span class="sxs-lookup"><span data-stu-id="22570-129">In this case, the caller cleans the stack.</span></span> <span data-ttu-id="22570-130">Esto permite llamar a funciones con `varargs` (es decir, las funciones que aceptan un número variable de parámetros).</span><span class="sxs-lookup"><span data-stu-id="22570-130">This enables calling functions with `varargs` (that is, functions that accept a variable number of parameters).</span></span>|  
|`pmCallConvStdcall`|<span data-ttu-id="22570-131">Use el `StdCall` convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="22570-131">Use the `StdCall` calling convention.</span></span> <span data-ttu-id="22570-132">En este caso, el destinatario limpia la pila.</span><span class="sxs-lookup"><span data-stu-id="22570-132">In this case, the callee cleans the stack.</span></span> <span data-ttu-id="22570-133">Esta es la convención predeterminada para llamar a funciones no administradas con platform invoke.</span><span class="sxs-lookup"><span data-stu-id="22570-133">This is the default convention for calling unmanaged functions with platform invoke.</span></span>|  
|`pmCallConvThiscall`|<span data-ttu-id="22570-134">Use el `ThisCall` convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="22570-134">Use the `ThisCall` calling convention.</span></span> <span data-ttu-id="22570-135">En este caso, el primer parámetro es el `this` puntero y se almacena en ECX.</span><span class="sxs-lookup"><span data-stu-id="22570-135">In this case, the first parameter is the `this` pointer and is stored in register ECX.</span></span> <span data-ttu-id="22570-136">Otros parámetros se insertan en la pila.</span><span class="sxs-lookup"><span data-stu-id="22570-136">Other parameters are pushed on the stack.</span></span> <span data-ttu-id="22570-137">El `ThisCall` convención de llamada se usa para llamar a métodos en clases exportadas desde una DLL no administrada.</span><span class="sxs-lookup"><span data-stu-id="22570-137">The `ThisCall` calling convention is used to call methods on classes exported from an unmanaged DLL.</span></span>|  
|`pmCallConvFastcall`|<span data-ttu-id="22570-138">Reservado.</span><span class="sxs-lookup"><span data-stu-id="22570-138">Reserved.</span></span>|  
|`pmMaxValue`|<span data-ttu-id="22570-139">Reservado.</span><span class="sxs-lookup"><span data-stu-id="22570-139">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="22570-140">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22570-140">Requirements</span></span>  
 <span data-ttu-id="22570-141">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22570-141">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22570-142">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="22570-142">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="22570-143">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22570-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22570-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="22570-144">See also</span></span>

- [<span data-ttu-id="22570-145">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="22570-145">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
