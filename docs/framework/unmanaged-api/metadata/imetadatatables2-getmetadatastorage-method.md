---
description: 'Más información sobre: IMetaDataTables2:: GetMetaDataStorage ((método)'
title: IMetaDataTables2::GetMetaDataStorage (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStorage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStorage
helpviewer_keywords:
- GetMetaDataStorage method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStorage method [.NET Framework metadata]
ms.assetid: 667a6d1e-753d-4ea2-8fd8-a8337d1bb9cd
topic_type:
- apiref
ms.openlocfilehash: df6bbc69be05986dc6d4f143cec7ec09a2d78ee5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799257"
---
# <a name="imetadatatables2getmetadatastorage-method"></a><span data-ttu-id="05e7d-103">IMetaDataTables2::GetMetaDataStorage (Método)</span><span class="sxs-lookup"><span data-stu-id="05e7d-103">IMetaDataTables2::GetMetaDataStorage Method</span></span>

<span data-ttu-id="05e7d-104">Obtiene el tamaño y el contenido de los metadatos almacenados en la sección especificada.</span><span class="sxs-lookup"><span data-stu-id="05e7d-104">Gets the size and contents of the metadata stored in the specified section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05e7d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="05e7d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataStorage (  
   [in, out] const void   **ppvMd,  
   [out] ULONG   *pcbMd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05e7d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="05e7d-106">Parameters</span></span>  

 `ppvMd`  
 <span data-ttu-id="05e7d-107">[in, out] Un puntero a una sección de metadatos.</span><span class="sxs-lookup"><span data-stu-id="05e7d-107">[in, out] A pointer to a metadata section.</span></span>  
  
 `pcbMd`  
 <span data-ttu-id="05e7d-108">enuncia Tamaño de la secuencia de metadatos.</span><span class="sxs-lookup"><span data-stu-id="05e7d-108">[out] The size of the metadata stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05e7d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="05e7d-109">Requirements</span></span>  

 <span data-ttu-id="05e7d-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05e7d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05e7d-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="05e7d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="05e7d-112">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="05e7d-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="05e7d-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05e7d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05e7d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="05e7d-114">See also</span></span>

- [<span data-ttu-id="05e7d-115">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="05e7d-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
- [<span data-ttu-id="05e7d-116">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="05e7d-116">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
