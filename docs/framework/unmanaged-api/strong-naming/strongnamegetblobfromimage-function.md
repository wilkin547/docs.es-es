---
title: "StrongNameGetBlobFromImage (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameGetBlobFromImage
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameGetBlobFromImage
helpviewer_keywords: StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3dd5fa1838517baa97079f5d7f75a789384255a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="ff24a-102">StrongNameGetBlobFromImage (Función)</span><span class="sxs-lookup"><span data-stu-id="ff24a-102">StrongNameGetBlobFromImage Function</span></span>
<span data-ttu-id="ff24a-103">Obtiene una representación binaria de la imagen de ensamblado en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="ff24a-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="ff24a-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="ff24a-104">This function has been deprecated.</span></span> <span data-ttu-id="ff24a-105">Use la [ICLRStrongName:: StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="ff24a-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff24a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff24a-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff24a-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ff24a-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="ff24a-108">[in] La dirección de memoria del manifiesto del ensamblado asignado.</span><span class="sxs-lookup"><span data-stu-id="ff24a-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="ff24a-109">[in] El tamaño, en bytes, de la imagen en `pbBase`.</span><span class="sxs-lookup"><span data-stu-id="ff24a-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="ff24a-110">[in] Un búfer que contiene la representación binaria de la imagen.</span><span class="sxs-lookup"><span data-stu-id="ff24a-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="ff24a-111">[entrada, salida] El solicita el tamaño máximo, en bytes, de `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="ff24a-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="ff24a-112">Al volver, el tamaño real, en bytes, de `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="ff24a-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff24a-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ff24a-113">Return Value</span></span>  
 <span data-ttu-id="ff24a-114">`true`Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ff24a-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff24a-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ff24a-115">Remarks</span></span>  
 <span data-ttu-id="ff24a-116">Si el `StrongNameGetBlobFromImage` función no se completan correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="ff24a-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff24a-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff24a-117">Requirements</span></span>  
 <span data-ttu-id="ff24a-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff24a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff24a-119">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="ff24a-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="ff24a-120">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ff24a-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ff24a-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff24a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff24a-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff24a-122">See Also</span></span>  
 [<span data-ttu-id="ff24a-123">StrongNameGetBlobFromImage (método)</span><span class="sxs-lookup"><span data-stu-id="ff24a-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [<span data-ttu-id="ff24a-124">StrongNameGetBlob (método)</span><span class="sxs-lookup"><span data-stu-id="ff24a-124">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [<span data-ttu-id="ff24a-125">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ff24a-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
