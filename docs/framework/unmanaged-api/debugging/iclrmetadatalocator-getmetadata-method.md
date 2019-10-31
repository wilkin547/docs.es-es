---
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
ms.openlocfilehash: 1f28a4b4acd9d6050d33b9824aa49a9b9041b59b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111245"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a><span data-ttu-id="8373b-102">ICLRMetadataLocator::GetMetadata (Método)</span><span class="sxs-lookup"><span data-stu-id="8373b-102">ICLRMetadataLocator::GetMetadata Method</span></span>
<span data-ttu-id="8373b-103">Lo llama el servicio de acceso a datos de Common Language Runtime (CLR) para recuperar los metadatos de una imagen.</span><span class="sxs-lookup"><span data-stu-id="8373b-103">Called by the common language runtime (CLR) data access services to retrieve the metadata of an image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8373b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8373b-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="8373b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8373b-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="8373b-106">de Cadena que especifica la ruta de acceso del archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="8373b-106">[in] A string that specifies the path of the image file.</span></span>  
  
 `imageTimestamp`  
 <span data-ttu-id="8373b-107">de Marca de tiempo del archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="8373b-107">[in] The time stamp of the image file.</span></span>  
  
 `imageSize`  
 <span data-ttu-id="8373b-108">de Tamaño del archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="8373b-108">[in] The size of the image file.</span></span>  
  
 `mvid`  
 <span data-ttu-id="8373b-109">de Identificador único global de la imagen.</span><span class="sxs-lookup"><span data-stu-id="8373b-109">[in] The globally unique identifier of the image.</span></span>  
  
 `mdRva`  
 <span data-ttu-id="8373b-110">de La dirección virtual relativa (RVA) de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="8373b-110">[in] The relative virtual address (RVA) of the metadata.</span></span> <span data-ttu-id="8373b-111">La dirección es relativa a la dirección base de la imagen.</span><span class="sxs-lookup"><span data-stu-id="8373b-111">The address is relative to the image base address.</span></span>  
  
 `flags`  
 <span data-ttu-id="8373b-112">de Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="8373b-112">[in] Reserved for future use.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="8373b-113">de Tamaño del búfer en el que se colocan los metadatos.</span><span class="sxs-lookup"><span data-stu-id="8373b-113">[in] The size of the buffer in which to place the metadata.</span></span>  
  
 `buffer`  
 <span data-ttu-id="8373b-114">enuncia Búfer en el que se colocan los metadatos.</span><span class="sxs-lookup"><span data-stu-id="8373b-114">[out] The buffer in which to place the metadata.</span></span>  
  
 `dataSize`  
 <span data-ttu-id="8373b-115">enuncia Tamaño de los metadatos que se devuelven.</span><span class="sxs-lookup"><span data-stu-id="8373b-115">[out] The size of the metadata that is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8373b-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8373b-116">Remarks</span></span>  
 <span data-ttu-id="8373b-117">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="8373b-117">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8373b-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8373b-118">Requirements</span></span>  
 <span data-ttu-id="8373b-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8373b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8373b-120">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="8373b-120">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="8373b-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8373b-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8373b-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8373b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8373b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="8373b-123">See also</span></span>

- [<span data-ttu-id="8373b-124">ICLRMetadataLocator (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8373b-124">ICLRMetadataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)
