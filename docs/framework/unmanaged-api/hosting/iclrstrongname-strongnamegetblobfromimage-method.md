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
ms.openlocfilehash: 82e18db2f5b911f0e7895959119edd7d2c722f3b
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763140"
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a><span data-ttu-id="5f505-102">ICLRStrongName::StrongNameGetBlobFromImage (Método)</span><span class="sxs-lookup"><span data-stu-id="5f505-102">ICLRStrongName::StrongNameGetBlobFromImage Method</span></span>
<span data-ttu-id="5f505-103">Obtiene una representación binaria de la imagen de ensamblado en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="5f505-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f505-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f505-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f505-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5f505-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="5f505-106">de Dirección de memoria del manifiesto del ensamblado asignado.</span><span class="sxs-lookup"><span data-stu-id="5f505-106">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="5f505-107">de Tamaño, en bytes, de la imagen en `pbBase` .</span><span class="sxs-lookup"><span data-stu-id="5f505-107">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="5f505-108">de Búfer que va a contener la representación binaria de la imagen.</span><span class="sxs-lookup"><span data-stu-id="5f505-108">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="5f505-109">[in, out] Tamaño máximo solicitado, en bytes, de `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="5f505-109">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="5f505-110">Después de la devolución, el tamaño real, en bytes, de `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="5f505-110">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f505-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5f505-111">Return Value</span></span>  
 <span data-ttu-id="5f505-112">`S_OK`Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="5f505-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f505-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f505-113">Requirements</span></span>  
 <span data-ttu-id="5f505-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f505-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f505-115">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="5f505-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5f505-116">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5f505-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f505-117">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f505-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f505-118">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="5f505-118">See also</span></span>

- [<span data-ttu-id="5f505-119">Método StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="5f505-119">StrongNameGetBlob Method</span></span>](iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="5f505-120">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f505-120">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
