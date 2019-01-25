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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3caa9e6f45368f4d09ed79159c650aac1e5b25e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678543"
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="67cea-102">ICLRStrongName::StrongNameGetBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="67cea-102">ICLRStrongName::StrongNameGetBlob Method</span></span>
<span data-ttu-id="67cea-103">Llena el búfer especificado con la representación binaria del archivo ejecutable en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="67cea-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67cea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67cea-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67cea-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="67cea-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="67cea-106">[in] Una ruta de acceso válida para el archivo ejecutable que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="67cea-106">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="67cea-107">[in] Búfer en el que se va a cargar el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="67cea-107">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="67cea-108">[in, out] El solicita el tamaño máximo, en bytes, de `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="67cea-108">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="67cea-109">Cuando se devuelve, el tamaño real, en bytes, de `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="67cea-109">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67cea-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="67cea-110">Return Value</span></span>  
 <span data-ttu-id="67cea-111">`S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="67cea-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67cea-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="67cea-112">Requirements</span></span>  
 <span data-ttu-id="67cea-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67cea-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67cea-114">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="67cea-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="67cea-115">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="67cea-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67cea-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67cea-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67cea-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="67cea-117">See also</span></span>
- [<span data-ttu-id="67cea-118">StrongNameGetBlobFromImage (método)</span><span class="sxs-lookup"><span data-stu-id="67cea-118">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="67cea-119">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="67cea-119">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
