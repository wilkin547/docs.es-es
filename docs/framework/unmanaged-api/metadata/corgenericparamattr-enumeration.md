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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0aa9b84c9e16811f799a3cd2ad096508db3f7d34
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045799"
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="54e96-102">CorGenericParamAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="54e96-102">CorGenericParamAttr Enumeration</span></span>
<span data-ttu-id="54e96-103">Contiene valores que describen el <xref:System.Type> parámetros para los tipos genéricos, como las usadas en llamadas a [IMetaDataEmit2:: DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="54e96-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54e96-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54e96-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="54e96-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="54e96-105">Members</span></span>  
  
|<span data-ttu-id="54e96-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="54e96-106">Member</span></span>|<span data-ttu-id="54e96-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="54e96-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="54e96-108">Varianza de parámetro solo se aplica a parámetros genéricos para interfaces y delegados.</span><span class="sxs-lookup"><span data-stu-id="54e96-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="54e96-109">Indica la ausencia de varianza.</span><span class="sxs-lookup"><span data-stu-id="54e96-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="54e96-110">Indica la covarianza.</span><span class="sxs-lookup"><span data-stu-id="54e96-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="54e96-111">Indica la contravarianza.</span><span class="sxs-lookup"><span data-stu-id="54e96-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="54e96-112">Pueden aplicar las restricciones especiales a cualquier <xref:System.Type> parámetro.</span><span class="sxs-lookup"><span data-stu-id="54e96-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="54e96-113">Indica que se aplica ninguna restricción a la <xref:System.Type> parámetro.</span><span class="sxs-lookup"><span data-stu-id="54e96-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="54e96-114">Indica que el <xref:System.Type> parámetro debe ser un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="54e96-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="54e96-115">Indica que el <xref:System.Type> parámetro debe ser un tipo de valor no puede ser un valor null.</span><span class="sxs-lookup"><span data-stu-id="54e96-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="54e96-116">Indica que el <xref:System.Type> parámetro debe tener un constructor público predeterminado que no toma ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="54e96-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="54e96-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54e96-117">Requirements</span></span>  
 <span data-ttu-id="54e96-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54e96-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54e96-119">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="54e96-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="54e96-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54e96-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54e96-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="54e96-121">See also</span></span>

- [<span data-ttu-id="54e96-122">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="54e96-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
