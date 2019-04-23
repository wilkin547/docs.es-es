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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0f70187ba9bd71225162e6e10184e4992b5600f5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228853"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="d3178-102">IMetaDataTables2::GetMetaDataStreamInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="d3178-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>
<span data-ttu-id="d3178-103">Obtiene el nombre, el tamaño y el contenido de la secuencia de metadatos en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="d3178-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3178-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3178-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3178-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d3178-105">Parameters</span></span>  
 `ix`  
 <span data-ttu-id="d3178-106">[in] El índice de la secuencia de metadatos solicitada.</span><span class="sxs-lookup"><span data-stu-id="d3178-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="d3178-107">[out] Un puntero al nombre de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="d3178-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="d3178-108">[out] Un puntero a la secuencia de metadatos.</span><span class="sxs-lookup"><span data-stu-id="d3178-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="d3178-109">[out] El tamaño, en bytes, de `ppv`.</span><span class="sxs-lookup"><span data-stu-id="d3178-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3178-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3178-110">Requirements</span></span>  
 <span data-ttu-id="d3178-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3178-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3178-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="d3178-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d3178-113">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d3178-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d3178-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3178-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3178-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3178-115">See also</span></span>

- [<span data-ttu-id="d3178-116">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3178-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
- [<span data-ttu-id="d3178-117">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3178-117">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
