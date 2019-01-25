---
title: StrongNameSignatureSize (Función)
ms.date: 03/30/2017
api_name:
- StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureSize
helpviewer_keywords:
- StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5e4e2a817abff7b0cf24223b7f245fc6f86c1d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544996"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="a6e69-102">StrongNameSignatureSize (Función)</span><span class="sxs-lookup"><span data-stu-id="a6e69-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="a6e69-103">Devuelve el tamaño de la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="a6e69-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="a6e69-104">`StrongNameSignatureSize` Normalmente se usa por los compiladores para determinar cuánto espacio se reserva en el archivo al crear un ensamblado con firma retrasada.</span><span class="sxs-lookup"><span data-stu-id="a6e69-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="a6e69-105">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="a6e69-105">This function has been deprecated.</span></span> <span data-ttu-id="a6e69-106">Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="a6e69-106">Use the [ICLRStrongName::StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6e69-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6e69-107">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="a6e69-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a6e69-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="a6e69-109">[in] Una estructura de tipo [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) que contiene la parte pública del par de claves utilizado para generar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="a6e69-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="a6e69-110">[in] El tamaño, en bytes, de `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="a6e69-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="a6e69-111">[in] El número de bytes necesarios para almacenar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="a6e69-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6e69-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a6e69-112">Return Value</span></span>  
 <span data-ttu-id="a6e69-113">`true` Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a6e69-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6e69-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a6e69-114">Remarks</span></span>  
 <span data-ttu-id="a6e69-115">Si el `StrongNameSignatureSize` función no se completa correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="a6e69-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6e69-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a6e69-116">Requirements</span></span>  
 <span data-ttu-id="a6e69-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6e69-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6e69-118">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="a6e69-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a6e69-119">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a6e69-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a6e69-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6e69-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6e69-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6e69-121">See also</span></span>
- [<span data-ttu-id="a6e69-122">StrongNameSignatureSize (método)</span><span class="sxs-lookup"><span data-stu-id="a6e69-122">StrongNameSignatureSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="a6e69-123">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a6e69-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
