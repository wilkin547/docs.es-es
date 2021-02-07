---
description: 'Más información acerca de: IMetaDataTables:: GetBlob (método)'
title: IMetaDataTables::GetBlob (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlob
helpviewer_keywords:
- GetBlob method [.NET Framework metadata]
- IMetaDataTables::GetBlob method [.NET Framework metadata]
ms.assetid: 94667c1c-6d58-4aa7-b74e-530b11e2a276
topic_type:
- apiref
ms.openlocfilehash: 733f94c280283e00b644fe7811d450efbc7e1e7c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688395"
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="95897-103">IMetaDataTables::GetBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="95897-103">IMetaDataTables::GetBlob Method</span></span>

<span data-ttu-id="95897-104">Obtiene un puntero al objeto binario grande (BLOB) en el índice de columna especificado.</span><span class="sxs-lookup"><span data-stu-id="95897-104">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95897-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95897-105">Syntax</span></span>  
  
```cpp  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95897-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="95897-106">Parameters</span></span>  

 `ixBlob`  
 <span data-ttu-id="95897-107">de Dirección de memoria de la que se va a obtener `ppData` .</span><span class="sxs-lookup"><span data-stu-id="95897-107">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="95897-108">enuncia Puntero al tamaño, en bytes, de `ppData` .</span><span class="sxs-lookup"><span data-stu-id="95897-108">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="95897-109">enuncia Un puntero a un puntero a los datos binarios recuperados.</span><span class="sxs-lookup"><span data-stu-id="95897-109">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95897-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="95897-110">Requirements</span></span>  

 <span data-ttu-id="95897-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95897-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95897-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="95897-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="95897-113">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="95897-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="95897-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95897-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95897-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="95897-115">See also</span></span>

- [<span data-ttu-id="95897-116">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="95897-116">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="95897-117">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="95897-117">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
