---
title: ICLRStrongName::StrongNameGetBlob (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlob
- ICLRStrongName.StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlob
helpviewer_keywords:
- ICLRStrongName::StrongNameGetBlob method [.NET Framework hosting]
- StrongNameGetBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: a24218f8-7196-44be-b7a2-ee9cdd7a85c4
topic_type:
- apiref
ms.openlocfilehash: c7f04364cc52bd38d7d2659d1d188c5fd783ad01
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899761"
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="36370-102">ICLRStrongName::StrongNameGetBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="36370-102">ICLRStrongName::StrongNameGetBlob Method</span></span>
<span data-ttu-id="36370-103">Llena el búfer especificado con la representación binaria del archivo ejecutable en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="36370-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36370-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36370-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36370-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="36370-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="36370-106">de Ruta de acceso válida al archivo ejecutable que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="36370-106">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="36370-107">de Búfer en el que se va a cargar el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="36370-107">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="36370-108">[in, out] Tamaño máximo solicitado, en bytes, de `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="36370-108">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="36370-109">Cuando se devuelve, el tamaño real, en bytes, de `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="36370-109">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36370-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="36370-110">Return Value</span></span>  
 <span data-ttu-id="36370-111">`S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="36370-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36370-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="36370-112">Requirements</span></span>  
 <span data-ttu-id="36370-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36370-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36370-114">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="36370-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="36370-115">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="36370-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="36370-116">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36370-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36370-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="36370-117">See also</span></span>

- [<span data-ttu-id="36370-118">StrongNameGetBlobFromImage (método)</span><span class="sxs-lookup"><span data-stu-id="36370-118">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="36370-119">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="36370-119">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
