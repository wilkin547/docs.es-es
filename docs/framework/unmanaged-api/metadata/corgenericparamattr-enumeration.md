---
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
ms.openlocfilehash: ea84b742c901ba58a3bb730f1f5033a0d90610ce
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007382"
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="18d5a-102">CorGenericParamAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="18d5a-102">CorGenericParamAttr Enumeration</span></span>
<span data-ttu-id="18d5a-103">Contiene valores que describen los <xref:System.Type> parámetros de los tipos genéricos, tal y como se usan en las llamadas a [IMetaDataEmit2::D efinegenericparam](imetadataemit2-definegenericparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="18d5a-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18d5a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="18d5a-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="18d5a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="18d5a-105">Members</span></span>  
  
|<span data-ttu-id="18d5a-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="18d5a-106">Member</span></span>|<span data-ttu-id="18d5a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="18d5a-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="18d5a-108">La varianza de parámetros solo se aplica a los parámetros genéricos para interfaces y delegados.</span><span class="sxs-lookup"><span data-stu-id="18d5a-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="18d5a-109">Indica la ausencia de varianza.</span><span class="sxs-lookup"><span data-stu-id="18d5a-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="18d5a-110">Indica covarianza.</span><span class="sxs-lookup"><span data-stu-id="18d5a-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="18d5a-111">Indica la contravarianza.</span><span class="sxs-lookup"><span data-stu-id="18d5a-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="18d5a-112">Las restricciones especiales se pueden aplicar a cualquier <xref:System.Type> parámetro.</span><span class="sxs-lookup"><span data-stu-id="18d5a-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="18d5a-113">Indica que no se aplica ninguna restricción al <xref:System.Type> parámetro.</span><span class="sxs-lookup"><span data-stu-id="18d5a-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="18d5a-114">Indica que el <xref:System.Type> parámetro debe ser un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="18d5a-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="18d5a-115">Indica que el <xref:System.Type> parámetro debe ser un tipo de valor que no puede ser un valor null.</span><span class="sxs-lookup"><span data-stu-id="18d5a-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="18d5a-116">Indica que el <xref:System.Type> parámetro debe tener un constructor público predeterminado que no tome ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="18d5a-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="18d5a-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="18d5a-117">Requirements</span></span>  
 <span data-ttu-id="18d5a-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18d5a-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18d5a-119">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="18d5a-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="18d5a-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18d5a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18d5a-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="18d5a-121">See also</span></span>

- [<span data-ttu-id="18d5a-122">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="18d5a-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
