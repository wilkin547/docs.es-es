---
title: "CorTypeAttr (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 501488c0ac03ebf508145572ed73163d7940bfbd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="cortypeattr-enumeration"></a><span data-ttu-id="9f504-102">CorTypeAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="9f504-102">CorTypeAttr Enumeration</span></span>
<span data-ttu-id="9f504-103">Contiene valores que indican los metadatos de tipo.</span><span class="sxs-lookup"><span data-stu-id="9f504-103">Contains values that indicate type metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f504-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f504-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="9f504-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9f504-105">Members</span></span>  
  
|<span data-ttu-id="9f504-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9f504-106">Member</span></span>|<span data-ttu-id="9f504-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f504-107">Description</span></span>|  
|------------|-----------------|  
|`tdVisibilityMask`|<span data-ttu-id="9f504-108">Se utiliza para obtener información de visibilidad del tipo.</span><span class="sxs-lookup"><span data-stu-id="9f504-108">Used for type visibility information.</span></span>|  
|`tdNotPublic`|<span data-ttu-id="9f504-109">Especifica que el tipo no está en ámbito público.</span><span class="sxs-lookup"><span data-stu-id="9f504-109">Specifies that the type is not in public scope.</span></span>|  
|`tdPublic`|<span data-ttu-id="9f504-110">Especifica que el tipo está en ámbito público.</span><span class="sxs-lookup"><span data-stu-id="9f504-110">Specifies that the type is in public scope.</span></span>|  
|`tdNestedPublic`|<span data-ttu-id="9f504-111">Especifica que el tipo se anida con visibilidad pública.</span><span class="sxs-lookup"><span data-stu-id="9f504-111">Specifies that the type is nested with public visibility.</span></span>|  
|`tdNestedPrivate`|<span data-ttu-id="9f504-112">Especifica que el tipo se anida con visibilidad privada.</span><span class="sxs-lookup"><span data-stu-id="9f504-112">Specifies that the type is nested with private visibility.</span></span>|  
|`tdNestedFamily`|<span data-ttu-id="9f504-113">Especifica que el tipo se anida con visibilidad de familia.</span><span class="sxs-lookup"><span data-stu-id="9f504-113">Specifies that the type is nested with family visibility.</span></span>|  
|`tdNestedAssembly`|<span data-ttu-id="9f504-114">Especifica que el tipo se anida con visibilidad de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9f504-114">Specifies that the type is nested with assembly visibility.</span></span>|  
|`tdNestedFamANDAssem`|<span data-ttu-id="9f504-115">Especifica que el tipo se anida con visibilidad de familia y ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9f504-115">Specifies that the type is nested with family and assembly visibility.</span></span>|  
|`tdNestedFamORAssem`|<span data-ttu-id="9f504-116">Especifica que el tipo se anida con visibilidad de familia o ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9f504-116">Specifies that the type is nested with family or assembly visibility.</span></span>|  
|`tdLayoutMask`|<span data-ttu-id="9f504-117">Obtiene información de diseño para el tipo.</span><span class="sxs-lookup"><span data-stu-id="9f504-117">Gets layout information for the type.</span></span>|  
|`tdAutoLayout`|<span data-ttu-id="9f504-118">Especifica que los campos de este tipo se distribuyen automáticamente.</span><span class="sxs-lookup"><span data-stu-id="9f504-118">Specifies that the fields of this type are laid out automatically.</span></span>|  
|`tdSequentialLayout`|<span data-ttu-id="9f504-119">Especifica que los campos de este tipo se disponen secuencialmente.</span><span class="sxs-lookup"><span data-stu-id="9f504-119">Specifies that the fields of this type are laid out sequentially.</span></span>|  
|`tdExplicitLayout`|<span data-ttu-id="9f504-120">Especifica el que diseño de los campos se proporciona explícitamente.</span><span class="sxs-lookup"><span data-stu-id="9f504-120">Specifies that field layout is supplied explicitly.</span></span>|  
|`tdClassSemanticsMask`|<span data-ttu-id="9f504-121">Obtiene información semántica sobre el tipo.</span><span class="sxs-lookup"><span data-stu-id="9f504-121">Gets semantic information about the type.</span></span>|  
|`tdClass`|<span data-ttu-id="9f504-122">Especifica que el tipo es una clase.</span><span class="sxs-lookup"><span data-stu-id="9f504-122">Specifies that the type is a class.</span></span>|  
|`tdInterface`|<span data-ttu-id="9f504-123">Especifica que el tipo es una interfaz.</span><span class="sxs-lookup"><span data-stu-id="9f504-123">Specifies that the type is an interface.</span></span>|  
|`tdAbstract`|<span data-ttu-id="9f504-124">Especifica que el tipo es abstracto.</span><span class="sxs-lookup"><span data-stu-id="9f504-124">Specifies that the type is abstract.</span></span>|  
|`tdSealed`|<span data-ttu-id="9f504-125">Especifica que no se puede ampliar el tipo.</span><span class="sxs-lookup"><span data-stu-id="9f504-125">Specifies that the type cannot be extended.</span></span>|  
|`tdSpecialName`|<span data-ttu-id="9f504-126">Especifica que el nombre de clase es especial.</span><span class="sxs-lookup"><span data-stu-id="9f504-126">Specifies that the class name is special.</span></span> <span data-ttu-id="9f504-127">Su nombre describe cómo.</span><span class="sxs-lookup"><span data-stu-id="9f504-127">Its name describes how.</span></span>|  
|`tdImport`|<span data-ttu-id="9f504-128">Especifica que el tipo se ha importado.</span><span class="sxs-lookup"><span data-stu-id="9f504-128">Specifies that the type is imported.</span></span>|  
|`tdSerializable`|<span data-ttu-id="9f504-129">Especifica que el tipo es serializable.</span><span class="sxs-lookup"><span data-stu-id="9f504-129">Specifies that the type is serializable.</span></span>|  
|`tdWindowsRuntime`|<span data-ttu-id="9f504-130">Especifica que este tipo es un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipo.</span><span class="sxs-lookup"><span data-stu-id="9f504-130">Specifies that this type is a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`tdStringFormatMask`|<span data-ttu-id="9f504-131">Obtiene información acerca de cómo las cadenas están codificadas y con formato.</span><span class="sxs-lookup"><span data-stu-id="9f504-131">Gets information about how strings are encoded and formatted.</span></span>|  
|`tdAnsiClass`|<span data-ttu-id="9f504-132">Especifica que este tipo interpreta LPTSTR como ANSI.</span><span class="sxs-lookup"><span data-stu-id="9f504-132">Specifies that this type interprets an LPTSTR as ANSI.</span></span>|  
|`tdUnicodeClass`|<span data-ttu-id="9f504-133">Especifica que este tipo interpreta LPTSTR como Unicode.</span><span class="sxs-lookup"><span data-stu-id="9f504-133">Specifies that this type interprets an LPTSTR as Unicode.</span></span>|  
|`tdAutoClass`|<span data-ttu-id="9f504-134">Especifica que este tipo interpreta LPTSTR automáticamente.</span><span class="sxs-lookup"><span data-stu-id="9f504-134">Specifies that this type interprets an LPTSTR automatically.</span></span>|  
|`tdCustomFormatClass`|<span data-ttu-id="9f504-135">Especifica que el tipo tiene una codificación no estándar, tal y como especifica `CustomFormatMask`.</span><span class="sxs-lookup"><span data-stu-id="9f504-135">Specifies that the type has a non-standard encoding, as specified by `CustomFormatMask`.</span></span>|  
|`tdCustomFormatMask`|<span data-ttu-id="9f504-136">Esta máscara se usa para obtener información de codificación no estándar para la interoperabilidad nativa.</span><span class="sxs-lookup"><span data-stu-id="9f504-136">Use this mask to get non-standard encoding information for native interop.</span></span> <span data-ttu-id="9f504-137">El significado de los valores de estos dos bits no está especificado.</span><span class="sxs-lookup"><span data-stu-id="9f504-137">The meaning of the values of these two bits is unspecified.</span></span>|  
|`tdBeforeFieldInit`|<span data-ttu-id="9f504-138">Especifica que el tipo se debe inicializar antes del primer intento para tener acceso a un campo estático.</span><span class="sxs-lookup"><span data-stu-id="9f504-138">Specifies that the type must be initialized before the first attempt to access a static field.</span></span>|  
|`tdForwarder`|<span data-ttu-id="9f504-139">Especifica que se exporta el tipo y un reenviador de tipos.</span><span class="sxs-lookup"><span data-stu-id="9f504-139">Specifies that the type is exported, and a type forwarder.</span></span>|  
|`tdReservedMask`|<span data-ttu-id="9f504-140">Common language runtime utiliza internamente esta marca y los indicadores siguientes.</span><span class="sxs-lookup"><span data-stu-id="9f504-140">This flag and the flags below are used internally by the common language runtime.</span></span>|  
|`tdRTSpecialName`|<span data-ttu-id="9f504-141">Especifica que common language runtime debe comprobar la codificación de nombres.</span><span class="sxs-lookup"><span data-stu-id="9f504-141">Specifies that the common language runtime should check the name encoding.</span></span>|  
|`tdHasSecurity`|<span data-ttu-id="9f504-142">Especifica que el tipo tiene seguridad asociada a él.</span><span class="sxs-lookup"><span data-stu-id="9f504-142">Specifies that the type has security associated with it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9f504-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f504-143">Requirements</span></span>  
 <span data-ttu-id="9f504-144">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f504-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f504-145">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="9f504-145">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9f504-146">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f504-146">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f504-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f504-147">See Also</span></span>  
 [<span data-ttu-id="9f504-148">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="9f504-148">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
