---
title: IMetaDataAssemblyImport::GetAssemblyFromScope (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope method [.NET Framework metadata]
- GetAssemblyFromScope method [.NET Framework metadata]
ms.assetid: 0b437f70-561d-48c7-abe0-0cb9ace10c08
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7914257d167d0f54d3625d252076576e5e40296b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634968"
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a><span data-ttu-id="23c66-102">IMetaDataAssemblyImport::GetAssemblyFromScope (Método)</span><span class="sxs-lookup"><span data-stu-id="23c66-102">IMetaDataAssemblyImport::GetAssemblyFromScope Method</span></span>
<span data-ttu-id="23c66-103">Obtiene un puntero al ensamblado en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="23c66-103">Gets a pointer to the assembly in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23c66-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23c66-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23c66-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="23c66-105">Parameters</span></span>  
 `ptkAssembly`  
 <span data-ttu-id="23c66-106">[out] Un puntero para el objeto recuperado `mdAssembly` símbolo (token) que identifica el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="23c66-106">[out] A pointer to the retrieved `mdAssembly` token that identifies the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23c66-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="23c66-107">Requirements</span></span>  
 <span data-ttu-id="23c66-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23c66-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23c66-109">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="23c66-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="23c66-110">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="23c66-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="23c66-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23c66-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23c66-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="23c66-112">See also</span></span>
- [<span data-ttu-id="23c66-113">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="23c66-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
