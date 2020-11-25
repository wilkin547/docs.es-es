---
title: StrongNameGetBlob (Función)
ms.date: 03/30/2017
api_name:
- StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlob
helpviewer_keywords:
- StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type:
- apiref
ms.openlocfilehash: 8f5cb89294004dfb1f020627ceb1edb58735f72c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732286"
---
# <a name="strongnamegetblob-function"></a><span data-ttu-id="94d95-102">StrongNameGetBlob (Función)</span><span class="sxs-lookup"><span data-stu-id="94d95-102">StrongNameGetBlob Function</span></span>

<span data-ttu-id="94d95-103">Llena el búfer especificado con la representación binaria del archivo ejecutable en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="94d95-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
 <span data-ttu-id="94d95-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="94d95-104">This function has been deprecated.</span></span> <span data-ttu-id="94d95-105">Use el método [ICLRStrongName:: strongnamegetblob (](../hosting/iclrstrongname-strongnamegetblob-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="94d95-105">Use the [ICLRStrongName::StrongNameGetBLob](../hosting/iclrstrongname-strongnamegetblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94d95-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94d95-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94d95-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="94d95-107">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="94d95-108">de Ruta de acceso válida al archivo ejecutable que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="94d95-108">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="94d95-109">de Búfer en el que se va a cargar el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="94d95-109">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="94d95-110">[in, out] Tamaño máximo solicitado, en bytes, de `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="94d95-110">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="94d95-111">Después de la devolución, el tamaño real, en bytes, de `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="94d95-111">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94d95-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="94d95-112">Return Value</span></span>  

 <span data-ttu-id="94d95-113">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="94d95-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94d95-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="94d95-114">Remarks</span></span>  

 <span data-ttu-id="94d95-115">Si la `StrongNameGetBlob` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="94d95-115">If the `StrongNameGetBlob` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94d95-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94d95-116">Requirements</span></span>  

 <span data-ttu-id="94d95-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94d95-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94d95-118">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="94d95-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="94d95-119">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="94d95-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="94d95-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94d95-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94d95-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="94d95-121">See also</span></span>

- [<span data-ttu-id="94d95-122">Método StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="94d95-122">StrongNameGetBlob Method</span></span>](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="94d95-123">Método StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="94d95-123">StrongNameGetBlobFromImage Method</span></span>](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="94d95-124">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="94d95-124">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
