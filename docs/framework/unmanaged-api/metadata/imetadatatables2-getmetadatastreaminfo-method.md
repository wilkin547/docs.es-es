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
ms.openlocfilehash: f0301506d591a3738ea403393236c2574d48a7cb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54593971"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="fa2c1-102">IMetaDataTables2::GetMetaDataStreamInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="fa2c1-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>
<span data-ttu-id="fa2c1-103">Obtiene el nombre, el tamaño y el contenido de la secuencia de metadatos en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="fa2c1-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa2c1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa2c1-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa2c1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fa2c1-105">Parameters</span></span>  
 `ix`  
 <span data-ttu-id="fa2c1-106">[in] El índice de la secuencia de metadatos solicitada.</span><span class="sxs-lookup"><span data-stu-id="fa2c1-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="fa2c1-107">[out] Un puntero al nombre de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="fa2c1-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="fa2c1-108">[out] Un puntero a la secuencia de metadatos.</span><span class="sxs-lookup"><span data-stu-id="fa2c1-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="fa2c1-109">[out] El tamaño, en bytes, de `ppv`.</span><span class="sxs-lookup"><span data-stu-id="fa2c1-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa2c1-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa2c1-110">Requirements</span></span>  
 <span data-ttu-id="fa2c1-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa2c1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa2c1-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="fa2c1-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fa2c1-113">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fa2c1-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fa2c1-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa2c1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa2c1-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa2c1-115">See also</span></span>
- [<span data-ttu-id="fa2c1-116">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa2c1-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
- [<span data-ttu-id="fa2c1-117">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa2c1-117">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
