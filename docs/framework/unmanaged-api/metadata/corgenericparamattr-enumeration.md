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
ms.openlocfilehash: bf0008ce9429671f0c156df4256bed0b2aaee184
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176180"
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="c933b-102">CorGenericParamAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c933b-102">CorGenericParamAttr Enumeration</span></span>
<span data-ttu-id="c933b-103">Contiene valores que <xref:System.Type> describen los parámetros de los tipos genéricos, como se usa en las llamadas a [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="c933b-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c933b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c933b-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="c933b-105">Members</span><span class="sxs-lookup"><span data-stu-id="c933b-105">Members</span></span>  
  
|<span data-ttu-id="c933b-106">Member</span><span class="sxs-lookup"><span data-stu-id="c933b-106">Member</span></span>|<span data-ttu-id="c933b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c933b-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="c933b-108">La varianza de parámetros solo se aplica a parámetros genéricos para interfaces y delegados.</span><span class="sxs-lookup"><span data-stu-id="c933b-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="c933b-109">Indica la ausencia de varianza.</span><span class="sxs-lookup"><span data-stu-id="c933b-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="c933b-110">Indica covarianza.</span><span class="sxs-lookup"><span data-stu-id="c933b-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="c933b-111">Indica contravarianza.</span><span class="sxs-lookup"><span data-stu-id="c933b-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="c933b-112">Se pueden aplicar restricciones especiales a cualquier <xref:System.Type> parámetro.</span><span class="sxs-lookup"><span data-stu-id="c933b-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="c933b-113">Indica que no se <xref:System.Type> aplica ninguna restricción al parámetro.</span><span class="sxs-lookup"><span data-stu-id="c933b-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="c933b-114">Indica que <xref:System.Type> el parámetro debe ser un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="c933b-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="c933b-115">Indica que <xref:System.Type> el parámetro debe ser un tipo de valor que no puede ser un valor nulo.</span><span class="sxs-lookup"><span data-stu-id="c933b-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="c933b-116">Indica que <xref:System.Type> el parámetro debe tener un constructor público predeterminado que no toma ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="c933b-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c933b-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c933b-117">Requirements</span></span>  
 <span data-ttu-id="c933b-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c933b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c933b-119">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="c933b-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c933b-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c933b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c933b-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c933b-121">See also</span></span>

- [<span data-ttu-id="c933b-122">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="c933b-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
