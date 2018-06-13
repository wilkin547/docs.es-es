---
title: StrongNameKeyDelete (Función)
ms.date: 03/30/2017
api_name:
- StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a35ec4e3c3110616ac20cd31db134371838deda0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461934"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="42e91-102">StrongNameKeyDelete (Función)</span><span class="sxs-lookup"><span data-stu-id="42e91-102">StrongNameKeyDelete Function</span></span>
<span data-ttu-id="42e91-103">Elimina el contenedor de claves especificado.</span><span class="sxs-lookup"><span data-stu-id="42e91-103">Deletes the specified key container.</span></span>  
  
 <span data-ttu-id="42e91-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="42e91-104">This function has been deprecated.</span></span> <span data-ttu-id="42e91-105">Use la [ICLRStrongName:: StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="42e91-105">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42e91-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42e91-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42e91-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="42e91-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="42e91-108">[in] Nombre del contenedor de claves para eliminar.</span><span class="sxs-lookup"><span data-stu-id="42e91-108">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42e91-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="42e91-109">Return Value</span></span>  
 <span data-ttu-id="42e91-110">`true` Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="42e91-110">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42e91-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="42e91-111">Remarks</span></span>  
 <span data-ttu-id="42e91-112">Use la [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) función para importar un par de claves pública/privada en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="42e91-112">Use the [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) function to importa a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="42e91-113">Si el `StrongNameKeyDelete` función no se completan correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="42e91-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42e91-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42e91-114">Requirements</span></span>  
 <span data-ttu-id="42e91-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42e91-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42e91-116">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="42e91-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="42e91-117">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="42e91-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="42e91-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42e91-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42e91-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="42e91-119">See Also</span></span>  
 [<span data-ttu-id="42e91-120">StrongNameKeyDelete (método)</span><span class="sxs-lookup"><span data-stu-id="42e91-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="42e91-121">StrongNameKeyInstall (método)</span><span class="sxs-lookup"><span data-stu-id="42e91-121">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="42e91-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="42e91-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
