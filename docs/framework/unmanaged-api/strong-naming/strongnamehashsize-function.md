---
title: StrongNameHashSize (Función)
ms.date: 03/30/2017
api_name:
- StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameHashSize
helpviewer_keywords:
- StrongNameHashSize function [.NET Framework strong naming]
ms.assetid: 738c98d7-a60c-45fe-a296-220af05e6991
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92b9d9b5baee856f09dd24a62767aff604728997
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454087"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="de3e9-102">StrongNameHashSize (Función)</span><span class="sxs-lookup"><span data-stu-id="de3e9-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="de3e9-103">Obtiene el tamaño de búfer requerido para un hash mediante el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="de3e9-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="de3e9-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="de3e9-104">This function has been deprecated.</span></span> <span data-ttu-id="de3e9-105">Use la [ICLRStrongName:: StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="de3e9-105">Use the [ICLRStrongName::StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de3e9-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de3e9-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de3e9-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="de3e9-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="de3e9-108">[in] El algoritmo hash que se utiliza para calcular el tamaño del búfer.</span><span class="sxs-lookup"><span data-stu-id="de3e9-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="de3e9-109">[out] El tamaño de búfer devuelto, en bytes.</span><span class="sxs-lookup"><span data-stu-id="de3e9-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de3e9-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="de3e9-110">Return Value</span></span>  
 <span data-ttu-id="de3e9-111">`true` Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="de3e9-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de3e9-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de3e9-112">Remarks</span></span>  
 <span data-ttu-id="de3e9-113">Si el `StrongNameHashSize` función no se completan correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="de3e9-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de3e9-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de3e9-114">Requirements</span></span>  
 <span data-ttu-id="de3e9-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de3e9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de3e9-116">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="de3e9-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="de3e9-117">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="de3e9-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="de3e9-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de3e9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de3e9-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="de3e9-119">See Also</span></span>  
 [<span data-ttu-id="de3e9-120">StrongNameHashSize (método)</span><span class="sxs-lookup"><span data-stu-id="de3e9-120">StrongNameHashSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)  
 [<span data-ttu-id="de3e9-121">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="de3e9-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
