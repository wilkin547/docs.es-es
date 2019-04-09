---
title: StrongNameKeyGen (Función)
ms.date: 03/30/2017
api_name:
- StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen function [.NET Framework strong naming]
ms.assetid: 883e413a-ad2f-4f7f-b1b9-aeb8fe5b65f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8ebecce4078ba6c2b59e6bfba2d54300ba0c4ee
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107385"
---
# <a name="strongnamekeygen-function"></a><span data-ttu-id="e2ee0-102">StrongNameKeyGen (Función)</span><span class="sxs-lookup"><span data-stu-id="e2ee0-102">StrongNameKeyGen Function</span></span>
<span data-ttu-id="e2ee0-103">Crea un par de claves pública y privada para su uso en nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="e2ee0-103">Creates a new public/private key pair for strong name use.</span></span>  
  
 <span data-ttu-id="e2ee0-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="e2ee0-104">This function has been deprecated.</span></span> <span data-ttu-id="e2ee0-105">Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e2ee0-105">Use the [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2ee0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2ee0-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2ee0-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e2ee0-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="e2ee0-108">[in] El nombre del contenedor de claves solicitado.</span><span class="sxs-lookup"><span data-stu-id="e2ee0-108">[in] The requested key container name.</span></span> `wszKeyContainer` <span data-ttu-id="e2ee0-109">debe ser una cadena no vacía o null para generar un nombre temporal.</span><span class="sxs-lookup"><span data-stu-id="e2ee0-109">must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e2ee0-110">[in] Especifica si se debe abandonar la clave registrada.</span><span class="sxs-lookup"><span data-stu-id="e2ee0-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="e2ee0-111">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="e2ee0-111">The following values are supported:</span></span>  
  
-   <span data-ttu-id="e2ee0-112">0 x 00000000: se usa cuando `wszKeyContainer` es nulo para generar un nombre de contenedor de claves temporal.</span><span class="sxs-lookup"><span data-stu-id="e2ee0-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="e2ee0-113">0 x 00000001 (`SN_LEAVE_KEY`): Especifica que se debe registrar la clave izquierda.</span><span class="sxs-lookup"><span data-stu-id="e2ee0-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="e2ee0-114">[out] El par de claves pública y privada devuelto.</span><span class="sxs-lookup"><span data-stu-id="e2ee0-114">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="e2ee0-115">[out] El tamaño, en bytes, de `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="e2ee0-115">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2ee0-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e2ee0-116">Return Value</span></span>  
 `true` <span data-ttu-id="e2ee0-117">Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="e2ee0-117">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2ee0-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e2ee0-118">Remarks</span></span>  
 <span data-ttu-id="e2ee0-119">El `StrongNameKeyGen` función crea una clave de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="e2ee0-119">The `StrongNameKeyGen` function creates a 1024-bit key.</span></span> <span data-ttu-id="e2ee0-120">Después de recupera la clave, debe llamar a la [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) función para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="e2ee0-120">After the key is retrieved, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="e2ee0-121">Si el `StrongNameKeyGen` función no se completa correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="e2ee0-121">If the `StrongNameKeyGen` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2ee0-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2ee0-122">Requirements</span></span>  
 <span data-ttu-id="e2ee0-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2ee0-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2ee0-124">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="e2ee0-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e2ee0-125">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e2ee0-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="e2ee0-126">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e2ee0-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e2ee0-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2ee0-127">See also</span></span>

- [<span data-ttu-id="e2ee0-128">Método StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="e2ee0-128">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="e2ee0-129">Método StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="e2ee0-129">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="e2ee0-130">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e2ee0-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
