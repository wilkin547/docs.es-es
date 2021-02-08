---
description: 'Más información sobre: enumeración CorGenericParamAttr ('
title: CorGenericParamAttr (Enumeración)
ms.date: 03/30/2017
api_name:
- CorGenericParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGenericParamAttr
helpviewer_keywords:
- CorGenericParamAttr enumeration [.NET Framework metadata]
ms.assetid: 36c76266-71d8-48dc-bd89-54943fa659c1
topic_type:
- apiref
ms.openlocfilehash: 8fe8cb20834ecbc5477bbe8b01bf77d6b1af0eea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784462"
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="413fa-103">CorGenericParamAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="413fa-103">CorGenericParamAttr Enumeration</span></span>

<span data-ttu-id="413fa-104">Contiene valores que describen los <xref:System.Type> parámetros de los tipos genéricos, tal y como se usan en las llamadas a [IMetaDataEmit2::D efinegenericparam](imetadataemit2-definegenericparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="413fa-104">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="413fa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="413fa-105">Syntax</span></span>  
  
```cpp  
typedef enum CorGenericParamAttr {  
  
    gpVarianceMask                     =   0x0003,  
    gpNonVariant                       =   0x0000,
    gpCovariant                        =   0x0001,  
    gpContravariant                    =   0x0002,  
  
    gpSpecialConstraintMask            =   0x001C,  
    gpNoSpecialConstraint              =   0x0000,  
    gpReferenceTypeConstraint          =   0x0004,
    gpNotNullableValueTypeConstraint   =   0x0008,  
    gpDefaultConstructorConstraint     =   0x0010  
  
} CorGenericParamAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="413fa-106">Members</span><span class="sxs-lookup"><span data-stu-id="413fa-106">Members</span></span>  
  
|<span data-ttu-id="413fa-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="413fa-107">Member</span></span>|<span data-ttu-id="413fa-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="413fa-108">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="413fa-109">La varianza de parámetros solo se aplica a los parámetros genéricos para interfaces y delegados.</span><span class="sxs-lookup"><span data-stu-id="413fa-109">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="413fa-110">Indica la ausencia de varianza.</span><span class="sxs-lookup"><span data-stu-id="413fa-110">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="413fa-111">Indica covarianza.</span><span class="sxs-lookup"><span data-stu-id="413fa-111">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="413fa-112">Indica la contravarianza.</span><span class="sxs-lookup"><span data-stu-id="413fa-112">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="413fa-113">Las restricciones especiales se pueden aplicar a cualquier <xref:System.Type> parámetro.</span><span class="sxs-lookup"><span data-stu-id="413fa-113">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="413fa-114">Indica que no se aplica ninguna restricción al <xref:System.Type> parámetro.</span><span class="sxs-lookup"><span data-stu-id="413fa-114">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="413fa-115">Indica que el <xref:System.Type> parámetro debe ser un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="413fa-115">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="413fa-116">Indica que el <xref:System.Type> parámetro debe ser un tipo de valor que no puede ser un valor null.</span><span class="sxs-lookup"><span data-stu-id="413fa-116">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="413fa-117">Indica que el <xref:System.Type> parámetro debe tener un constructor público predeterminado que no tome ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="413fa-117">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="413fa-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="413fa-118">Requirements</span></span>  

 <span data-ttu-id="413fa-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="413fa-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="413fa-120">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="413fa-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="413fa-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="413fa-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="413fa-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="413fa-122">See also</span></span>

- [<span data-ttu-id="413fa-123">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="413fa-123">Metadata Enumerations</span></span>](metadata-enumerations.md)
