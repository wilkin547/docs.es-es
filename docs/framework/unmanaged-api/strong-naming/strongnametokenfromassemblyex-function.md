---
title: StrongNameTokenFromAssemblyEx (Función)
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx function [.NET Framework strong naming]
ms.assetid: 67a8a9f2-dee3-44b2-a1c0-f307a3bdf90f
topic_type:
- apiref
ms.openlocfilehash: 566bba09f6bfac2f7616dc5caf32ef431f2e1e67
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719806"
---
# <a name="strongnametokenfromassemblyex-function"></a><span data-ttu-id="7e334-102">StrongNameTokenFromAssemblyEx (Función)</span><span class="sxs-lookup"><span data-stu-id="7e334-102">StrongNameTokenFromAssemblyEx Function</span></span>

<span data-ttu-id="7e334-103">Crea un token de nombre seguro a partir del archivo de ensamblado especificado y devuelve la clave pública que representa el token.</span><span class="sxs-lookup"><span data-stu-id="7e334-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
 <span data-ttu-id="7e334-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="7e334-104">This function has been deprecated.</span></span> <span data-ttu-id="7e334-105">Use el método [ICLRStrongName:: strongnametokenfromassemblyex (](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="7e334-105">Use the [ICLRStrongName::StrongNameTokenFromAssemblyEx](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e334-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e334-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e334-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7e334-107">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="7e334-108">de La ruta de acceso al archivo portable ejecutable (PE) para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7e334-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="7e334-109">enuncia El token de nombre seguro devuelto.</span><span class="sxs-lookup"><span data-stu-id="7e334-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="7e334-110">enuncia Tamaño, en bytes, del token de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="7e334-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="7e334-111">enuncia La clave pública devuelta.</span><span class="sxs-lookup"><span data-stu-id="7e334-111">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="7e334-112">enuncia Tamaño, en bytes, de la clave pública.</span><span class="sxs-lookup"><span data-stu-id="7e334-112">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e334-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7e334-113">Return Value</span></span>  

 <span data-ttu-id="7e334-114">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="7e334-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e334-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7e334-115">Remarks</span></span>  

 <span data-ttu-id="7e334-116">Un token de nombre seguro es la forma abreviada de una clave pública.</span><span class="sxs-lookup"><span data-stu-id="7e334-116">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="7e334-117">El token es un hash de 64 bits que se crea a partir de la clave pública utilizada para firmar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7e334-117">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="7e334-118">El token es una parte del nombre seguro del ensamblado y se puede leer desde los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7e334-118">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="7e334-119">Una vez recuperada la clave y creado el token, debe llamar a la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="7e334-119">After the key is retrieved and the token is created, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="7e334-120">Si la `StrongNameTokenFromAssemblyEx` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="7e334-120">If the `StrongNameTokenFromAssemblyEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e334-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e334-121">Requirements</span></span>  

 <span data-ttu-id="7e334-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e334-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e334-123">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="7e334-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="7e334-124">**Biblioteca:** Se incluye como un recurso en mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7e334-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="7e334-125">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e334-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e334-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7e334-126">See also</span></span>

- [<span data-ttu-id="7e334-127">Método StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="7e334-127">StrongNameTokenFromAssemblyEx Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="7e334-128">Método StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="7e334-128">StrongNameTokenFromAssembly Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="7e334-129">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e334-129">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
