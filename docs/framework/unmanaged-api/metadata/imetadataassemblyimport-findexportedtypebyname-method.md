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
ms.openlocfilehash: edfe5de9c9d7ef9607a2eea5146194bbd4393a92
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175998"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="74f84-102">IMetaDataAssemblyImport::FindExportedTypeByName (Método)</span><span class="sxs-lookup"><span data-stu-id="74f84-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="74f84-103">Obtiene un puntero a un tipo exportado, dado su nombre y tipo envolvente.</span><span class="sxs-lookup"><span data-stu-id="74f84-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74f84-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74f84-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74f84-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74f84-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="74f84-106">[en] El nombre del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="74f84-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="74f84-107">[en] El token de metadatos para la clase envolvente del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="74f84-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="74f84-108">Este valor `mdExportedTypeNil` es si el tipo exportado solicitado no es un tipo anidado.</span><span class="sxs-lookup"><span data-stu-id="74f84-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="74f84-109">[fuera] Puntero al `mdExportedType` token que representa el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="74f84-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74f84-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="74f84-110">Remarks</span></span>  
 <span data-ttu-id="74f84-111">El `FindExportedTypeByName` método utiliza las reglas estándar empleadas por Common Language Runtime para resolver referencias.</span><span class="sxs-lookup"><span data-stu-id="74f84-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74f84-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74f84-112">Requirements</span></span>  
 <span data-ttu-id="74f84-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74f84-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74f84-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="74f84-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="74f84-115">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="74f84-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="74f84-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74f84-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74f84-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="74f84-117">See also</span></span>

- [<span data-ttu-id="74f84-118">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="74f84-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="74f84-119">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="74f84-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
