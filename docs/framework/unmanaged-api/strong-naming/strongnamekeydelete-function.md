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
ms.openlocfilehash: 3eace88e5034c61b7608a6d777608cc2544b8564
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688485"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="735a6-102">StrongNameKeyDelete (Función)</span><span class="sxs-lookup"><span data-stu-id="735a6-102">StrongNameKeyDelete Function</span></span>
<span data-ttu-id="735a6-103">Elimina el contenedor de claves especificado.</span><span class="sxs-lookup"><span data-stu-id="735a6-103">Deletes the specified key container.</span></span>  
  
 <span data-ttu-id="735a6-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="735a6-104">This function has been deprecated.</span></span> <span data-ttu-id="735a6-105">Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="735a6-105">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="735a6-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="735a6-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="735a6-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="735a6-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="735a6-108">[in] Nombre del contenedor de claves para eliminar.</span><span class="sxs-lookup"><span data-stu-id="735a6-108">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="735a6-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="735a6-109">Return Value</span></span>  
 <span data-ttu-id="735a6-110">`true` Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="735a6-110">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="735a6-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="735a6-111">Remarks</span></span>  
 <span data-ttu-id="735a6-112">Use la [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) función para importar un par de claves pública y privada en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="735a6-112">Use the [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) function to importa a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="735a6-113">Si el `StrongNameKeyDelete` función no se completa correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="735a6-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="735a6-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="735a6-114">Requirements</span></span>  
 <span data-ttu-id="735a6-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="735a6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="735a6-116">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="735a6-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="735a6-117">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="735a6-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="735a6-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="735a6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="735a6-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="735a6-119">See also</span></span>
- [<span data-ttu-id="735a6-120">StrongNameKeyDelete (método)</span><span class="sxs-lookup"><span data-stu-id="735a6-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="735a6-121">StrongNameKeyInstall (método)</span><span class="sxs-lookup"><span data-stu-id="735a6-121">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="735a6-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="735a6-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
