---
description: 'Más información sobre: ICLRStrongName:: Strongnamegetblobfromimage ((método)'
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
ms.openlocfilehash: 32f04e21f1f08f3872ccdd27a64f39ea29d7e060
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799621"
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a><span data-ttu-id="3b043-103">ICLRStrongName::StrongNameGetBlobFromImage (Método)</span><span class="sxs-lookup"><span data-stu-id="3b043-103">ICLRStrongName::StrongNameGetBlobFromImage Method</span></span>

<span data-ttu-id="3b043-104">Obtiene una representación binaria de la imagen de ensamblado en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="3b043-104">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b043-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b043-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b043-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3b043-106">Parameters</span></span>  

 `pbBase`  
 <span data-ttu-id="3b043-107">de Dirección de memoria del manifiesto del ensamblado asignado.</span><span class="sxs-lookup"><span data-stu-id="3b043-107">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="3b043-108">de Tamaño, en bytes, de la imagen en `pbBase` .</span><span class="sxs-lookup"><span data-stu-id="3b043-108">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="3b043-109">de Búfer que va a contener la representación binaria de la imagen.</span><span class="sxs-lookup"><span data-stu-id="3b043-109">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="3b043-110">[in, out] Tamaño máximo solicitado, en bytes, de `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="3b043-110">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="3b043-111">Después de la devolución, el tamaño real, en bytes, de `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="3b043-111">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b043-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3b043-112">Return Value</span></span>  

 <span data-ttu-id="3b043-113">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="3b043-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b043-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b043-114">Requirements</span></span>  

 <span data-ttu-id="3b043-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b043-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b043-116">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="3b043-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3b043-117">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3b043-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b043-118">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b043-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b043-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b043-119">See also</span></span>

- [<span data-ttu-id="3b043-120">Método StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="3b043-120">StrongNameGetBlob Method</span></span>](iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="3b043-121">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b043-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
