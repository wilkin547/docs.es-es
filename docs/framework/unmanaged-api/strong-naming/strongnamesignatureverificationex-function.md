---
title: StrongNameSignatureVerificationEx (Función)
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type:
- apiref
ms.openlocfilehash: 27417c379411e242c48d6d9b0c99de833f7ede8a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719273"
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="e4d70-102">StrongNameSignatureVerificationEx (Función)</span><span class="sxs-lookup"><span data-stu-id="e4d70-102">StrongNameSignatureVerificationEx Function</span></span>

<span data-ttu-id="e4d70-103">Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="e4d70-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="e4d70-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="e4d70-104">This function has been deprecated.</span></span> <span data-ttu-id="e4d70-105">Use el método [ICLRStrongName:: strongnamesignatureverificationex (](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e4d70-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4d70-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4d70-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4d70-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e4d70-107">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="e4d70-108">de Ruta de acceso al archivo portable ejecutable (. exe o. dll) del ensamblado que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="e4d70-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="e4d70-109">[in] `true` para realizar la comprobación, incluso si es necesario invalidar la configuración del registro; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="e4d70-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="e4d70-110">[out] `true` Si se ha comprobado la firma de nombre seguro; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="e4d70-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="e4d70-111">`pfWasVerified` también se establece en `false` si la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="e4d70-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e4d70-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e4d70-112">Return Value</span></span>  

 <span data-ttu-id="e4d70-113">`true` Si la comprobación se realizó correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="e4d70-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4d70-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e4d70-114">Remarks</span></span>  

 <span data-ttu-id="e4d70-115">`StrongNameSignatureVerificationEx` proporciona una funcionalidad similar a la función [strongnamesignatureverification (](strongnamesignatureverification-function.md) .</span><span class="sxs-lookup"><span data-stu-id="e4d70-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="e4d70-116">Sin embargo, el segundo parámetro de entrada y el parámetro de salida para `StrongNameSignatureVerificationEx` son de tipo `BOOLEAN` en lugar de `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="e4d70-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4d70-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e4d70-117">Requirements</span></span>  

 <span data-ttu-id="e4d70-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4d70-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4d70-119">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="e4d70-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e4d70-120">**Biblioteca:** Se incluye como un recurso en mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e4d70-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="e4d70-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4d70-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4d70-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e4d70-122">See also</span></span>

- [<span data-ttu-id="e4d70-123">Método StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="e4d70-123">StrongNameSignatureVerificationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="e4d70-124">Método StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="e4d70-124">StrongNameSignatureVerification Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="e4d70-125">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e4d70-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
