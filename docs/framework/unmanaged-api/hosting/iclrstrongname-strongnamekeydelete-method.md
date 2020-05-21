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
ms.openlocfilehash: 8f6f2445d88d608d51be4e6fe1e064efbb58325d
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763103"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="d52f7-102">ICLRStrongName::StrongNameKeyDelete (Método)</span><span class="sxs-lookup"><span data-stu-id="d52f7-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="d52f7-103">Elimina el contenedor de claves especificado.</span><span class="sxs-lookup"><span data-stu-id="d52f7-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d52f7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d52f7-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d52f7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d52f7-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="d52f7-106">de Nombre del contenedor de claves que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="d52f7-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d52f7-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d52f7-107">Return Value</span></span>  
 <span data-ttu-id="d52f7-108">`S_OK`Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="d52f7-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d52f7-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d52f7-109">Remarks</span></span>  
 <span data-ttu-id="d52f7-110">Use el método [ICLRStrongName:: StrongNameKeyInstall (](iclrstrongname-strongnamekeyinstall-method.md) para importar un par de claves pública y privada en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="d52f7-110">Use the [ICLRStrongName::StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d52f7-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d52f7-111">Requirements</span></span>  
 <span data-ttu-id="d52f7-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d52f7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d52f7-113">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="d52f7-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d52f7-114">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d52f7-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d52f7-115">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d52f7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d52f7-116">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="d52f7-116">See also</span></span>

- [<span data-ttu-id="d52f7-117">Método StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="d52f7-117">StrongNameKeyInstall Method</span></span>](iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="d52f7-118">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d52f7-118">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
