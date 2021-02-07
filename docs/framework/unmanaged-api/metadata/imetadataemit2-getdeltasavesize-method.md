---
description: 'Más información sobre: IMetaDataEmit2:: GetDeltaSaveSize ((método)'
title: IMetaDataEmit2::GetDeltaSaveSize (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.GetDeltaSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::GetDeltaSaveSize
helpviewer_keywords:
- IMetaDataEmit2::GetDeltaSaveSize method [.NET Framework metadata]
- GetDeltaSaveSize method [.NET Framework metadata]
ms.assetid: 036db5e7-8211-4645-9a34-03d1a89be955
topic_type:
- apiref
ms.openlocfilehash: d7b5eae7f89a5465876083c5cc8021330d3c59de
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745767"
---
# <a name="imetadataemit2getdeltasavesize-method"></a><span data-ttu-id="73c42-103">IMetaDataEmit2::GetDeltaSaveSize (Método)</span><span class="sxs-lookup"><span data-stu-id="73c42-103">IMetaDataEmit2::GetDeltaSaveSize Method</span></span>

<span data-ttu-id="73c42-104">Obtiene un valor que indica cualquier cambio en el tamaño de los metadatos que es el resultado de la sesión de edición y continuación actual.</span><span class="sxs-lookup"><span data-stu-id="73c42-104">Gets a value indicating any change in metadata size that results from the current edit-and-continue session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73c42-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73c42-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73c42-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="73c42-106">Parameters</span></span>  

 `fSave`  
 <span data-ttu-id="73c42-107">de Uno de los valores de [CorSaveSize (](corsavesize-enumeration.md) , que indica el nivel de precisión que se desea.</span><span class="sxs-lookup"><span data-stu-id="73c42-107">[in] One of the [CorSaveSize](corsavesize-enumeration.md) values, indicating the level of precision desired.</span></span> <span data-ttu-id="73c42-108">En el .NET Framework versión 2,0, este parámetro se omite.</span><span class="sxs-lookup"><span data-stu-id="73c42-108">For the .NET Framework version 2.0, this parameter is ignored.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="73c42-109">enuncia Cambio en el tamaño de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="73c42-109">[out] The change in the size of the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73c42-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73c42-110">Requirements</span></span>  

 <span data-ttu-id="73c42-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73c42-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73c42-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="73c42-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="73c42-113">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="73c42-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="73c42-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73c42-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73c42-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="73c42-115">See also</span></span>

- [<span data-ttu-id="73c42-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="73c42-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="73c42-117">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="73c42-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
