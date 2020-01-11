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
ms.openlocfilehash: 95098cbb060c06d2d5a5a4c04b6fa9017bca66a1
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899591"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="9f086-102">ICLRStrongName::StrongNameKeyDelete (Método)</span><span class="sxs-lookup"><span data-stu-id="9f086-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="9f086-103">Elimina el contenedor de claves especificado.</span><span class="sxs-lookup"><span data-stu-id="9f086-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f086-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f086-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f086-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="9f086-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="9f086-106">de Nombre del contenedor de claves que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="9f086-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f086-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9f086-107">Return Value</span></span>  
 <span data-ttu-id="9f086-108">`S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="9f086-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f086-109">Notas</span><span class="sxs-lookup"><span data-stu-id="9f086-109">Remarks</span></span>  
 <span data-ttu-id="9f086-110">Use el método [ICLRStrongName:: StrongNameKeyInstall (](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) para importar un par de claves pública y privada en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="9f086-110">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f086-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="9f086-111">Requirements</span></span>  
 <span data-ttu-id="9f086-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f086-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f086-113">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="9f086-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9f086-114">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9f086-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9f086-115">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f086-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f086-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f086-116">See also</span></span>

- [<span data-ttu-id="9f086-117">StrongNameKeyInstall (método)</span><span class="sxs-lookup"><span data-stu-id="9f086-117">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="9f086-118">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9f086-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
