---
description: 'Más información acerca de: Strongnamegetblobfromimage ((función)'
title: StrongNameGetBlobFromImage (Función)
ms.date: 03/30/2017
api_name:
- StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type:
- apiref
ms.openlocfilehash: c68d6914d47fbb711c49c1e8432cae1bf33e771f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636356"
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="d6ca2-103">StrongNameGetBlobFromImage (Función)</span><span class="sxs-lookup"><span data-stu-id="d6ca2-103">StrongNameGetBlobFromImage Function</span></span>

<span data-ttu-id="d6ca2-104">Obtiene una representación binaria de la imagen de ensamblado en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="d6ca2-104">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="d6ca2-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="d6ca2-105">This function has been deprecated.</span></span> <span data-ttu-id="d6ca2-106">Use el método [ICLRStrongName:: strongnamegetblobfromimage (](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d6ca2-106">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6ca2-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6ca2-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6ca2-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d6ca2-108">Parameters</span></span>  

 `pbBase`  
 <span data-ttu-id="d6ca2-109">de Dirección de memoria del manifiesto del ensamblado asignado.</span><span class="sxs-lookup"><span data-stu-id="d6ca2-109">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="d6ca2-110">de Tamaño, en bytes, de la imagen en `pbBase` .</span><span class="sxs-lookup"><span data-stu-id="d6ca2-110">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="d6ca2-111">de Búfer que va a contener la representación binaria de la imagen.</span><span class="sxs-lookup"><span data-stu-id="d6ca2-111">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="d6ca2-112">[in, out] Tamaño máximo solicitado, en bytes, de `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="d6ca2-112">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="d6ca2-113">Después de la devolución, el tamaño real, en bytes, de `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="d6ca2-113">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d6ca2-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d6ca2-114">Return Value</span></span>  

 <span data-ttu-id="d6ca2-115">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="d6ca2-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6ca2-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d6ca2-116">Remarks</span></span>  

 <span data-ttu-id="d6ca2-117">Si la `StrongNameGetBlobFromImage` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="d6ca2-117">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6ca2-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6ca2-118">Requirements</span></span>  

 <span data-ttu-id="d6ca2-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6ca2-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6ca2-120">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="d6ca2-120">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d6ca2-121">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d6ca2-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d6ca2-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6ca2-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6ca2-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6ca2-123">See also</span></span>

- [<span data-ttu-id="d6ca2-124">Método StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="d6ca2-124">StrongNameGetBlobFromImage Method</span></span>](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="d6ca2-125">Método StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="d6ca2-125">StrongNameGetBlob Method</span></span>](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="d6ca2-126">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d6ca2-126">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
