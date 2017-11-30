---
title: "CorGenericParamAttr (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorGenericParamAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorGenericParamAttr
helpviewer_keywords: CorGenericParamAttr enumeration [.NET Framework metadata]
ms.assetid: 36c76266-71d8-48dc-bd89-54943fa659c1
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 95d7a6097766c8e2389e9828f54e81e37ffea454
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="78882-102">CorGenericParamAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="78882-102">CorGenericParamAttr Enumeration</span></span>
<span data-ttu-id="78882-103">Contiene valores que describen la <xref:System.Type> parámetros de tipos genéricos, como usan en las llamadas a [IMetaDataEmit2:: DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="78882-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78882-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78882-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="78882-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="78882-105">Members</span></span>  
  
|<span data-ttu-id="78882-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="78882-106">Member</span></span>|<span data-ttu-id="78882-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="78882-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="78882-108">La varianza de parámetros solo se aplica a parámetros genéricos para las interfaces y delegados.</span><span class="sxs-lookup"><span data-stu-id="78882-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="78882-109">Indica la ausencia de varianza.</span><span class="sxs-lookup"><span data-stu-id="78882-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="78882-110">Indica la covarianza.</span><span class="sxs-lookup"><span data-stu-id="78882-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="78882-111">Indica la contravarianza.</span><span class="sxs-lookup"><span data-stu-id="78882-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="78882-112">Pueden aplicar las restricciones especiales a cualquier <xref:System.Type> parámetro.</span><span class="sxs-lookup"><span data-stu-id="78882-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="78882-113">Indica que se aplica ninguna restricción a la <xref:System.Type> parámetro.</span><span class="sxs-lookup"><span data-stu-id="78882-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="78882-114">Indica que el <xref:System.Type> parámetro debe ser un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="78882-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="78882-115">Indica que el <xref:System.Type> parámetro debe ser un tipo de valor no puede ser un valor null.</span><span class="sxs-lookup"><span data-stu-id="78882-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="78882-116">Indica que el <xref:System.Type> parámetro debe tener un constructor público predeterminado que no toma ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="78882-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="78882-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78882-117">Requirements</span></span>  
 <span data-ttu-id="78882-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78882-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78882-119">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="78882-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="78882-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78882-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78882-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="78882-121">See Also</span></span>  
 [<span data-ttu-id="78882-122">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="78882-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
