---
title: StrongNameTokenFromAssembly (Función)
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssembly
helpviewer_keywords:
- StrongNameTokenFromAssembly function [.NET Framework strong naming]
ms.assetid: 0a4b47ee-02f6-4a98-864e-a6f11ca3f2d9
topic_type:
- apiref
ms.openlocfilehash: 0feb180befd575dce20a83ddc89ebf13f87f3810
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728555"
---
# <a name="strongnametokenfromassembly-function"></a><span data-ttu-id="c5250-102">StrongNameTokenFromAssembly (Función)</span><span class="sxs-lookup"><span data-stu-id="c5250-102">StrongNameTokenFromAssembly Function</span></span>

<span data-ttu-id="c5250-103">Crea un token de nombre seguro desde el archivo de ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="c5250-103">Creates a strong name token from the specified assembly file.</span></span>  
  
 <span data-ttu-id="c5250-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="c5250-104">This function has been deprecated.</span></span> <span data-ttu-id="c5250-105">Use el método [ICLRStrongName:: StrongNameTokenFromAssembly (](../hosting/iclrstrongname-strongnametokenfromassembly-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="c5250-105">Use the [ICLRStrongName::StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5250-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5250-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5250-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c5250-107">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="c5250-108">de La ruta de acceso al archivo portable ejecutable (PE) para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c5250-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="c5250-109">enuncia El token de nombre seguro devuelto.</span><span class="sxs-lookup"><span data-stu-id="c5250-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="c5250-110">enuncia Tamaño, en bytes, del token de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="c5250-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5250-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c5250-111">Return Value</span></span>  

 <span data-ttu-id="c5250-112">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="c5250-112">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5250-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c5250-113">Remarks</span></span>  

 <span data-ttu-id="c5250-114">Un token de nombre seguro es la forma abreviada de una clave pública.</span><span class="sxs-lookup"><span data-stu-id="c5250-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="c5250-115">El token es un hash de 64 bits que se crea a partir de la clave pública utilizada para firmar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c5250-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="c5250-116">El token es una parte del nombre seguro del ensamblado y se puede leer desde los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c5250-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="c5250-117">Una vez creado el token, debe llamar a la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="c5250-117">After the token is created, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="c5250-118">Si la `StrongNameTokenFromAssembly` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="c5250-118">If the `StrongNameTokenFromAssembly` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5250-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5250-119">Requirements</span></span>  

 <span data-ttu-id="c5250-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5250-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5250-121">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="c5250-121">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c5250-122">**Biblioteca:** Se incluye como un recurso en mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c5250-122">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="c5250-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5250-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5250-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c5250-124">See also</span></span>

- [<span data-ttu-id="c5250-125">Método StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="c5250-125">StrongNameTokenFromAssembly Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="c5250-126">Método StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="c5250-126">StrongNameTokenFromAssemblyEx Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="c5250-127">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c5250-127">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
