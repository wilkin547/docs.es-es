---
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
ms.openlocfilehash: b1586184c91619994ba0dfc9d5dcc277c10f99cf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436452"
---
# <a name="cortypeattr-enumeration"></a><span data-ttu-id="5dd07-102">CorTypeAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="5dd07-102">CorTypeAttr Enumeration</span></span>
<span data-ttu-id="5dd07-103">Contiene valores que indican los metadatos de tipo.</span><span class="sxs-lookup"><span data-stu-id="5dd07-103">Contains values that indicate type metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dd07-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5dd07-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="5dd07-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="5dd07-105">Members</span></span>  
  
|<span data-ttu-id="5dd07-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="5dd07-106">Member</span></span>|<span data-ttu-id="5dd07-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5dd07-107">Description</span></span>|  
|------------|-----------------|  
|`tdVisibilityMask`|<span data-ttu-id="5dd07-108">Used for type visibility information.</span><span class="sxs-lookup"><span data-stu-id="5dd07-108">Used for type visibility information.</span></span>|  
|`tdNotPublic`|<span data-ttu-id="5dd07-109">Specifies that the type is not in public scope.</span><span class="sxs-lookup"><span data-stu-id="5dd07-109">Specifies that the type is not in public scope.</span></span>|  
|`tdPublic`|<span data-ttu-id="5dd07-110">Specifies that the type is in public scope.</span><span class="sxs-lookup"><span data-stu-id="5dd07-110">Specifies that the type is in public scope.</span></span>|  
|`tdNestedPublic`|<span data-ttu-id="5dd07-111">Specifies that the type is nested with public visibility.</span><span class="sxs-lookup"><span data-stu-id="5dd07-111">Specifies that the type is nested with public visibility.</span></span>|  
|`tdNestedPrivate`|<span data-ttu-id="5dd07-112">Specifies that the type is nested with private visibility.</span><span class="sxs-lookup"><span data-stu-id="5dd07-112">Specifies that the type is nested with private visibility.</span></span>|  
|`tdNestedFamily`|<span data-ttu-id="5dd07-113">Specifies that the type is nested with family visibility.</span><span class="sxs-lookup"><span data-stu-id="5dd07-113">Specifies that the type is nested with family visibility.</span></span>|  
|`tdNestedAssembly`|<span data-ttu-id="5dd07-114">Specifies that the type is nested with assembly visibility.</span><span class="sxs-lookup"><span data-stu-id="5dd07-114">Specifies that the type is nested with assembly visibility.</span></span>|  
|`tdNestedFamANDAssem`|<span data-ttu-id="5dd07-115">Specifies that the type is nested with family and assembly visibility.</span><span class="sxs-lookup"><span data-stu-id="5dd07-115">Specifies that the type is nested with family and assembly visibility.</span></span>|  
|`tdNestedFamORAssem`|<span data-ttu-id="5dd07-116">Specifies that the type is nested with family or assembly visibility.</span><span class="sxs-lookup"><span data-stu-id="5dd07-116">Specifies that the type is nested with family or assembly visibility.</span></span>|  
|`tdLayoutMask`|<span data-ttu-id="5dd07-117">Gets layout information for the type.</span><span class="sxs-lookup"><span data-stu-id="5dd07-117">Gets layout information for the type.</span></span>|  
|`tdAutoLayout`|<span data-ttu-id="5dd07-118">Specifies that the fields of this type are laid out automatically.</span><span class="sxs-lookup"><span data-stu-id="5dd07-118">Specifies that the fields of this type are laid out automatically.</span></span>|  
|`tdSequentialLayout`|<span data-ttu-id="5dd07-119">Specifies that the fields of this type are laid out sequentially.</span><span class="sxs-lookup"><span data-stu-id="5dd07-119">Specifies that the fields of this type are laid out sequentially.</span></span>|  
|`tdExplicitLayout`|<span data-ttu-id="5dd07-120">Specifies that field layout is supplied explicitly.</span><span class="sxs-lookup"><span data-stu-id="5dd07-120">Specifies that field layout is supplied explicitly.</span></span>|  
|`tdClassSemanticsMask`|<span data-ttu-id="5dd07-121">Gets semantic information about the type.</span><span class="sxs-lookup"><span data-stu-id="5dd07-121">Gets semantic information about the type.</span></span>|  
|`tdClass`|<span data-ttu-id="5dd07-122">Especifica que el tipo es una clase.</span><span class="sxs-lookup"><span data-stu-id="5dd07-122">Specifies that the type is a class.</span></span>|  
|`tdInterface`|<span data-ttu-id="5dd07-123">Especifica que el tipo es una interfaz.</span><span class="sxs-lookup"><span data-stu-id="5dd07-123">Specifies that the type is an interface.</span></span>|  
|`tdAbstract`|<span data-ttu-id="5dd07-124">Especifica que el tipo es abstracto.</span><span class="sxs-lookup"><span data-stu-id="5dd07-124">Specifies that the type is abstract.</span></span>|  
|`tdSealed`|<span data-ttu-id="5dd07-125">Specifies that the type cannot be extended.</span><span class="sxs-lookup"><span data-stu-id="5dd07-125">Specifies that the type cannot be extended.</span></span>|  
|`tdSpecialName`|<span data-ttu-id="5dd07-126">Specifies that the class name is special.</span><span class="sxs-lookup"><span data-stu-id="5dd07-126">Specifies that the class name is special.</span></span> <span data-ttu-id="5dd07-127">Its name describes how.</span><span class="sxs-lookup"><span data-stu-id="5dd07-127">Its name describes how.</span></span>|  
|`tdImport`|<span data-ttu-id="5dd07-128">Specifies that the type is imported.</span><span class="sxs-lookup"><span data-stu-id="5dd07-128">Specifies that the type is imported.</span></span>|  
|`tdSerializable`|<span data-ttu-id="5dd07-129">Specifies that the type is serializable.</span><span class="sxs-lookup"><span data-stu-id="5dd07-129">Specifies that the type is serializable.</span></span>|  
|`tdWindowsRuntime`|<span data-ttu-id="5dd07-130">Specifies that this type is a Windows Runtime type.</span><span class="sxs-lookup"><span data-stu-id="5dd07-130">Specifies that this type is a Windows Runtime type.</span></span>|  
|`tdStringFormatMask`|<span data-ttu-id="5dd07-131">Gets information about how strings are encoded and formatted.</span><span class="sxs-lookup"><span data-stu-id="5dd07-131">Gets information about how strings are encoded and formatted.</span></span>|  
|`tdAnsiClass`|<span data-ttu-id="5dd07-132">Specifies that this type interprets an LPTSTR as ANSI.</span><span class="sxs-lookup"><span data-stu-id="5dd07-132">Specifies that this type interprets an LPTSTR as ANSI.</span></span>|  
|`tdUnicodeClass`|<span data-ttu-id="5dd07-133">Specifies that this type interprets an LPTSTR as Unicode.</span><span class="sxs-lookup"><span data-stu-id="5dd07-133">Specifies that this type interprets an LPTSTR as Unicode.</span></span>|  
|`tdAutoClass`|<span data-ttu-id="5dd07-134">Specifies that this type interprets an LPTSTR automatically.</span><span class="sxs-lookup"><span data-stu-id="5dd07-134">Specifies that this type interprets an LPTSTR automatically.</span></span>|  
|`tdCustomFormatClass`|<span data-ttu-id="5dd07-135">Specifies that the type has a non-standard encoding, as specified by `CustomFormatMask`.</span><span class="sxs-lookup"><span data-stu-id="5dd07-135">Specifies that the type has a non-standard encoding, as specified by `CustomFormatMask`.</span></span>|  
|`tdCustomFormatMask`|<span data-ttu-id="5dd07-136">Use this mask to get non-standard encoding information for native interop.</span><span class="sxs-lookup"><span data-stu-id="5dd07-136">Use this mask to get non-standard encoding information for native interop.</span></span> <span data-ttu-id="5dd07-137">The meaning of the values of these two bits is unspecified.</span><span class="sxs-lookup"><span data-stu-id="5dd07-137">The meaning of the values of these two bits is unspecified.</span></span>|  
|`tdBeforeFieldInit`|<span data-ttu-id="5dd07-138">Specifies that the type must be initialized before the first attempt to access a static field.</span><span class="sxs-lookup"><span data-stu-id="5dd07-138">Specifies that the type must be initialized before the first attempt to access a static field.</span></span>|  
|`tdForwarder`|<span data-ttu-id="5dd07-139">Specifies that the type is exported, and a type forwarder.</span><span class="sxs-lookup"><span data-stu-id="5dd07-139">Specifies that the type is exported, and a type forwarder.</span></span>|  
|`tdReservedMask`|<span data-ttu-id="5dd07-140">This flag and the flags below are used internally by the common language runtime.</span><span class="sxs-lookup"><span data-stu-id="5dd07-140">This flag and the flags below are used internally by the common language runtime.</span></span>|  
|`tdRTSpecialName`|<span data-ttu-id="5dd07-141">Specifies that the common language runtime should check the name encoding.</span><span class="sxs-lookup"><span data-stu-id="5dd07-141">Specifies that the common language runtime should check the name encoding.</span></span>|  
|`tdHasSecurity`|<span data-ttu-id="5dd07-142">Specifies that the type has security associated with it.</span><span class="sxs-lookup"><span data-stu-id="5dd07-142">Specifies that the type has security associated with it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5dd07-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5dd07-143">Requirements</span></span>  
 <span data-ttu-id="5dd07-144">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dd07-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dd07-145">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="5dd07-145">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="5dd07-146">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dd07-146">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dd07-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="5dd07-147">See also</span></span>

- [<span data-ttu-id="5dd07-148">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="5dd07-148">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
