---
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
ms.openlocfilehash: b1672d98d76241e5af4b6b60a38785f1278e15a8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731597"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="a0cb3-102">IMetaDataAssemblyImport::FindExportedTypeByName (Método)</span><span class="sxs-lookup"><span data-stu-id="a0cb3-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>

<span data-ttu-id="a0cb3-103">Obtiene un puntero a un tipo exportado, dado su nombre y tipo envolvente.</span><span class="sxs-lookup"><span data-stu-id="a0cb3-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0cb3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0cb3-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0cb3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a0cb3-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="a0cb3-106">de Nombre del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="a0cb3-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="a0cb3-107">de Símbolo (token) de metadatos para la clase envolvente del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="a0cb3-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="a0cb3-108">Este valor es `mdExportedTypeNil` si el tipo exportado solicitado no es un tipo anidado.</span><span class="sxs-lookup"><span data-stu-id="a0cb3-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="a0cb3-109">enuncia Puntero al `mdExportedType` token que representa el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="a0cb3-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0cb3-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a0cb3-110">Remarks</span></span>  

 <span data-ttu-id="a0cb3-111">El `FindExportedTypeByName` método utiliza las reglas estándar empleadas por el Common Language Runtime para resolver las referencias.</span><span class="sxs-lookup"><span data-stu-id="a0cb3-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0cb3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a0cb3-112">Requirements</span></span>  

 <span data-ttu-id="a0cb3-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0cb3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0cb3-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a0cb3-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0cb3-115">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a0cb3-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a0cb3-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0cb3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0cb3-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a0cb3-117">See also</span></span>

- [<span data-ttu-id="a0cb3-118">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0cb3-118">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="a0cb3-119">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="a0cb3-119">How the Runtime Locates Assemblies</span></span>](../../deployment/how-the-runtime-locates-assemblies.md)
