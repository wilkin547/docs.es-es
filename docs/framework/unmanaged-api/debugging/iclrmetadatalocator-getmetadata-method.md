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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e677aefd5420f71867c1f11a2c9408c77d305c45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697841"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a><span data-ttu-id="20971-102">ICLRMetadataLocator::GetMetadata (Método)</span><span class="sxs-lookup"><span data-stu-id="20971-102">ICLRMetadataLocator::GetMetadata Method</span></span>
<span data-ttu-id="20971-103">Llamado por los servicios de acceso a datos de common language runtime (CLR) para recuperar los metadatos de una imagen.</span><span class="sxs-lookup"><span data-stu-id="20971-103">Called by the common language runtime (CLR) data access services to retrieve the metadata of an image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20971-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20971-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="20971-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="20971-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="20971-106">[in] Una cadena que especifica la ruta de acceso del archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="20971-106">[in] A string that specifies the path of the image file.</span></span>  
  
 `imageTimestamp`  
 <span data-ttu-id="20971-107">[in] La marca de tiempo del archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="20971-107">[in] The time stamp of the image file.</span></span>  
  
 `imageSize`  
 <span data-ttu-id="20971-108">[in] El tamaño del archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="20971-108">[in] The size of the image file.</span></span>  
  
 `mvid`  
 <span data-ttu-id="20971-109">[in] El identificador único global de la imagen.</span><span class="sxs-lookup"><span data-stu-id="20971-109">[in] The globally unique identifier of the image.</span></span>  
  
 `mdRva`  
 <span data-ttu-id="20971-110">[in] La virtual dirección relativa (RVA) de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="20971-110">[in] The relative virtual address (RVA) of the metadata.</span></span> <span data-ttu-id="20971-111">La dirección es relativa a la dirección base de imagen.</span><span class="sxs-lookup"><span data-stu-id="20971-111">The address is relative to the image base address.</span></span>  
  
 `flags`  
 <span data-ttu-id="20971-112">[in] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="20971-112">[in] Reserved for future use.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="20971-113">[in] El tamaño del búfer en el que se va a colocar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="20971-113">[in] The size of the buffer in which to place the metadata.</span></span>  
  
 `buffer`  
 <span data-ttu-id="20971-114">[out] El búfer en el que se va a colocar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="20971-114">[out] The buffer in which to place the metadata.</span></span>  
  
 `dataSize`  
 <span data-ttu-id="20971-115">[out] El tamaño de los metadatos que se devuelven.</span><span class="sxs-lookup"><span data-stu-id="20971-115">[out] The size of the metadata that is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20971-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="20971-116">Remarks</span></span>  
 <span data-ttu-id="20971-117">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="20971-117">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20971-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="20971-118">Requirements</span></span>  
 <span data-ttu-id="20971-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20971-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20971-120">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="20971-120">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="20971-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20971-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20971-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20971-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20971-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="20971-123">See also</span></span>

- [<span data-ttu-id="20971-124">ICLRMetadataLocator (interfaz)</span><span class="sxs-lookup"><span data-stu-id="20971-124">ICLRMetadataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)
