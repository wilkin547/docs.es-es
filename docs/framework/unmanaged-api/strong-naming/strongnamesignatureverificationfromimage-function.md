---
description: 'Más información acerca de: Strongnamesignatureverificationfromimage ((función)'
title: StrongNameSignatureVerificationFromImage (Función)
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- StrongnameSignatureVerificationFromImage function [.NET Framework strong naming]
ms.assetid: 9fb144d2-07e0-4a0e-8e05-907bbb6c9e03
topic_type:
- apiref
ms.openlocfilehash: 9dca8d0b221dfe8959be2de9b8347b95d3802a0e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794499"
---
# <a name="strongnamesignatureverificationfromimage-function"></a><span data-ttu-id="10281-103">StrongNameSignatureVerificationFromImage (Función)</span><span class="sxs-lookup"><span data-stu-id="10281-103">StrongNameSignatureVerificationFromImage Function</span></span>

<span data-ttu-id="10281-104">Comprueba si un ensamblado que ya se ha asignado a la memoria es válido para la clave pública asociada.</span><span class="sxs-lookup"><span data-stu-id="10281-104">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
 <span data-ttu-id="10281-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="10281-105">This function has been deprecated.</span></span> <span data-ttu-id="10281-106">Use el método [ICLRStrongName:: StrongNameVerificationFromImage](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="10281-106">Use the [ICLRStrongName::StrongNameVerificationFromImage](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10281-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10281-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10281-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="10281-108">Parameters</span></span>  

 `pbBase`  
 <span data-ttu-id="10281-109">de Dirección virtual relativa del manifiesto del ensamblado asignado.</span><span class="sxs-lookup"><span data-stu-id="10281-109">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="10281-110">de Tamaño, en bytes, de la imagen asignada.</span><span class="sxs-lookup"><span data-stu-id="10281-110">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="10281-111">de Marcas que influyen en el comportamiento de la comprobación.</span><span class="sxs-lookup"><span data-stu-id="10281-111">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="10281-112">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="10281-112">The following values are supported:</span></span>  
  
- <span data-ttu-id="10281-113">`SN_INFLAG_FORCE_VER` (0x00000001): fuerza la comprobación aunque sea necesario invalidar la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="10281-113">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="10281-114">`SN_INFLAG_INSTALL` (0x00000002): especifica que esta es la primera comprobación realizada en esta imagen.</span><span class="sxs-lookup"><span data-stu-id="10281-114">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
- <span data-ttu-id="10281-115">`SN_INFLAG_ADMIN_ACCESS` (0x00000004): especifica que la memoria caché permitirá el acceso solo a los usuarios que tengan privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="10281-115">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="10281-116">`SN_INFLAG_USER_ACCESS` (0x00000008): especifica que el ensamblado será accesible únicamente para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="10281-116">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="10281-117">`SN_INFLAG_ALL_ACCESS` (0x00000010): especifica que la memoria caché no proporcionará ninguna garantía de restricción de acceso.</span><span class="sxs-lookup"><span data-stu-id="10281-117">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="10281-118">`SN_INFLAG_RUNTIME` (0x80000000): reservado para la depuración interna.</span><span class="sxs-lookup"><span data-stu-id="10281-118">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="10281-119">enuncia Marca para la información de salida adicional.</span><span class="sxs-lookup"><span data-stu-id="10281-119">[out] A flag for additional output information.</span></span> <span data-ttu-id="10281-120">Se admite el siguiente valor:</span><span class="sxs-lookup"><span data-stu-id="10281-120">The following value is supported:</span></span>  
  
- <span data-ttu-id="10281-121">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001): este valor se establece en `false` para especificar que la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="10281-121">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10281-122">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="10281-122">Return Value</span></span>  

 <span data-ttu-id="10281-123">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="10281-123">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10281-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="10281-124">Remarks</span></span>  

 <span data-ttu-id="10281-125">Si la `StrongNameSignatureVerificationFromImage` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="10281-125">If the `StrongNameSignatureVerificationFromImage` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10281-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="10281-126">Requirements</span></span>  

 <span data-ttu-id="10281-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10281-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10281-128">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="10281-128">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="10281-129">**Biblioteca:** Se incluye como un recurso en mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="10281-129">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="10281-130">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10281-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10281-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="10281-131">See also</span></span>

- [<span data-ttu-id="10281-132">Método StrongNameSignatureVerificationFromImage</span><span class="sxs-lookup"><span data-stu-id="10281-132">StrongNameSignatureVerificationFromImage Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)
- [<span data-ttu-id="10281-133">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="10281-133">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
