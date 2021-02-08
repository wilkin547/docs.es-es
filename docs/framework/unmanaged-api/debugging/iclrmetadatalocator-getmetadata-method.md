---
description: 'Más información sobre: Iclrmetadatalocator (:: GetMetadata (método)'
title: ICLRMetadataLocator::GetMetadata (Método)
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator.GetMetadata
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator::GetMetadata
helpviewer_keywords:
- GetMetadata method, ICLRMetadataLocator interface [.NET Framework debugging]
- ICLRMetadataLocator::GetMetadata method [.NET Framework debugging]
ms.assetid: 704a8893-ac56-43b4-90ea-715f38ccb40e
topic_type:
- apiref
ms.openlocfilehash: 4a7e8b906b66c4295dd24800d260790526114701
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772632"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a><span data-ttu-id="b024c-103">ICLRMetadataLocator::GetMetadata (Método)</span><span class="sxs-lookup"><span data-stu-id="b024c-103">ICLRMetadataLocator::GetMetadata Method</span></span>

<span data-ttu-id="b024c-104">Lo llama el servicio de acceso a datos de Common Language Runtime (CLR) para recuperar los metadatos de una imagen.</span><span class="sxs-lookup"><span data-stu-id="b024c-104">Called by the common language runtime (CLR) data access services to retrieve the metadata of an image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b024c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b024c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMetadata(  
    [in]  LPCWSTR         imagePath,  
    [in]  ULONG32         imageTimestamp,  
    [in]  ULONG32         imageSize,  
    [in]  GUID*           mvid,  
    [in]  ULONG32         mdRva,  
    [in]  ULONG32         flags,  
    [in]  ULONG32         bufferSize,  
    [out, size_is(bufferSize), length_is(*dataSize)]  
          BYTE*           buffer,  
    [out] ULONG32*        dataSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b024c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b024c-106">Parameters</span></span>  

 `imagePath`  
 <span data-ttu-id="b024c-107">de Cadena que especifica la ruta de acceso del archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="b024c-107">[in] A string that specifies the path of the image file.</span></span>  
  
 `imageTimestamp`  
 <span data-ttu-id="b024c-108">de Marca de tiempo del archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="b024c-108">[in] The time stamp of the image file.</span></span>  
  
 `imageSize`  
 <span data-ttu-id="b024c-109">de Tamaño del archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="b024c-109">[in] The size of the image file.</span></span>  
  
 `mvid`  
 <span data-ttu-id="b024c-110">de Identificador único global de la imagen.</span><span class="sxs-lookup"><span data-stu-id="b024c-110">[in] The globally unique identifier of the image.</span></span>  
  
 `mdRva`  
 <span data-ttu-id="b024c-111">de La dirección virtual relativa (RVA) de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="b024c-111">[in] The relative virtual address (RVA) of the metadata.</span></span> <span data-ttu-id="b024c-112">La dirección es relativa a la dirección base de la imagen.</span><span class="sxs-lookup"><span data-stu-id="b024c-112">The address is relative to the image base address.</span></span>  
  
 `flags`  
 <span data-ttu-id="b024c-113">[in] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="b024c-113">[in] Reserved for future use.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="b024c-114">de Tamaño del búfer en el que se colocan los metadatos.</span><span class="sxs-lookup"><span data-stu-id="b024c-114">[in] The size of the buffer in which to place the metadata.</span></span>  
  
 `buffer`  
 <span data-ttu-id="b024c-115">enuncia Búfer en el que se colocan los metadatos.</span><span class="sxs-lookup"><span data-stu-id="b024c-115">[out] The buffer in which to place the metadata.</span></span>  
  
 `dataSize`  
 <span data-ttu-id="b024c-116">enuncia Tamaño de los metadatos que se devuelven.</span><span class="sxs-lookup"><span data-stu-id="b024c-116">[out] The size of the metadata that is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b024c-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b024c-117">Remarks</span></span>  

 <span data-ttu-id="b024c-118">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="b024c-118">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b024c-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b024c-119">Requirements</span></span>  

 <span data-ttu-id="b024c-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b024c-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b024c-121">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="b024c-121">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b024c-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b024c-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b024c-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b024c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b024c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="b024c-124">See also</span></span>

- [<span data-ttu-id="b024c-125">ICLRMetadataLocator (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b024c-125">ICLRMetadataLocator Interface</span></span>](iclrmetadatalocator-interface.md)
