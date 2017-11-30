---
title: "CorAttributeTargets (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorAttributeTargets
api_location: mscoree.dll
api_type: COM
f1_keywords: CorAttributeTargets
helpviewer_keywords: CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ce783c790eeb15c60d8e7699396755a560df7c9c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="7e825-102">CorAttributeTargets (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="7e825-102">CorAttributeTargets Enumeration</span></span>
<span data-ttu-id="7e825-103">Especifica los elementos de aplicación en los que se permite aplicar un atributo.</span><span class="sxs-lookup"><span data-stu-id="7e825-103">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e825-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e825-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="7e825-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="7e825-105">Members</span></span>  
  
|<span data-ttu-id="7e825-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="7e825-106">Member</span></span>|<span data-ttu-id="7e825-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e825-107">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="7e825-108">Atributo se puede aplicar a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7e825-108">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="7e825-109">Atributo se puede aplicar a un módulo ejecutable portable (.dll o .exe).</span><span class="sxs-lookup"><span data-stu-id="7e825-109">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="7e825-110">Atributo se puede aplicar a una clase.</span><span class="sxs-lookup"><span data-stu-id="7e825-110">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="7e825-111">Atributo se puede aplicar a una estructura; es decir, un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="7e825-111">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="7e825-112">Atributo se puede aplicar a una enumeración.</span><span class="sxs-lookup"><span data-stu-id="7e825-112">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="7e825-113">Atributo se puede aplicar a un constructor.</span><span class="sxs-lookup"><span data-stu-id="7e825-113">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="7e825-114">Atributo se puede aplicar a un método.</span><span class="sxs-lookup"><span data-stu-id="7e825-114">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="7e825-115">Atributo se puede aplicar a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="7e825-115">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="7e825-116">Atributo se puede aplicar a un campo.</span><span class="sxs-lookup"><span data-stu-id="7e825-116">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="7e825-117">Atributo se puede aplicar a un evento.</span><span class="sxs-lookup"><span data-stu-id="7e825-117">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="7e825-118">Atributo se puede aplicar a una interfaz.</span><span class="sxs-lookup"><span data-stu-id="7e825-118">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="7e825-119">Atributo se puede aplicar a un parámetro.</span><span class="sxs-lookup"><span data-stu-id="7e825-119">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="7e825-120">Atributo se puede aplicar a un delegado.</span><span class="sxs-lookup"><span data-stu-id="7e825-120">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="7e825-121">Atributo se puede aplicar a un parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="7e825-121">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="7e825-122">Atributo se puede aplicar a cualquier elemento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7e825-122">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="7e825-123">Atributo se puede aplicar a un miembro de una clase.</span><span class="sxs-lookup"><span data-stu-id="7e825-123">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e825-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7e825-124">Remarks</span></span>  
 <span data-ttu-id="7e825-125">El `CorAttributeTargets` valores de enumeración se pueden combinar con una operación OR bit a bit para obtener la combinación preferida.</span><span class="sxs-lookup"><span data-stu-id="7e825-125">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="7e825-126">El `CorAttributeTargets` se asemeja a los recursos administrados <xref:System.AttributeTargets?displayProperty=nameWithType> enumeración.</span><span class="sxs-lookup"><span data-stu-id="7e825-126">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e825-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e825-127">Requirements</span></span>  
 <span data-ttu-id="7e825-128">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e825-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e825-129">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="7e825-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7e825-130">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e825-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e825-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e825-131">See Also</span></span>  
 [<span data-ttu-id="7e825-132">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="7e825-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
