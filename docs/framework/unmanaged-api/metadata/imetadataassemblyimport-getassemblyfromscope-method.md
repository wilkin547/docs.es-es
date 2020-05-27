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
ms.openlocfilehash: adcaac02526c7d72ffb75ba6c7552632173032cf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009046"
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a><span data-ttu-id="f05fa-102">IMetaDataAssemblyImport::GetAssemblyFromScope (Método)</span><span class="sxs-lookup"><span data-stu-id="f05fa-102">IMetaDataAssemblyImport::GetAssemblyFromScope Method</span></span>
<span data-ttu-id="f05fa-103">Obtiene un puntero al ensamblado en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="f05fa-103">Gets a pointer to the assembly in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f05fa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f05fa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f05fa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f05fa-105">Parameters</span></span>  
 `ptkAssembly`  
 <span data-ttu-id="f05fa-106">enuncia Puntero al token recuperado `mdAssembly` que identifica el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f05fa-106">[out] A pointer to the retrieved `mdAssembly` token that identifies the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f05fa-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f05fa-107">Requirements</span></span>  
 <span data-ttu-id="f05fa-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f05fa-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f05fa-109">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f05fa-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f05fa-110">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f05fa-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f05fa-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f05fa-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f05fa-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f05fa-112">See also</span></span>

- [<span data-ttu-id="f05fa-113">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f05fa-113">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
