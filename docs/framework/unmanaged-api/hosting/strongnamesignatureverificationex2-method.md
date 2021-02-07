---
description: 'Más información sobre: método Strongnamesignatureverificationex2 ('
title: StrongNameSignatureVerificationEx2 (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameSignatureVerificationEx2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameSignatureVerificationEx2
helpviewer_keywords:
- StrongNameSignatureVerificationEx2 method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameSignatureVerificationEx2 method [.NET Framework hosting]
ms.assetid: dfd4133f-a074-4db3-a7ee-4f250fe9ad3a
topic_type:
- apiref
ms.openlocfilehash: d79491744ce1a930693d2901544ad80bf8049544
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679282"
---
# <a name="strongnamesignatureverificationex2-method"></a><span data-ttu-id="9b464-103">StrongNameSignatureVerificationEx2 (Método)</span><span class="sxs-lookup"><span data-stu-id="9b464-103">StrongNameSignatureVerificationEx2 Method</span></span>

<span data-ttu-id="9b464-104">Comprueba la firma de un ensamblado con nombre seguro y proporciona una asignación de la clave ECMA a una clave real.</span><span class="sxs-lookup"><span data-stu-id="9b464-104">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b464-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b464-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b464-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9b464-106">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="9b464-107">de Ruta de acceso al archivo portable ejecutable (. exe o. dll) del ensamblado que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="9b464-107">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="9b464-108">[in] `true` para realizar la comprobación, incluso si es necesario invalidar la configuración del registro; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="9b464-108">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pbEcmaPublicKey`  
 <span data-ttu-id="9b464-109">de Un puntero a la asignación de la clave pública ECMA a la clave real que se usa para la comprobación.</span><span class="sxs-lookup"><span data-stu-id="9b464-109">[in] A pointer to the mapping from the ECMA public key to the real key used for verification.</span></span>  
  
 `cbEcmaPublicKey`  
 <span data-ttu-id="9b464-110">de La longitud de la clave pública ECMA real.</span><span class="sxs-lookup"><span data-stu-id="9b464-110">[in] The length of the real ECMA public key.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="9b464-111">[out] `true` Si se ha comprobado la firma de nombre seguro; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="9b464-111">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="9b464-112">Este parámetro también se establece en `false` si la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="9b464-112">This parameter is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b464-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9b464-113">Return Value</span></span>  

 <span data-ttu-id="9b464-114">`S_OK` Si la comprobación se realizó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="9b464-114">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b464-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9b464-115">Requirements</span></span>  

 <span data-ttu-id="9b464-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b464-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b464-117">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="9b464-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9b464-118">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9b464-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b464-119">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b464-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b464-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b464-120">See also</span></span>

- [<span data-ttu-id="9b464-121">Método StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="9b464-121">StrongNameSignatureVerification Method</span></span>](iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="9b464-122">Método StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="9b464-122">StrongNameSignatureVerificationEx Method</span></span>](iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="9b464-123">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9b464-123">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
