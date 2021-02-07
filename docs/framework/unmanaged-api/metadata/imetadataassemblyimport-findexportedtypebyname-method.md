---
description: 'Más información sobre: IMetaDataAssemblyImport:: Findexportedtypebyname ((método)'
title: IMetaDataAssemblyImport::FindExportedTypeByName (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindExportedTypeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type:
- apiref
ms.openlocfilehash: 4a2dc2b65b7f7fe6d5f2e120c635214d457991bc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677995"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="665aa-103">IMetaDataAssemblyImport::FindExportedTypeByName (Método)</span><span class="sxs-lookup"><span data-stu-id="665aa-103">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>

<span data-ttu-id="665aa-104">Obtiene un puntero a un tipo exportado, dado su nombre y tipo envolvente.</span><span class="sxs-lookup"><span data-stu-id="665aa-104">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="665aa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="665aa-105">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="665aa-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="665aa-106">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="665aa-107">de Nombre del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="665aa-107">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="665aa-108">de Símbolo (token) de metadatos para la clase envolvente del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="665aa-108">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="665aa-109">Este valor es `mdExportedTypeNil` si el tipo exportado solicitado no es un tipo anidado.</span><span class="sxs-lookup"><span data-stu-id="665aa-109">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="665aa-110">enuncia Puntero al `mdExportedType` token que representa el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="665aa-110">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="665aa-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="665aa-111">Remarks</span></span>  

 <span data-ttu-id="665aa-112">El `FindExportedTypeByName` método utiliza las reglas estándar empleadas por el Common Language Runtime para resolver las referencias.</span><span class="sxs-lookup"><span data-stu-id="665aa-112">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="665aa-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="665aa-113">Requirements</span></span>  

 <span data-ttu-id="665aa-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="665aa-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="665aa-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="665aa-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="665aa-116">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="665aa-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="665aa-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="665aa-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="665aa-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="665aa-118">See also</span></span>

- [<span data-ttu-id="665aa-119">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="665aa-119">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="665aa-120">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="665aa-120">How the Runtime Locates Assemblies</span></span>](../../deployment/how-the-runtime-locates-assemblies.md)
