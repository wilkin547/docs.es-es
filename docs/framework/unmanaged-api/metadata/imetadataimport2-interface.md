---
description: 'Más información acerca de: interfaz IMetaDataImport2'
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
ms.openlocfilehash: de1b190ae174c6028e4f116d7f6fc0b9af0aac6d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688551"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="b704b-103">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b704b-103">IMetaDataImport2 Interface</span></span>

<span data-ttu-id="b704b-104">Extiende la interfaz [IMetaDataImport](imetadataimport-interface.md) para proporcionar la capacidad de trabajar con tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="b704b-104">Extends the [IMetaDataImport](imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b704b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b704b-105">Methods</span></span>  
  
|<span data-ttu-id="b704b-106">Método</span><span class="sxs-lookup"><span data-stu-id="b704b-106">Method</span></span>|<span data-ttu-id="b704b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b704b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b704b-108">Método EnumGenericParamConstraints</span><span class="sxs-lookup"><span data-stu-id="b704b-108">EnumGenericParamConstraints Method</span></span>](imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="b704b-109">Obtiene un enumerador para una matriz de restricciones de parámetros genéricos asociada al parámetro genérico representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="b704b-109">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="b704b-110">Método EnumGenericParams</span><span class="sxs-lookup"><span data-stu-id="b704b-110">EnumGenericParams Method</span></span>](imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="b704b-111">Obtiene un enumerador para una matriz de tokens de parámetro genéricos asociados al token de TypeDef o MethodDef especificado.</span><span class="sxs-lookup"><span data-stu-id="b704b-111">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="b704b-112">Método EnumMethodSpecs</span><span class="sxs-lookup"><span data-stu-id="b704b-112">EnumMethodSpecs Method</span></span>](imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="b704b-113">Obtiene un enumerador para una matriz de tokens MethodSpec asociados al token MethodDef o MemberRef especificado.</span><span class="sxs-lookup"><span data-stu-id="b704b-113">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="b704b-114">Método GetGenericParamConstraintProps</span><span class="sxs-lookup"><span data-stu-id="b704b-114">GetGenericParamConstraintProps Method</span></span>](imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="b704b-115">Obtiene los metadatos asociados a la restricción de parámetro genérico que representa el token de restricción especificado.</span><span class="sxs-lookup"><span data-stu-id="b704b-115">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="b704b-116">Método GetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="b704b-116">GetGenericParamProps Method</span></span>](imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="b704b-117">Obtiene los metadatos asociados al parámetro genérico representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="b704b-117">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="b704b-118">Método GetMethodSpecProps</span><span class="sxs-lookup"><span data-stu-id="b704b-118">GetMethodSpecProps Method</span></span>](imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="b704b-119">Obtiene la firma de metadatos del método al que hace referencia el token MethodSpec especificado.</span><span class="sxs-lookup"><span data-stu-id="b704b-119">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="b704b-120">Método GetPEKind</span><span class="sxs-lookup"><span data-stu-id="b704b-120">GetPEKind Method</span></span>](imetadataimport2-getpekind-method.md)|<span data-ttu-id="b704b-121">Obtiene un valor que identifica la naturaleza del código en un archivo portable ejecutable (PE), normalmente un archivo DLL o EXE, definido en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="b704b-121">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="b704b-122">Método GetVersionString</span><span class="sxs-lookup"><span data-stu-id="b704b-122">GetVersionString Method</span></span>](imetadataimport2-getversionstring-method.md)|<span data-ttu-id="b704b-123">Obtiene el número de versión del motor en tiempo de ejecución que se usó para compilar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b704b-123">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b704b-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b704b-124">Requirements</span></span>  

 <span data-ttu-id="b704b-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b704b-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b704b-126">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b704b-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b704b-127">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b704b-127">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b704b-128">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b704b-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b704b-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="b704b-129">See also</span></span>

- <xref:System.Reflection.PortableExecutableKinds>
- [<span data-ttu-id="b704b-130">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="b704b-130">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="b704b-131">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b704b-131">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
