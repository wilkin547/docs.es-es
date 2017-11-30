---
title: "StrongNameSignatureVerificationEx2 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName2.StrongNameSignatureVerificationEx2
api_location: mscoree.dll
api_type: COM
f1_keywords: StrongNameSignatureVerificationEx2
helpviewer_keywords:
- StrongNameSignatureVerificationEx2 method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameSignatureVerificationEx2 method [.NET Framework hosting]
ms.assetid: dfd4133f-a074-4db3-a7ee-4f250fe9ad3a
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 823eac67a53c4534a12122b118ac46bb91530d1b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignatureverificationex2-method"></a><span data-ttu-id="c160a-102">StrongNameSignatureVerificationEx2 (Método)</span><span class="sxs-lookup"><span data-stu-id="c160a-102">StrongNameSignatureVerificationEx2 Method</span></span>
<span data-ttu-id="c160a-103">Comprueba la firma de un ensamblado con nombre seguro y proporciona una asignación de la clave ECMA a una clave real.</span><span class="sxs-lookup"><span data-stu-id="c160a-103">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c160a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c160a-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c160a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c160a-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="c160a-106">[in] La ruta de acceso al archivo ejecutable portable (.dll o .exe) del ensamblado que debe comprobarse.</span><span class="sxs-lookup"><span data-stu-id="c160a-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="c160a-107">[in] `true` para realizar la comprobación, incluso si es necesario reemplazar la configuración del registro; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="c160a-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pbEcmaPublicKey`  
 <span data-ttu-id="c160a-108">[in] Un puntero a la asignación de la clave pública ECMA a la clave real que se utiliza para la comprobación.</span><span class="sxs-lookup"><span data-stu-id="c160a-108">[in] A pointer to the mapping from the ECMA public key to the real key used for verification.</span></span>  
  
 `cbEcmaPublicKey`  
 <span data-ttu-id="c160a-109">[in] La longitud de la clave pública de ECMA real.</span><span class="sxs-lookup"><span data-stu-id="c160a-109">[in] The length of the real ECMA public key.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="c160a-110">[out] `true` si la firma de nombre seguro se ha comprobado; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="c160a-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="c160a-111">Este parámetro también se establece en `false` si la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="c160a-111">This parameter is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c160a-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c160a-112">Return Value</span></span>  
 <span data-ttu-id="c160a-113">`S_OK`Si la comprobación se realizó correctamente; en caso contrario, un valor HRESULT que indica un error (vea [valores HRESULT comunes](http://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="c160a-113">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c160a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c160a-114">Requirements</span></span>  
 <span data-ttu-id="c160a-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c160a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c160a-116">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c160a-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c160a-117">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c160a-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c160a-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c160a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c160a-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c160a-119">See Also</span></span>  
 [<span data-ttu-id="c160a-120">StrongNameSignatureVerification (método)</span><span class="sxs-lookup"><span data-stu-id="c160a-120">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="c160a-121">StrongNameSignatureVerificationEx (método)</span><span class="sxs-lookup"><span data-stu-id="c160a-121">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="c160a-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c160a-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
