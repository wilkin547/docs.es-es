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
ms.openlocfilehash: 3e470250fa0e86610fcc9a6d6e2ca03569d62b54
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449446"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="e2104-102">IMetaDataAssemblyImport::FindExportedTypeByName (Método)</span><span class="sxs-lookup"><span data-stu-id="e2104-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="e2104-103">Obtiene un puntero a un tipo exportado, dado su nombre y tipo envolvente.</span><span class="sxs-lookup"><span data-stu-id="e2104-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2104-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2104-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2104-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e2104-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="e2104-106">de Nombre del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="e2104-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="e2104-107">de Símbolo (token) de metadatos para la clase envolvente del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="e2104-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="e2104-108">Este valor se `mdExportedTypeNil` si el tipo exportado solicitado no es un tipo anidado.</span><span class="sxs-lookup"><span data-stu-id="e2104-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="e2104-109">enuncia Puntero al token de `mdExportedType` que representa el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="e2104-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2104-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e2104-110">Remarks</span></span>  
 <span data-ttu-id="e2104-111">El método `FindExportedTypeByName` utiliza las reglas estándar empleadas por el Common Language Runtime para resolver las referencias.</span><span class="sxs-lookup"><span data-stu-id="e2104-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2104-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2104-112">Requirements</span></span>  
 <span data-ttu-id="e2104-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2104-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2104-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e2104-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e2104-115">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e2104-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e2104-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2104-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2104-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2104-117">See also</span></span>

- [<span data-ttu-id="e2104-118">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e2104-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="e2104-119">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="e2104-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
