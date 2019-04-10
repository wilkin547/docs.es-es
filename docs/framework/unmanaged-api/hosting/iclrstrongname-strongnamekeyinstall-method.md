---
title: ICLRStrongName::StrongNameKeyInstall (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyInstall
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyInstall method [.NET Framework hosting]
- StrongNameKeyInstall method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5c15cf3b-164c-49d1-8e57-e42949d55acf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 415df9928572e095c529119bf2e726fa383577b0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224954"
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="6169f-102">ICLRStrongName::StrongNameKeyInstall (Método)</span><span class="sxs-lookup"><span data-stu-id="6169f-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>
<span data-ttu-id="6169f-103">Importa un par de claves pública y privada a un contenedor.</span><span class="sxs-lookup"><span data-stu-id="6169f-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6169f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6169f-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6169f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6169f-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="6169f-106">[in] Nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="6169f-106">[in] The name of the key container.</span></span> `wszKeyContainer` <span data-ttu-id="6169f-107">debe ser una cadena no vacía.</span><span class="sxs-lookup"><span data-stu-id="6169f-107">must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="6169f-108">[in] El par de claves binario.</span><span class="sxs-lookup"><span data-stu-id="6169f-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="6169f-109">[in] El tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="6169f-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6169f-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6169f-110">Return Value</span></span>  
 `S_OK` <span data-ttu-id="6169f-111">Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="6169f-111">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6169f-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6169f-112">Remarks</span></span>  
 <span data-ttu-id="6169f-113">Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) método para eliminar el contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="6169f-113">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6169f-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6169f-114">Requirements</span></span>  
 <span data-ttu-id="6169f-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6169f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6169f-116">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6169f-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6169f-117">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6169f-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="6169f-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6169f-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6169f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="6169f-119">See also</span></span>

- [<span data-ttu-id="6169f-120">Método StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="6169f-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="6169f-121">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6169f-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
