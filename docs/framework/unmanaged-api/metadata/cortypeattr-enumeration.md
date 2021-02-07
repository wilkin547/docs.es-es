---
description: 'Más información sobre: enumeración Cortypeattr ('
title: CorTypeAttr (Enumeración)
ms.date: 03/30/2017
api_name:
- CorTypeAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTypeAttr
helpviewer_keywords:
- CorTypeAttr enumeration [.NET Framework metadata]
ms.assetid: 9bede0ec-5fdf-42a2-b5b7-bee64056acb6
topic_type:
- apiref
ms.openlocfilehash: d4f7d25ce8ead945790defae800b7a45dc88bc38
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721173"
---
# <a name="cortypeattr-enumeration"></a><span data-ttu-id="f3f06-103">CorTypeAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f3f06-103">CorTypeAttr Enumeration</span></span>

<span data-ttu-id="f3f06-104">Contiene valores que indican los metadatos de tipo.</span><span class="sxs-lookup"><span data-stu-id="f3f06-104">Contains values that indicate type metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3f06-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3f06-105">Syntax</span></span>  
  
```cpp  
typedef enum CorTypeAttr {  
  
    tdVisibilityMask        =   0x00000007,  
    tdNotPublic             =   0x00000000,  
    tdPublic                =   0x00000001,  
    tdNestedPublic          =   0x00000002,  
    tdNestedPrivate         =   0x00000003,  
    tdNestedFamily          =   0x00000004,  
    tdNestedAssembly        =   0x00000005,  
    tdNestedFamANDAssem     =   0x00000006,  
    tdNestedFamORAssem      =   0x00000007,  
  
    tdLayoutMask            =   0x00000018,  
    tdAutoLayout            =   0x00000000,  
    tdSequentialLayout      =   0x00000008,  
    tdExplicitLayout        =   0x00000010,  
  
    tdClassSemanticsMask    =   0x00000020,  
    tdClass                 =   0x00000000,  
    tdInterface             =   0x00000020,  
  
    tdAbstract              =   0x00000080,  
    tdSealed                =   0x00000100,  
    tdSpecialName           =   0x00000400,  
  
    tdImport                =   0x00001000,  
    tdSerializable          =   0x00002000,  
    tdWindowsRuntime        =   0x00004000,  
  
    tdStringFormatMask      =   0x00030000,  
    tdAnsiClass             =   0x00000000,  
    tdUnicodeClass          =   0x00010000,  
    tdAutoClass             =   0x00020000,  
    tdCustomFormatClass     =   0x00030000,  
    tdCustomFormatMask      =   0x00C00000,  
  
    tdBeforeFieldInit       =   0x00100000,  
    tdForwarder             =   0x00200000,  
  
    tdReservedMask          =   0x00040800,  
    tdRTSpecialName         =   0x00000800,  
    tdHasSecurity           =   0x00040000,  
  
} CorTypeAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="f3f06-106">Members</span><span class="sxs-lookup"><span data-stu-id="f3f06-106">Members</span></span>  
  
|<span data-ttu-id="f3f06-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="f3f06-107">Member</span></span>|<span data-ttu-id="f3f06-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3f06-108">Description</span></span>|  
|------------|-----------------|  
|`tdVisibilityMask`|<span data-ttu-id="f3f06-109">Se usa para la información de visibilidad del tipo.</span><span class="sxs-lookup"><span data-stu-id="f3f06-109">Used for type visibility information.</span></span>|  
|`tdNotPublic`|<span data-ttu-id="f3f06-110">Especifica que el tipo no está en el ámbito público.</span><span class="sxs-lookup"><span data-stu-id="f3f06-110">Specifies that the type is not in public scope.</span></span>|  
|`tdPublic`|<span data-ttu-id="f3f06-111">Especifica que el tipo está en el ámbito público.</span><span class="sxs-lookup"><span data-stu-id="f3f06-111">Specifies that the type is in public scope.</span></span>|  
|`tdNestedPublic`|<span data-ttu-id="f3f06-112">Especifica que el tipo se anida con visibilidad pública.</span><span class="sxs-lookup"><span data-stu-id="f3f06-112">Specifies that the type is nested with public visibility.</span></span>|  
|`tdNestedPrivate`|<span data-ttu-id="f3f06-113">Especifica que el tipo está anidado con visibilidad privada.</span><span class="sxs-lookup"><span data-stu-id="f3f06-113">Specifies that the type is nested with private visibility.</span></span>|  
|`tdNestedFamily`|<span data-ttu-id="f3f06-114">Especifica que el tipo está anidado con visibilidad de la familia.</span><span class="sxs-lookup"><span data-stu-id="f3f06-114">Specifies that the type is nested with family visibility.</span></span>|  
|`tdNestedAssembly`|<span data-ttu-id="f3f06-115">Especifica que el tipo está anidado con visibilidad de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f3f06-115">Specifies that the type is nested with assembly visibility.</span></span>|  
|`tdNestedFamANDAssem`|<span data-ttu-id="f3f06-116">Especifica que el tipo se anida con visibilidad de familia y ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f3f06-116">Specifies that the type is nested with family and assembly visibility.</span></span>|  
|`tdNestedFamORAssem`|<span data-ttu-id="f3f06-117">Especifica que el tipo se anida con visibilidad de familia o ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f3f06-117">Specifies that the type is nested with family or assembly visibility.</span></span>|  
|`tdLayoutMask`|<span data-ttu-id="f3f06-118">Obtiene información de diseño para el tipo.</span><span class="sxs-lookup"><span data-stu-id="f3f06-118">Gets layout information for the type.</span></span>|  
|`tdAutoLayout`|<span data-ttu-id="f3f06-119">Especifica que los campos de este tipo se colocan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f3f06-119">Specifies that the fields of this type are laid out automatically.</span></span>|  
|`tdSequentialLayout`|<span data-ttu-id="f3f06-120">Especifica que los campos de este tipo se disponen secuencialmente.</span><span class="sxs-lookup"><span data-stu-id="f3f06-120">Specifies that the fields of this type are laid out sequentially.</span></span>|  
|`tdExplicitLayout`|<span data-ttu-id="f3f06-121">Especifica que el diseño de campo se proporciona explícitamente.</span><span class="sxs-lookup"><span data-stu-id="f3f06-121">Specifies that field layout is supplied explicitly.</span></span>|  
|`tdClassSemanticsMask`|<span data-ttu-id="f3f06-122">Obtiene información semántica sobre el tipo.</span><span class="sxs-lookup"><span data-stu-id="f3f06-122">Gets semantic information about the type.</span></span>|  
|`tdClass`|<span data-ttu-id="f3f06-123">Especifica que el tipo es una clase.</span><span class="sxs-lookup"><span data-stu-id="f3f06-123">Specifies that the type is a class.</span></span>|  
|`tdInterface`|<span data-ttu-id="f3f06-124">Especifica que el tipo es una interfaz.</span><span class="sxs-lookup"><span data-stu-id="f3f06-124">Specifies that the type is an interface.</span></span>|  
|`tdAbstract`|<span data-ttu-id="f3f06-125">Especifica que el tipo es abstracto.</span><span class="sxs-lookup"><span data-stu-id="f3f06-125">Specifies that the type is abstract.</span></span>|  
|`tdSealed`|<span data-ttu-id="f3f06-126">Especifica que el tipo no se puede extender.</span><span class="sxs-lookup"><span data-stu-id="f3f06-126">Specifies that the type cannot be extended.</span></span>|  
|`tdSpecialName`|<span data-ttu-id="f3f06-127">Especifica que el nombre de la clase es especial.</span><span class="sxs-lookup"><span data-stu-id="f3f06-127">Specifies that the class name is special.</span></span> <span data-ttu-id="f3f06-128">Su nombre describe cómo.</span><span class="sxs-lookup"><span data-stu-id="f3f06-128">Its name describes how.</span></span>|  
|`tdImport`|<span data-ttu-id="f3f06-129">Especifica que el tipo se ha importado.</span><span class="sxs-lookup"><span data-stu-id="f3f06-129">Specifies that the type is imported.</span></span>|  
|`tdSerializable`|<span data-ttu-id="f3f06-130">Especifica que el tipo es serializable.</span><span class="sxs-lookup"><span data-stu-id="f3f06-130">Specifies that the type is serializable.</span></span>|  
|`tdWindowsRuntime`|<span data-ttu-id="f3f06-131">Especifica que este tipo es un tipo de Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="f3f06-131">Specifies that this type is a Windows Runtime type.</span></span>|  
|`tdStringFormatMask`|<span data-ttu-id="f3f06-132">Obtiene información sobre cómo se codifican y formatean las cadenas.</span><span class="sxs-lookup"><span data-stu-id="f3f06-132">Gets information about how strings are encoded and formatted.</span></span>|  
|`tdAnsiClass`|<span data-ttu-id="f3f06-133">Especifica que este tipo interpreta LPTSTR como ANSI.</span><span class="sxs-lookup"><span data-stu-id="f3f06-133">Specifies that this type interprets an LPTSTR as ANSI.</span></span>|  
|`tdUnicodeClass`|<span data-ttu-id="f3f06-134">Especifica que este tipo interpreta LPTSTR como Unicode.</span><span class="sxs-lookup"><span data-stu-id="f3f06-134">Specifies that this type interprets an LPTSTR as Unicode.</span></span>|  
|`tdAutoClass`|<span data-ttu-id="f3f06-135">Especifica que este tipo interpreta LPTSTR automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f3f06-135">Specifies that this type interprets an LPTSTR automatically.</span></span>|  
|`tdCustomFormatClass`|<span data-ttu-id="f3f06-136">Especifica que el tipo tiene una codificación no estándar, tal y como especifica `CustomFormatMask` .</span><span class="sxs-lookup"><span data-stu-id="f3f06-136">Specifies that the type has a non-standard encoding, as specified by `CustomFormatMask`.</span></span>|  
|`tdCustomFormatMask`|<span data-ttu-id="f3f06-137">Use esta máscara para obtener información de codificación no estándar para la interoperabilidad nativa.</span><span class="sxs-lookup"><span data-stu-id="f3f06-137">Use this mask to get non-standard encoding information for native interop.</span></span> <span data-ttu-id="f3f06-138">El significado de los valores de estos dos bits no se especifica.</span><span class="sxs-lookup"><span data-stu-id="f3f06-138">The meaning of the values of these two bits is unspecified.</span></span>|  
|`tdBeforeFieldInit`|<span data-ttu-id="f3f06-139">Especifica que el tipo se debe inicializar antes del primer intento de obtener acceso a un campo estático.</span><span class="sxs-lookup"><span data-stu-id="f3f06-139">Specifies that the type must be initialized before the first attempt to access a static field.</span></span>|  
|`tdForwarder`|<span data-ttu-id="f3f06-140">Especifica que el tipo se exporta y un reenviador de tipos.</span><span class="sxs-lookup"><span data-stu-id="f3f06-140">Specifies that the type is exported, and a type forwarder.</span></span>|  
|`tdReservedMask`|<span data-ttu-id="f3f06-141">El Common Language Runtime utiliza internamente esta marca y las marcas siguientes.</span><span class="sxs-lookup"><span data-stu-id="f3f06-141">This flag and the flags below are used internally by the common language runtime.</span></span>|  
|`tdRTSpecialName`|<span data-ttu-id="f3f06-142">Especifica que el Common Language Runtime debe comprobar la codificación del nombre.</span><span class="sxs-lookup"><span data-stu-id="f3f06-142">Specifies that the common language runtime should check the name encoding.</span></span>|  
|`tdHasSecurity`|<span data-ttu-id="f3f06-143">Especifica que el tipo tiene seguridad asociada.</span><span class="sxs-lookup"><span data-stu-id="f3f06-143">Specifies that the type has security associated with it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f3f06-144">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3f06-144">Requirements</span></span>  

 <span data-ttu-id="f3f06-145">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3f06-145">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3f06-146">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="f3f06-146">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f3f06-147">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3f06-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3f06-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3f06-148">See also</span></span>

- [<span data-ttu-id="f3f06-149">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="f3f06-149">Metadata Enumerations</span></span>](metadata-enumerations.md)
