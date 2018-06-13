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
ms.openlocfilehash: 7322b4d0fce36f5dbef7e82f35cf9e2a1cae24a3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444335"
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a><span data-ttu-id="44427-102">IMetaDataAssemblyImport::GetAssemblyFromScope (Método)</span><span class="sxs-lookup"><span data-stu-id="44427-102">IMetaDataAssemblyImport::GetAssemblyFromScope Method</span></span>
<span data-ttu-id="44427-103">Obtiene un puntero al ensamblado en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="44427-103">Gets a pointer to the assembly in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44427-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44427-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44427-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="44427-105">Parameters</span></span>  
 `ptkAssembly`  
 <span data-ttu-id="44427-106">[out] Un puntero para el objeto recuperado `mdAssembly` símbolo (token) que identifica el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="44427-106">[out] A pointer to the retrieved `mdAssembly` token that identifies the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44427-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44427-107">Requirements</span></span>  
 <span data-ttu-id="44427-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44427-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44427-109">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="44427-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="44427-110">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="44427-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="44427-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44427-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44427-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="44427-112">See Also</span></span>  
 [<span data-ttu-id="44427-113">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="44427-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
