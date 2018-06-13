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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5f04d71e1709eed6c3a9f1af400f79b4722f4433
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457706"
---
# <a name="strongnametokenfromassembly-function"></a><span data-ttu-id="56f7e-102">StrongNameTokenFromAssembly (Función)</span><span class="sxs-lookup"><span data-stu-id="56f7e-102">StrongNameTokenFromAssembly Function</span></span>
<span data-ttu-id="56f7e-103">Crea un token de nombre seguro del archivo de ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="56f7e-103">Creates a strong name token from the specified assembly file.</span></span>  
  
 <span data-ttu-id="56f7e-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="56f7e-104">This function has been deprecated.</span></span> <span data-ttu-id="56f7e-105">Use la [ICLRStrongName:: StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="56f7e-105">Use the [ICLRStrongName::StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56f7e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56f7e-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="56f7e-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="56f7e-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="56f7e-108">[in] La ruta de acceso al archivo ejecutable portable (PE) para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="56f7e-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="56f7e-109">[out] El token de nombre seguro devuelto.</span><span class="sxs-lookup"><span data-stu-id="56f7e-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="56f7e-110">[out] El tamaño, en bytes, del token de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="56f7e-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56f7e-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="56f7e-111">Return Value</span></span>  
 <span data-ttu-id="56f7e-112">`true` Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="56f7e-112">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56f7e-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="56f7e-113">Remarks</span></span>  
 <span data-ttu-id="56f7e-114">Un token de nombre seguro es la forma abreviada de una clave pública.</span><span class="sxs-lookup"><span data-stu-id="56f7e-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="56f7e-115">El token es un hash de 64 bits que se crea a partir de la clave pública utilizada para firmar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="56f7e-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="56f7e-116">El token forma parte del nombre seguro del ensamblado y se puede leer desde los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="56f7e-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="56f7e-117">Una vez creado el token, debe llamar a la [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) función para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="56f7e-117">After the token is created, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="56f7e-118">Si el `StrongNameTokenFromAssembly` función no se completan correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="56f7e-118">If the `StrongNameTokenFromAssembly` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56f7e-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="56f7e-119">Requirements</span></span>  
 <span data-ttu-id="56f7e-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56f7e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56f7e-121">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="56f7e-121">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="56f7e-122">**Biblioteca:** incluye como recurso en mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="56f7e-122">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="56f7e-123">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56f7e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56f7e-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="56f7e-124">See Also</span></span>  
 [<span data-ttu-id="56f7e-125">StrongNameTokenFromAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="56f7e-125">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)  
 [<span data-ttu-id="56f7e-126">StrongNameTokenFromAssemblyEx (método)</span><span class="sxs-lookup"><span data-stu-id="56f7e-126">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)  
 [<span data-ttu-id="56f7e-127">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="56f7e-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
