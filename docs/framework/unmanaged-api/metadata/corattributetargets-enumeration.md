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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 416c7787e7e68ea0c6864091e92d92fed1a60bf4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650124"
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="f340d-102">CorAttributeTargets (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f340d-102">CorAttributeTargets Enumeration</span></span>
<span data-ttu-id="f340d-103">Especifica los elementos de aplicación en los que se permite aplicar un atributo.</span><span class="sxs-lookup"><span data-stu-id="f340d-103">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f340d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f340d-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="f340d-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="f340d-105">Members</span></span>  
  
|<span data-ttu-id="f340d-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="f340d-106">Member</span></span>|<span data-ttu-id="f340d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f340d-107">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="f340d-108">Atributo puede aplicarse a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f340d-108">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="f340d-109">Atributo puede aplicarse a un módulo ejecutable portable (.dll o .exe).</span><span class="sxs-lookup"><span data-stu-id="f340d-109">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="f340d-110">Atributo puede aplicarse a una clase.</span><span class="sxs-lookup"><span data-stu-id="f340d-110">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="f340d-111">Atributo puede aplicarse a una estructura; es decir, un valor de tipo.</span><span class="sxs-lookup"><span data-stu-id="f340d-111">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="f340d-112">Atributo puede aplicarse a una enumeración.</span><span class="sxs-lookup"><span data-stu-id="f340d-112">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="f340d-113">Atributo puede aplicarse a un constructor.</span><span class="sxs-lookup"><span data-stu-id="f340d-113">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="f340d-114">Atributo puede aplicarse a un método.</span><span class="sxs-lookup"><span data-stu-id="f340d-114">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="f340d-115">Atributo puede aplicarse a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="f340d-115">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="f340d-116">Atributo puede aplicarse a un campo.</span><span class="sxs-lookup"><span data-stu-id="f340d-116">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="f340d-117">Atributo puede aplicarse a un evento.</span><span class="sxs-lookup"><span data-stu-id="f340d-117">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="f340d-118">Atributo puede aplicarse a una interfaz.</span><span class="sxs-lookup"><span data-stu-id="f340d-118">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="f340d-119">Atributo puede aplicarse a un parámetro.</span><span class="sxs-lookup"><span data-stu-id="f340d-119">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="f340d-120">Atributo puede aplicarse a un delegado.</span><span class="sxs-lookup"><span data-stu-id="f340d-120">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="f340d-121">Atributo puede aplicarse a un parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="f340d-121">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="f340d-122">Atributo puede aplicarse a cualquier elemento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f340d-122">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="f340d-123">Atributo puede aplicarse a un miembro de una clase.</span><span class="sxs-lookup"><span data-stu-id="f340d-123">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f340d-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f340d-124">Remarks</span></span>  
 <span data-ttu-id="f340d-125">El `CorAttributeTargets` valores de enumeración se pueden combinar con una operación OR bit a bit para obtener la combinación preferida.</span><span class="sxs-lookup"><span data-stu-id="f340d-125">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="f340d-126">El `CorAttributeTargets` es semejante a los recursos administrados <xref:System.AttributeTargets?displayProperty=nameWithType> enumeración.</span><span class="sxs-lookup"><span data-stu-id="f340d-126">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f340d-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f340d-127">Requirements</span></span>  
 <span data-ttu-id="f340d-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f340d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f340d-129">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="f340d-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f340d-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f340d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f340d-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="f340d-131">See also</span></span>
- [<span data-ttu-id="f340d-132">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="f340d-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
