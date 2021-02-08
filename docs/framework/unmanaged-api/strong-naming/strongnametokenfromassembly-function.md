---
description: 'Más información acerca de: StrongNameTokenFromAssembly ((función)'
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
ms.openlocfilehash: 3646d441da4885624c15d5e53670a8dd8db45160
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794486"
---
# <a name="strongnametokenfromassembly-function"></a><span data-ttu-id="dad11-103">StrongNameTokenFromAssembly (Función)</span><span class="sxs-lookup"><span data-stu-id="dad11-103">StrongNameTokenFromAssembly Function</span></span>

<span data-ttu-id="dad11-104">Crea un token de nombre seguro desde el archivo de ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="dad11-104">Creates a strong name token from the specified assembly file.</span></span>  
  
 <span data-ttu-id="dad11-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="dad11-105">This function has been deprecated.</span></span> <span data-ttu-id="dad11-106">Use el método [ICLRStrongName:: StrongNameTokenFromAssembly (](../hosting/iclrstrongname-strongnametokenfromassembly-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="dad11-106">Use the [ICLRStrongName::StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dad11-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dad11-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dad11-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dad11-108">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="dad11-109">de La ruta de acceso al archivo portable ejecutable (PE) para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dad11-109">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="dad11-110">enuncia El token de nombre seguro devuelto.</span><span class="sxs-lookup"><span data-stu-id="dad11-110">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="dad11-111">enuncia Tamaño, en bytes, del token de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="dad11-111">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dad11-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dad11-112">Return Value</span></span>  

 <span data-ttu-id="dad11-113">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="dad11-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dad11-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dad11-114">Remarks</span></span>  

 <span data-ttu-id="dad11-115">Un token de nombre seguro es la forma abreviada de una clave pública.</span><span class="sxs-lookup"><span data-stu-id="dad11-115">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="dad11-116">El token es un hash de 64 bits que se crea a partir de la clave pública utilizada para firmar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dad11-116">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="dad11-117">El token es una parte del nombre seguro del ensamblado y se puede leer desde los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dad11-117">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="dad11-118">Una vez creado el token, debe llamar a la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="dad11-118">After the token is created, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="dad11-119">Si la `StrongNameTokenFromAssembly` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="dad11-119">If the `StrongNameTokenFromAssembly` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dad11-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dad11-120">Requirements</span></span>  

 <span data-ttu-id="dad11-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dad11-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dad11-122">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="dad11-122">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="dad11-123">**Biblioteca:** Se incluye como un recurso en mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="dad11-123">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="dad11-124">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dad11-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dad11-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="dad11-125">See also</span></span>

- [<span data-ttu-id="dad11-126">Método StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="dad11-126">StrongNameTokenFromAssembly Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="dad11-127">Método StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="dad11-127">StrongNameTokenFromAssemblyEx Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="dad11-128">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dad11-128">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
