---
description: 'Más información sobre: IMetaDataTables2:: GetMetaDataStreamInfo ((método)'
title: IMetaDataTables2::GetMetaDataStreamInfo (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStreamInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type:
- apiref
ms.openlocfilehash: 323c31931cc97f18ff09df83c57153a3629d0a10
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799254"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="4f8a1-103">IMetaDataTables2::GetMetaDataStreamInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="4f8a1-103">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>

<span data-ttu-id="4f8a1-104">Obtiene el nombre, el tamaño y el contenido de la secuencia de metadatos en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="4f8a1-104">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f8a1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f8a1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f8a1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4f8a1-106">Parameters</span></span>  

 `ix`  
 <span data-ttu-id="4f8a1-107">de Índice de la secuencia de metadatos solicitada.</span><span class="sxs-lookup"><span data-stu-id="4f8a1-107">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="4f8a1-108">enuncia Puntero al nombre de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="4f8a1-108">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="4f8a1-109">enuncia Puntero a la secuencia de metadatos.</span><span class="sxs-lookup"><span data-stu-id="4f8a1-109">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="4f8a1-110">enuncia Tamaño, en bytes, de `ppv` .</span><span class="sxs-lookup"><span data-stu-id="4f8a1-110">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f8a1-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f8a1-111">Requirements</span></span>  

 <span data-ttu-id="4f8a1-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f8a1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f8a1-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4f8a1-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4f8a1-114">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4f8a1-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4f8a1-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f8a1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f8a1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f8a1-116">See also</span></span>

- [<span data-ttu-id="4f8a1-117">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4f8a1-117">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
- [<span data-ttu-id="4f8a1-118">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4f8a1-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
