---
title: ICLRStrongName::StrongNameKeyDelete (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyDelete method [.NET Framework hosting]
ms.assetid: 0163412f-f617-4428-89e0-03992fec31e8
topic_type:
- apiref
ms.openlocfilehash: 4e72818be6808c519677192d3744bbc5ec414d0d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135088"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="fabd8-102">ICLRStrongName::StrongNameKeyDelete (Método)</span><span class="sxs-lookup"><span data-stu-id="fabd8-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="fabd8-103">Elimina el contenedor de claves especificado.</span><span class="sxs-lookup"><span data-stu-id="fabd8-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fabd8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fabd8-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fabd8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fabd8-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="fabd8-106">de Nombre del contenedor de claves que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="fabd8-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fabd8-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fabd8-107">Return Value</span></span>  
 <span data-ttu-id="fabd8-108">`S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para una lista).</span><span class="sxs-lookup"><span data-stu-id="fabd8-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fabd8-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fabd8-109">Remarks</span></span>  
 <span data-ttu-id="fabd8-110">Use el método [ICLRStrongName:: StrongNameKeyInstall (](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) para importar un par de claves pública y privada en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="fabd8-110">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fabd8-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fabd8-111">Requirements</span></span>  
 <span data-ttu-id="fabd8-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fabd8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fabd8-113">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="fabd8-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fabd8-114">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fabd8-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fabd8-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fabd8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fabd8-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="fabd8-116">See also</span></span>

- [<span data-ttu-id="fabd8-117">StrongNameKeyInstall (método)</span><span class="sxs-lookup"><span data-stu-id="fabd8-117">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="fabd8-118">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fabd8-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
