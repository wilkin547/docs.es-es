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
ms.openlocfilehash: fe9e87618291218a41e52f80198ce9068c9c56e2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490404"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="f4925-102">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4925-102">IMetaDataImport2 Interface</span></span>
<span data-ttu-id="f4925-103">Extiende la interfaz [IMetaDataImport](imetadataimport-interface.md) para proporcionar la capacidad de trabajar con tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="f4925-103">Extends the [IMetaDataImport](imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f4925-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f4925-104">Methods</span></span>  
  
|<span data-ttu-id="f4925-105">Método</span><span class="sxs-lookup"><span data-stu-id="f4925-105">Method</span></span>|<span data-ttu-id="f4925-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4925-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f4925-107">Método EnumGenericParamConstraints</span><span class="sxs-lookup"><span data-stu-id="f4925-107">EnumGenericParamConstraints Method</span></span>](imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="f4925-108">Obtiene un enumerador para una matriz de restricciones de parámetros genéricos asociada al parámetro genérico representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="f4925-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="f4925-109">Método EnumGenericParams</span><span class="sxs-lookup"><span data-stu-id="f4925-109">EnumGenericParams Method</span></span>](imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="f4925-110">Obtiene un enumerador para una matriz de tokens de parámetro genéricos asociados al token de TypeDef o MethodDef especificado.</span><span class="sxs-lookup"><span data-stu-id="f4925-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="f4925-111">Método EnumMethodSpecs</span><span class="sxs-lookup"><span data-stu-id="f4925-111">EnumMethodSpecs Method</span></span>](imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="f4925-112">Obtiene un enumerador para una matriz de tokens MethodSpec asociados al token MethodDef o MemberRef especificado.</span><span class="sxs-lookup"><span data-stu-id="f4925-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="f4925-113">Método GetGenericParamConstraintProps</span><span class="sxs-lookup"><span data-stu-id="f4925-113">GetGenericParamConstraintProps Method</span></span>](imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="f4925-114">Obtiene los metadatos asociados a la restricción de parámetro genérico que representa el token de restricción especificado.</span><span class="sxs-lookup"><span data-stu-id="f4925-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="f4925-115">Método GetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="f4925-115">GetGenericParamProps Method</span></span>](imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="f4925-116">Obtiene los metadatos asociados al parámetro genérico representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="f4925-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="f4925-117">Método GetMethodSpecProps</span><span class="sxs-lookup"><span data-stu-id="f4925-117">GetMethodSpecProps Method</span></span>](imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="f4925-118">Obtiene la firma de metadatos del método al que hace referencia el token MethodSpec especificado.</span><span class="sxs-lookup"><span data-stu-id="f4925-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="f4925-119">Método GetPEKind</span><span class="sxs-lookup"><span data-stu-id="f4925-119">GetPEKind Method</span></span>](imetadataimport2-getpekind-method.md)|<span data-ttu-id="f4925-120">Obtiene un valor que identifica la naturaleza del código en un archivo portable ejecutable (PE), normalmente un archivo DLL o EXE, definido en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="f4925-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="f4925-121">GetVersionString (Método)</span><span class="sxs-lookup"><span data-stu-id="f4925-121">GetVersionString Method</span></span>](imetadataimport2-getversionstring-method.md)|<span data-ttu-id="f4925-122">Obtiene el número de versión del motor en tiempo de ejecución que se usó para compilar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f4925-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f4925-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4925-123">Requirements</span></span>  
 <span data-ttu-id="f4925-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4925-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4925-125">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f4925-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f4925-126">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f4925-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f4925-127">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4925-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4925-128">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="f4925-128">See also</span></span>

- <xref:System.Reflection.PortableExecutableKinds>
- [<span data-ttu-id="f4925-129">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="f4925-129">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="f4925-130">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4925-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
