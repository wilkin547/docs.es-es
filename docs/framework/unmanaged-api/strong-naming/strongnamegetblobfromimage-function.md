---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86b99b29a85f498a6bfa0363a446bf589876bff9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799088"
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="89047-102">StrongNameGetBlobFromImage (Función)</span><span class="sxs-lookup"><span data-stu-id="89047-102">StrongNameGetBlobFromImage Function</span></span>
<span data-ttu-id="89047-103">Obtiene una representación binaria de la imagen de ensamblado en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="89047-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="89047-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="89047-104">This function has been deprecated.</span></span> <span data-ttu-id="89047-105">Use el método [ICLRStrongName:: strongnamegetblobfromimage (](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="89047-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89047-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89047-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89047-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="89047-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="89047-108">de Dirección de memoria del manifiesto del ensamblado asignado.</span><span class="sxs-lookup"><span data-stu-id="89047-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="89047-109">de Tamaño, en bytes, de la imagen en `pbBase`.</span><span class="sxs-lookup"><span data-stu-id="89047-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="89047-110">de Búfer que va a contener la representación binaria de la imagen.</span><span class="sxs-lookup"><span data-stu-id="89047-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="89047-111">[in, out] Tamaño máximo solicitado, en bytes, de `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="89047-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="89047-112">Después de la devolución, el tamaño real, en bytes `pbBlob`, de.</span><span class="sxs-lookup"><span data-stu-id="89047-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89047-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="89047-113">Return Value</span></span>  
 <span data-ttu-id="89047-114">`true`Cuando se complete correctamente; en caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="89047-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89047-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="89047-115">Remarks</span></span>  
 <span data-ttu-id="89047-116">Si la `StrongNameGetBlobFromImage` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="89047-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89047-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89047-117">Requirements</span></span>  
 <span data-ttu-id="89047-118">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89047-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89047-119">**Encabezado**: StrongName. h</span><span class="sxs-lookup"><span data-stu-id="89047-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="89047-120">**Biblioteca** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="89047-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="89047-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89047-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89047-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="89047-122">See also</span></span>

- [<span data-ttu-id="89047-123">StrongNameGetBlobFromImage (método)</span><span class="sxs-lookup"><span data-stu-id="89047-123">StrongNameGetBlobFromImage Method</span></span>](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="89047-124">StrongNameGetBlob (método)</span><span class="sxs-lookup"><span data-stu-id="89047-124">StrongNameGetBlob Method</span></span>](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="89047-125">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="89047-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
