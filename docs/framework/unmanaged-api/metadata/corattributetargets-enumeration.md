---
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
ms.openlocfilehash: f1836f26af99f91ab1765107573f6b067edd5e95
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007928"
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="09b14-102">CorAttributeTargets (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="09b14-102">CorAttributeTargets Enumeration</span></span>
<span data-ttu-id="09b14-103">Especifica los elementos de aplicación en los que se permite aplicar un atributo.</span><span class="sxs-lookup"><span data-stu-id="09b14-103">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09b14-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09b14-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="09b14-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="09b14-105">Members</span></span>  
  
|<span data-ttu-id="09b14-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="09b14-106">Member</span></span>|<span data-ttu-id="09b14-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="09b14-107">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="09b14-108">El atributo puede aplicarse a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="09b14-108">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="09b14-109">El atributo se puede aplicar a un módulo ejecutable portable (. dll o. exe).</span><span class="sxs-lookup"><span data-stu-id="09b14-109">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="09b14-110">El atributo puede aplicarse a una clase.</span><span class="sxs-lookup"><span data-stu-id="09b14-110">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="09b14-111">El atributo puede aplicarse a una estructura, es decir, a un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="09b14-111">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="09b14-112">El atributo puede aplicarse a una enumeración.</span><span class="sxs-lookup"><span data-stu-id="09b14-112">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="09b14-113">El atributo puede aplicarse a un constructor.</span><span class="sxs-lookup"><span data-stu-id="09b14-113">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="09b14-114">El atributo puede aplicarse a un método.</span><span class="sxs-lookup"><span data-stu-id="09b14-114">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="09b14-115">El atributo puede aplicarse a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="09b14-115">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="09b14-116">El atributo puede aplicarse a un campo.</span><span class="sxs-lookup"><span data-stu-id="09b14-116">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="09b14-117">El atributo puede aplicarse a un evento.</span><span class="sxs-lookup"><span data-stu-id="09b14-117">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="09b14-118">El atributo puede aplicarse a una interfaz.</span><span class="sxs-lookup"><span data-stu-id="09b14-118">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="09b14-119">El atributo puede aplicarse a un parámetro.</span><span class="sxs-lookup"><span data-stu-id="09b14-119">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="09b14-120">El atributo puede aplicarse a un delegado.</span><span class="sxs-lookup"><span data-stu-id="09b14-120">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="09b14-121">El atributo puede aplicarse a un parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="09b14-121">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="09b14-122">El atributo puede aplicarse a cualquier elemento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="09b14-122">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="09b14-123">El atributo se puede aplicar a un miembro de una clase.</span><span class="sxs-lookup"><span data-stu-id="09b14-123">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09b14-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="09b14-124">Remarks</span></span>  
 <span data-ttu-id="09b14-125">Los `CorAttributeTargets` valores de enumeración se pueden combinar con una operación OR bit a bit para obtener la combinación preferida.</span><span class="sxs-lookup"><span data-stu-id="09b14-125">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="09b14-126">La `CorAttributeTargets` enumeración administrada es paralela <xref:System.AttributeTargets?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="09b14-126">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09b14-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09b14-127">Requirements</span></span>  
 <span data-ttu-id="09b14-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09b14-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09b14-129">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="09b14-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="09b14-130">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09b14-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09b14-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="09b14-131">See also</span></span>

- [<span data-ttu-id="09b14-132">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="09b14-132">Metadata Enumerations</span></span>](metadata-enumerations.md)
