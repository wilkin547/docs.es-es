---
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
ms.openlocfilehash: 7d39d089c348b7320651ed21ea14ba07d7877fd4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501113"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="dc2d3-102">IMetaDataTables2::GetMetaDataStreamInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="dc2d3-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>
<span data-ttu-id="dc2d3-103">Obtiene el nombre, el tamaño y el contenido de la secuencia de metadatos en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="dc2d3-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc2d3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc2d3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc2d3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dc2d3-105">Parameters</span></span>  
 `ix`  
 <span data-ttu-id="dc2d3-106">de Índice de la secuencia de metadatos solicitada.</span><span class="sxs-lookup"><span data-stu-id="dc2d3-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="dc2d3-107">enuncia Puntero al nombre de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="dc2d3-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="dc2d3-108">enuncia Puntero a la secuencia de metadatos.</span><span class="sxs-lookup"><span data-stu-id="dc2d3-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="dc2d3-109">enuncia Tamaño, en bytes, de `ppv` .</span><span class="sxs-lookup"><span data-stu-id="dc2d3-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc2d3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc2d3-110">Requirements</span></span>  
 <span data-ttu-id="dc2d3-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc2d3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc2d3-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="dc2d3-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dc2d3-113">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dc2d3-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dc2d3-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc2d3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc2d3-115">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="dc2d3-115">See also</span></span>

- [<span data-ttu-id="dc2d3-116">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc2d3-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
- [<span data-ttu-id="dc2d3-117">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc2d3-117">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
