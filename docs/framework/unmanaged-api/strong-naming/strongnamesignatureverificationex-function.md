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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08247c1ec5b868055e4836b3c0fb520a536374e8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798923"
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="7ca9d-102">StrongNameSignatureVerificationEx (Función)</span><span class="sxs-lookup"><span data-stu-id="7ca9d-102">StrongNameSignatureVerificationEx Function</span></span>
<span data-ttu-id="7ca9d-103">Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="7ca9d-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="7ca9d-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="7ca9d-104">This function has been deprecated.</span></span> <span data-ttu-id="7ca9d-105">Use el método [ICLRStrongName:: strongnamesignatureverificationex (](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="7ca9d-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ca9d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ca9d-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ca9d-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7ca9d-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="7ca9d-108">de Ruta de acceso al archivo portable ejecutable (. exe o. dll) del ensamblado que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="7ca9d-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="7ca9d-109">de para realizar la comprobación, incluso si es necesario invalidar la configuración del registro; de lo contrario, `false`. `true`</span><span class="sxs-lookup"><span data-stu-id="7ca9d-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="7ca9d-110">enuncia Si se ha comprobado la firma de nombre seguro; en caso contrario, `false`. `true`</span><span class="sxs-lookup"><span data-stu-id="7ca9d-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="7ca9d-111">`pfWasVerified`también se establece en `false` si la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="7ca9d-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ca9d-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7ca9d-112">Return Value</span></span>  
 <span data-ttu-id="7ca9d-113">`true`Si la comprobación se realizó correctamente; en caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="7ca9d-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ca9d-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7ca9d-114">Remarks</span></span>  
 <span data-ttu-id="7ca9d-115">`StrongNameSignatureVerificationEx`proporciona una funcionalidad similar a la función [strongnamesignatureverification (](strongnamesignatureverification-function.md) .</span><span class="sxs-lookup"><span data-stu-id="7ca9d-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="7ca9d-116">Sin embargo, el segundo parámetro de entrada y el parámetro `StrongNameSignatureVerificationEx` de salida para `BOOLEAN` son de tipo `DWORD`en lugar de.</span><span class="sxs-lookup"><span data-stu-id="7ca9d-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ca9d-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ca9d-117">Requirements</span></span>  
 <span data-ttu-id="7ca9d-118">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ca9d-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ca9d-119">**Encabezado**: StrongName. h</span><span class="sxs-lookup"><span data-stu-id="7ca9d-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="7ca9d-120">**Biblioteca** Se incluye como recurso en Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7ca9d-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="7ca9d-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ca9d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ca9d-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ca9d-122">See also</span></span>

- [<span data-ttu-id="7ca9d-123">StrongNameSignatureVerificationEx (método)</span><span class="sxs-lookup"><span data-stu-id="7ca9d-123">StrongNameSignatureVerificationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="7ca9d-124">StrongNameSignatureVerification (método)</span><span class="sxs-lookup"><span data-stu-id="7ca9d-124">StrongNameSignatureVerification Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="7ca9d-125">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ca9d-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
