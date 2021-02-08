---
description: 'Más información sobre: IMetaDataAssemblyImport:: Getassemblyfromscope ((método)'
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
ms.openlocfilehash: 78e2862fca80dc06c37436f3d81db4b19c4ec332
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784163"
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a><span data-ttu-id="dd918-103">IMetaDataAssemblyImport::GetAssemblyFromScope (Método)</span><span class="sxs-lookup"><span data-stu-id="dd918-103">IMetaDataAssemblyImport::GetAssemblyFromScope Method</span></span>

<span data-ttu-id="dd918-104">Obtiene un puntero al ensamblado en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="dd918-104">Gets a pointer to the assembly in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd918-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd918-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd918-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dd918-106">Parameters</span></span>  

 `ptkAssembly`  
 <span data-ttu-id="dd918-107">enuncia Puntero al token recuperado `mdAssembly` que identifica el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dd918-107">[out] A pointer to the retrieved `mdAssembly` token that identifies the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd918-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd918-108">Requirements</span></span>  

 <span data-ttu-id="dd918-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd918-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd918-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="dd918-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dd918-111">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dd918-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dd918-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd918-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd918-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd918-113">See also</span></span>

- [<span data-ttu-id="dd918-114">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd918-114">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
