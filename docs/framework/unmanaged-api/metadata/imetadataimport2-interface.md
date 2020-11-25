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
ms.openlocfilehash: a845ecfde6583d625d2a8f165443344ff9e40d05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702557"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="939a7-102">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="939a7-102">IMetaDataImport2 Interface</span></span>

<span data-ttu-id="939a7-103">Extiende la interfaz [IMetaDataImport](imetadataimport-interface.md) para proporcionar la capacidad de trabajar con tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="939a7-103">Extends the [IMetaDataImport](imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="939a7-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="939a7-104">Methods</span></span>  
  
|<span data-ttu-id="939a7-105">Método</span><span class="sxs-lookup"><span data-stu-id="939a7-105">Method</span></span>|<span data-ttu-id="939a7-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="939a7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="939a7-107">Método EnumGenericParamConstraints</span><span class="sxs-lookup"><span data-stu-id="939a7-107">EnumGenericParamConstraints Method</span></span>](imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="939a7-108">Obtiene un enumerador para una matriz de restricciones de parámetros genéricos asociada al parámetro genérico representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="939a7-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="939a7-109">Método EnumGenericParams</span><span class="sxs-lookup"><span data-stu-id="939a7-109">EnumGenericParams Method</span></span>](imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="939a7-110">Obtiene un enumerador para una matriz de tokens de parámetro genéricos asociados al token de TypeDef o MethodDef especificado.</span><span class="sxs-lookup"><span data-stu-id="939a7-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="939a7-111">Método EnumMethodSpecs</span><span class="sxs-lookup"><span data-stu-id="939a7-111">EnumMethodSpecs Method</span></span>](imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="939a7-112">Obtiene un enumerador para una matriz de tokens MethodSpec asociados al token MethodDef o MemberRef especificado.</span><span class="sxs-lookup"><span data-stu-id="939a7-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="939a7-113">Método GetGenericParamConstraintProps</span><span class="sxs-lookup"><span data-stu-id="939a7-113">GetGenericParamConstraintProps Method</span></span>](imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="939a7-114">Obtiene los metadatos asociados a la restricción de parámetro genérico que representa el token de restricción especificado.</span><span class="sxs-lookup"><span data-stu-id="939a7-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="939a7-115">Método GetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="939a7-115">GetGenericParamProps Method</span></span>](imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="939a7-116">Obtiene los metadatos asociados al parámetro genérico representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="939a7-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="939a7-117">Método GetMethodSpecProps</span><span class="sxs-lookup"><span data-stu-id="939a7-117">GetMethodSpecProps Method</span></span>](imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="939a7-118">Obtiene la firma de metadatos del método al que hace referencia el token MethodSpec especificado.</span><span class="sxs-lookup"><span data-stu-id="939a7-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="939a7-119">Método GetPEKind</span><span class="sxs-lookup"><span data-stu-id="939a7-119">GetPEKind Method</span></span>](imetadataimport2-getpekind-method.md)|<span data-ttu-id="939a7-120">Obtiene un valor que identifica la naturaleza del código en un archivo portable ejecutable (PE), normalmente un archivo DLL o EXE, definido en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="939a7-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="939a7-121">Método GetVersionString</span><span class="sxs-lookup"><span data-stu-id="939a7-121">GetVersionString Method</span></span>](imetadataimport2-getversionstring-method.md)|<span data-ttu-id="939a7-122">Obtiene el número de versión del motor en tiempo de ejecución que se usó para compilar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="939a7-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="939a7-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="939a7-123">Requirements</span></span>  

 <span data-ttu-id="939a7-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="939a7-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="939a7-125">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="939a7-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="939a7-126">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="939a7-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="939a7-127">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="939a7-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="939a7-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="939a7-128">See also</span></span>

- <xref:System.Reflection.PortableExecutableKinds>
- [<span data-ttu-id="939a7-129">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="939a7-129">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="939a7-130">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="939a7-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
