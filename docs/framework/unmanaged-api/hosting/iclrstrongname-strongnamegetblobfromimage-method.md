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
ms.openlocfilehash: a0bcc62a1715fb455f0affee64a351cabe0ba3f6
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901123"
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a><span data-ttu-id="6c31c-102">ICLRStrongName::StrongNameGetBlobFromImage (Método)</span><span class="sxs-lookup"><span data-stu-id="6c31c-102">ICLRStrongName::StrongNameGetBlobFromImage Method</span></span>
<span data-ttu-id="6c31c-103">Obtiene una representación binaria de la imagen de ensamblado en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="6c31c-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c31c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c31c-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c31c-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="6c31c-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="6c31c-106">de Dirección de memoria del manifiesto del ensamblado asignado.</span><span class="sxs-lookup"><span data-stu-id="6c31c-106">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="6c31c-107">de Tamaño, en bytes, de la imagen en `pbBase`.</span><span class="sxs-lookup"><span data-stu-id="6c31c-107">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="6c31c-108">de Búfer que va a contener la representación binaria de la imagen.</span><span class="sxs-lookup"><span data-stu-id="6c31c-108">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="6c31c-109">[in, out] Tamaño máximo solicitado, en bytes, de `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="6c31c-109">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="6c31c-110">Cuando se devuelve, el tamaño real, en bytes, de `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="6c31c-110">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c31c-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6c31c-111">Return Value</span></span>  
 <span data-ttu-id="6c31c-112">`S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="6c31c-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c31c-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="6c31c-113">Requirements</span></span>  
 <span data-ttu-id="6c31c-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c31c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c31c-115">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="6c31c-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6c31c-116">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6c31c-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c31c-117">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c31c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c31c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c31c-118">See also</span></span>

- [<span data-ttu-id="6c31c-119">StrongNameGetBlob (método)</span><span class="sxs-lookup"><span data-stu-id="6c31c-119">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="6c31c-120">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c31c-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
