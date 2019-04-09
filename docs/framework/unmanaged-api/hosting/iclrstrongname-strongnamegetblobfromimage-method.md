---
title: ICLRStrongName::StrongNameGetBlobFromImage (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetBlobFromImage method [.NET Framework hosting]
ms.assetid: 0f5a2ec8-e776-4fd8-bda6-937b6834575a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fa83f55a03ebfff9ae88217b01c86272bf0de93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178976"
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a><span data-ttu-id="8aab5-102">ICLRStrongName::StrongNameGetBlobFromImage (Método)</span><span class="sxs-lookup"><span data-stu-id="8aab5-102">ICLRStrongName::StrongNameGetBlobFromImage Method</span></span>
<span data-ttu-id="8aab5-103">Obtiene una representación binaria de la imagen de ensamblado en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="8aab5-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aab5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8aab5-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8aab5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8aab5-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="8aab5-106">[in] La dirección de memoria del manifiesto del ensamblado asignado.</span><span class="sxs-lookup"><span data-stu-id="8aab5-106">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="8aab5-107">[in] El tamaño, en bytes, de la imagen en `pbBase`.</span><span class="sxs-lookup"><span data-stu-id="8aab5-107">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="8aab5-108">[in] Un búfer que contiene la representación binaria de la imagen.</span><span class="sxs-lookup"><span data-stu-id="8aab5-108">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="8aab5-109">[in, out] El solicita el tamaño máximo, en bytes, de `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="8aab5-109">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="8aab5-110">Cuando se devuelve, el tamaño real, en bytes, de `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="8aab5-110">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8aab5-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8aab5-111">Return Value</span></span>  
 `S_OK` <span data-ttu-id="8aab5-112">Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="8aab5-112">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8aab5-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8aab5-113">Requirements</span></span>  
 <span data-ttu-id="8aab5-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8aab5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8aab5-115">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="8aab5-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8aab5-116">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8aab5-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="8aab5-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8aab5-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8aab5-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="8aab5-118">See also</span></span>

- [<span data-ttu-id="8aab5-119">Método StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="8aab5-119">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="8aab5-120">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8aab5-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
