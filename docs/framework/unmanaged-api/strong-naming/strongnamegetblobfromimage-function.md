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
ms.openlocfilehash: 3a84221f94bad76d69f0dc67fe695ada3f3862f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732247"
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="8cb2e-102">StrongNameGetBlobFromImage (Función)</span><span class="sxs-lookup"><span data-stu-id="8cb2e-102">StrongNameGetBlobFromImage Function</span></span>

<span data-ttu-id="8cb2e-103">Obtiene una representación binaria de la imagen de ensamblado en la dirección de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="8cb2e-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="8cb2e-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="8cb2e-104">This function has been deprecated.</span></span> <span data-ttu-id="8cb2e-105">Use el método [ICLRStrongName:: strongnamegetblobfromimage (](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="8cb2e-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cb2e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8cb2e-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cb2e-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8cb2e-107">Parameters</span></span>  

 `pbBase`  
 <span data-ttu-id="8cb2e-108">de Dirección de memoria del manifiesto del ensamblado asignado.</span><span class="sxs-lookup"><span data-stu-id="8cb2e-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="8cb2e-109">de Tamaño, en bytes, de la imagen en `pbBase` .</span><span class="sxs-lookup"><span data-stu-id="8cb2e-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="8cb2e-110">de Búfer que va a contener la representación binaria de la imagen.</span><span class="sxs-lookup"><span data-stu-id="8cb2e-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="8cb2e-111">[in, out] Tamaño máximo solicitado, en bytes, de `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="8cb2e-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="8cb2e-112">Después de la devolución, el tamaño real, en bytes, de `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="8cb2e-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8cb2e-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8cb2e-113">Return Value</span></span>  

 <span data-ttu-id="8cb2e-114">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="8cb2e-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8cb2e-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8cb2e-115">Remarks</span></span>  

 <span data-ttu-id="8cb2e-116">Si la `StrongNameGetBlobFromImage` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="8cb2e-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cb2e-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8cb2e-117">Requirements</span></span>  

 <span data-ttu-id="8cb2e-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cb2e-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cb2e-119">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="8cb2e-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="8cb2e-120">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8cb2e-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8cb2e-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cb2e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cb2e-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8cb2e-122">See also</span></span>

- [<span data-ttu-id="8cb2e-123">Método StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="8cb2e-123">StrongNameGetBlobFromImage Method</span></span>](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="8cb2e-124">Método StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="8cb2e-124">StrongNameGetBlob Method</span></span>](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="8cb2e-125">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8cb2e-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
