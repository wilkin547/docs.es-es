---
title: IMetaDataImport2 (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataImport2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2
helpviewer_keywords:
- IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type:
- apiref
ms.openlocfilehash: 0fd7915ef46899bdce8312bc6e8a466167e26382
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429209"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="5a696-102">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a696-102">IMetaDataImport2 Interface</span></span>
<span data-ttu-id="5a696-103">Extends the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface to provide the capability of working with generic types.</span><span class="sxs-lookup"><span data-stu-id="5a696-103">Extends the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5a696-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5a696-104">Methods</span></span>  
  
|<span data-ttu-id="5a696-105">Método</span><span class="sxs-lookup"><span data-stu-id="5a696-105">Method</span></span>|<span data-ttu-id="5a696-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a696-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5a696-107">EnumGenericParamConstraints (método)</span><span class="sxs-lookup"><span data-stu-id="5a696-107">EnumGenericParamConstraints Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="5a696-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span><span class="sxs-lookup"><span data-stu-id="5a696-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="5a696-109">EnumGenericParams (método)</span><span class="sxs-lookup"><span data-stu-id="5a696-109">EnumGenericParams Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="5a696-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span><span class="sxs-lookup"><span data-stu-id="5a696-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="5a696-111">EnumMethodSpecs (método)</span><span class="sxs-lookup"><span data-stu-id="5a696-111">EnumMethodSpecs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="5a696-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span><span class="sxs-lookup"><span data-stu-id="5a696-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="5a696-113">GetGenericParamConstraintProps (método)</span><span class="sxs-lookup"><span data-stu-id="5a696-113">GetGenericParamConstraintProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="5a696-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span><span class="sxs-lookup"><span data-stu-id="5a696-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="5a696-115">GetGenericParamProps (método)</span><span class="sxs-lookup"><span data-stu-id="5a696-115">GetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="5a696-116">Gets the metadata associated with the generic parameter represented by the specified token.</span><span class="sxs-lookup"><span data-stu-id="5a696-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="5a696-117">GetMethodSpecProps (método)</span><span class="sxs-lookup"><span data-stu-id="5a696-117">GetMethodSpecProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="5a696-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span><span class="sxs-lookup"><span data-stu-id="5a696-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="5a696-119">GetPEKind (método)</span><span class="sxs-lookup"><span data-stu-id="5a696-119">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|<span data-ttu-id="5a696-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span><span class="sxs-lookup"><span data-stu-id="5a696-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="5a696-121">GetVersionString (método)</span><span class="sxs-lookup"><span data-stu-id="5a696-121">GetVersionString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|<span data-ttu-id="5a696-122">Gets the version number of the runtime that was used to build the assembly.</span><span class="sxs-lookup"><span data-stu-id="5a696-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a696-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a696-123">Requirements</span></span>  
 <span data-ttu-id="5a696-124">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a696-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a696-125">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5a696-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5a696-126">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a696-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5a696-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a696-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a696-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a696-128">See also</span></span>

- <xref:System.Reflection.PortableExecutableKinds>
- [<span data-ttu-id="5a696-129">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="5a696-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="5a696-130">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a696-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
