---
title: StrongNameKeyGenEx (Función)
ms.date: 03/30/2017
api_name:
- StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGenEx
helpviewer_keywords:
- StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af75a645b11325b96740807f9a3df65f5a676026
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120866"
---
# <a name="strongnamekeygenex-function"></a><span data-ttu-id="3630b-102">StrongNameKeyGenEx (Función)</span><span class="sxs-lookup"><span data-stu-id="3630b-102">StrongNameKeyGenEx Function</span></span>
<span data-ttu-id="3630b-103">Genera un nuevo par de claves pública y privada con el tamaño de clave especificado para su uso de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="3630b-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
 <span data-ttu-id="3630b-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="3630b-104">This function has been deprecated.</span></span> <span data-ttu-id="3630b-105">Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="3630b-105">Use the [ICLRStrongName::StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3630b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3630b-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3630b-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3630b-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="3630b-108">[in] El nombre del contenedor de claves solicitado.</span><span class="sxs-lookup"><span data-stu-id="3630b-108">[in] The requested key container name.</span></span> `wszKeyContainer` <span data-ttu-id="3630b-109">debe ser una cadena no vacía o null para generar un nombre temporal.</span><span class="sxs-lookup"><span data-stu-id="3630b-109">must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3630b-110">[in] Especifica si se debe abandonar la clave registrada.</span><span class="sxs-lookup"><span data-stu-id="3630b-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="3630b-111">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="3630b-111">The following values are supported:</span></span>  
  
-   <span data-ttu-id="3630b-112">0 x 00000000: se usa cuando `wszKeyContainer` es nulo para generar un nombre de contenedor de claves temporal.</span><span class="sxs-lookup"><span data-stu-id="3630b-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="3630b-113">0 x 00000001 (`SN_LEAVE_KEY`): Especifica que se debe registrar la clave izquierda.</span><span class="sxs-lookup"><span data-stu-id="3630b-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="3630b-114">[in] El tamaño solicitado de la clave en bits.</span><span class="sxs-lookup"><span data-stu-id="3630b-114">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="3630b-115">[out] El par de claves pública y privada devuelto.</span><span class="sxs-lookup"><span data-stu-id="3630b-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="3630b-116">[out] El tamaño, en bytes, de `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="3630b-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3630b-117">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3630b-117">Return Value</span></span>  
 `true` <span data-ttu-id="3630b-118">Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="3630b-118">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3630b-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3630b-119">Remarks</span></span>  
 <span data-ttu-id="3630b-120">Las versiones 1.0 y 1.1 de .NET Framework requieren una `dwKeySize` de 1024 bits para firmar un ensamblado con un nombre seguro; versión 2.0 agrega compatibilidad para las claves de 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="3630b-120">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="3630b-121">Después de recupera la clave, debe llamar a la [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) función para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="3630b-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="3630b-122">Si el `StrongNameKeyGenEx` función no se completa correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="3630b-122">If the `StrongNameKeyGenEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3630b-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3630b-123">Requirements</span></span>  
 <span data-ttu-id="3630b-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3630b-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3630b-125">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="3630b-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="3630b-126">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3630b-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="3630b-127">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3630b-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3630b-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="3630b-128">See also</span></span>

- [<span data-ttu-id="3630b-129">Método StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="3630b-129">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="3630b-130">Método StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="3630b-130">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="3630b-131">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3630b-131">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
