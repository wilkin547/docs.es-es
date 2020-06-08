---
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
ms.openlocfilehash: 55fcde6c47705e515eb2d20f25ac870e257b92c0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501136"
---
# <a name="imetadatatables2getmetadatastorage-method"></a><span data-ttu-id="15aba-102">IMetaDataTables2::GetMetaDataStorage (Método)</span><span class="sxs-lookup"><span data-stu-id="15aba-102">IMetaDataTables2::GetMetaDataStorage Method</span></span>
<span data-ttu-id="15aba-103">Obtiene el tamaño y el contenido de los metadatos almacenados en la sección especificada.</span><span class="sxs-lookup"><span data-stu-id="15aba-103">Gets the size and contents of the metadata stored in the specified section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15aba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15aba-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataStorage (  
   [in, out] const void   **ppvMd,  
   [out] ULONG   *pcbMd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15aba-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15aba-105">Parameters</span></span>  
 `ppvMd`  
 <span data-ttu-id="15aba-106">[in, out] Un puntero a una sección de metadatos.</span><span class="sxs-lookup"><span data-stu-id="15aba-106">[in, out] A pointer to a metadata section.</span></span>  
  
 `pcbMd`  
 <span data-ttu-id="15aba-107">enuncia Tamaño de la secuencia de metadatos.</span><span class="sxs-lookup"><span data-stu-id="15aba-107">[out] The size of the metadata stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15aba-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15aba-108">Requirements</span></span>  
 <span data-ttu-id="15aba-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15aba-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15aba-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="15aba-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="15aba-111">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="15aba-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="15aba-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15aba-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15aba-113">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="15aba-113">See also</span></span>

- [<span data-ttu-id="15aba-114">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="15aba-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
- [<span data-ttu-id="15aba-115">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="15aba-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
