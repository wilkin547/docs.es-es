---
description: 'Más información sobre: IMetaDataEmit2:: SaveDelta ((método)'
title: IMetaDataEmit2::SaveDelta (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDelta
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDelta
helpviewer_keywords:
- IMetaDataEmit2::SaveDelta method [.NET Framework metadata]
- SaveDelta method [.NET Framework metadata]
ms.assetid: b95739fe-d2fa-4776-ae0d-31d9707ef799
topic_type:
- apiref
ms.openlocfilehash: 6e7a7527125869fea041f407da056db3eea88cbe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771774"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="80ed3-103">IMetaDataEmit2::SaveDelta (Método)</span><span class="sxs-lookup"><span data-stu-id="80ed3-103">IMetaDataEmit2::SaveDelta Method</span></span>

<span data-ttu-id="80ed3-104">Guarda los cambios de la sesión de edición y continuación actual en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="80ed3-104">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80ed3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80ed3-105">Syntax</span></span>  
  
```cpp  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80ed3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="80ed3-106">Parameters</span></span>  

 `szFile`  
 <span data-ttu-id="80ed3-107">de Nombre del archivo en el que se van a guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="80ed3-107">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="80ed3-108">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="80ed3-108">[in] Reserved.</span></span> <span data-ttu-id="80ed3-109">Debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="80ed3-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80ed3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80ed3-110">Requirements</span></span>  

 <span data-ttu-id="80ed3-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80ed3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80ed3-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="80ed3-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="80ed3-113">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="80ed3-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="80ed3-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80ed3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80ed3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="80ed3-115">See also</span></span>

- [<span data-ttu-id="80ed3-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="80ed3-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="80ed3-117">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="80ed3-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
