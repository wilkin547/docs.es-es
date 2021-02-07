---
description: 'Más información sobre: enumeración CorAttributeTargets ('
title: CorAttributeTargets (Enumeración)
ms.date: 03/30/2017
api_name:
- CorAttributeTargets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAttributeTargets
helpviewer_keywords:
- CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type:
- apiref
ms.openlocfilehash: 6f80df31b9da8591fac3d979ede1e9bf0f8ecfc4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678502"
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="2d6d2-103">CorAttributeTargets (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="2d6d2-103">CorAttributeTargets Enumeration</span></span>

<span data-ttu-id="2d6d2-104">Especifica los elementos de aplicación en los que se permite aplicar un atributo.</span><span class="sxs-lookup"><span data-stu-id="2d6d2-104">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d6d2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d6d2-105">Syntax</span></span>  
  
```cpp  
typedef enum CorAttributeTargets  
{  
    catAssembly            = 0x0001,  
    catModule              = 0x0002,  
    catClass               = 0x0004,  
    catStruct              = 0x0008,  
    catEnum                = 0x0010,  
    catConstructor         = 0x0020,  
    catMethod              = 0x0040,  
    catProperty            = 0x0080,  
    catField               = 0x0100,  
    catEvent               = 0x0200,  
    catInterface           = 0x0400,  
    catParameter           = 0x0800,  
    catDelegate            = 0x1000,  
    catGenericParameter    = 0x4000,  
  
    catAll                 =
        catAssembly | catModule | catClass | catStruct |
        catEnum | catConstructor | catMethod | catProperty |
        catField | catEvent | catInterface | catParameter |
        catDelegate | catGenericParameter,  
  
    catClassMembers        =
        catClass | catStruct | catEnum | catConstructor |
        catMethod | catProperty | catField | catEvent |
        catDelegate | catInterface  
  
} CorAttributeTargets;  
```  
  
## <a name="members"></a><span data-ttu-id="2d6d2-106">Members</span><span class="sxs-lookup"><span data-stu-id="2d6d2-106">Members</span></span>  
  
|<span data-ttu-id="2d6d2-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="2d6d2-107">Member</span></span>|<span data-ttu-id="2d6d2-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d6d2-108">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="2d6d2-109">El atributo puede aplicarse a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2d6d2-109">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="2d6d2-110">El atributo se puede aplicar a un módulo ejecutable portable (. dll o. exe).</span><span class="sxs-lookup"><span data-stu-id="2d6d2-110">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="2d6d2-111">El atributo puede aplicarse a una clase.</span><span class="sxs-lookup"><span data-stu-id="2d6d2-111">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="2d6d2-112">El atributo puede aplicarse a una estructura, es decir, a un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="2d6d2-112">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="2d6d2-113">El atributo puede aplicarse a una enumeración.</span><span class="sxs-lookup"><span data-stu-id="2d6d2-113">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="2d6d2-114">El atributo puede aplicarse a un constructor.</span><span class="sxs-lookup"><span data-stu-id="2d6d2-114">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="2d6d2-115">El atributo puede aplicarse a un método.</span><span class="sxs-lookup"><span data-stu-id="2d6d2-115">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="2d6d2-116">El atributo puede aplicarse a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="2d6d2-116">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="2d6d2-117">El atributo puede aplicarse a un campo.</span><span class="sxs-lookup"><span data-stu-id="2d6d2-117">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="2d6d2-118">El atributo puede aplicarse a un evento.</span><span class="sxs-lookup"><span data-stu-id="2d6d2-118">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="2d6d2-119">El atributo puede aplicarse a una interfaz.</span><span class="sxs-lookup"><span data-stu-id="2d6d2-119">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="2d6d2-120">El atributo puede aplicarse a un parámetro.</span><span class="sxs-lookup"><span data-stu-id="2d6d2-120">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="2d6d2-121">El atributo puede aplicarse a un delegado.</span><span class="sxs-lookup"><span data-stu-id="2d6d2-121">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="2d6d2-122">El atributo puede aplicarse a un parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="2d6d2-122">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="2d6d2-123">El atributo puede aplicarse a cualquier elemento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2d6d2-123">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="2d6d2-124">El atributo se puede aplicar a un miembro de una clase.</span><span class="sxs-lookup"><span data-stu-id="2d6d2-124">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d6d2-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2d6d2-125">Remarks</span></span>  

 <span data-ttu-id="2d6d2-126">Los `CorAttributeTargets` valores de enumeración se pueden combinar con una operación OR bit a bit para obtener la combinación preferida.</span><span class="sxs-lookup"><span data-stu-id="2d6d2-126">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="2d6d2-127">La `CorAttributeTargets` enumeración administrada es paralela <xref:System.AttributeTargets?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="2d6d2-127">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d6d2-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d6d2-128">Requirements</span></span>  

 <span data-ttu-id="2d6d2-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d6d2-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d6d2-130">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="2d6d2-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="2d6d2-131">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d6d2-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d6d2-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d6d2-132">See also</span></span>

- [<span data-ttu-id="2d6d2-133">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="2d6d2-133">Metadata Enumerations</span></span>](metadata-enumerations.md)
