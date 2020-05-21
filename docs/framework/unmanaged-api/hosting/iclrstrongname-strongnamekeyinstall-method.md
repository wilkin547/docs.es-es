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
ms.openlocfilehash: e0c60d6e74c48531a223f6dbb35125b5a2017cbb
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763051"
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="42ce8-102">ICLRStrongName::StrongNameKeyInstall (Método)</span><span class="sxs-lookup"><span data-stu-id="42ce8-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>
<span data-ttu-id="42ce8-103">Importa un par de claves pública y privada a un contenedor.</span><span class="sxs-lookup"><span data-stu-id="42ce8-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42ce8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42ce8-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42ce8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="42ce8-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="42ce8-106">de Nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="42ce8-106">[in] The name of the key container.</span></span> <span data-ttu-id="42ce8-107">`wszKeyContainer`debe ser una cadena no vacía.</span><span class="sxs-lookup"><span data-stu-id="42ce8-107">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="42ce8-108">de Par de claves binarias.</span><span class="sxs-lookup"><span data-stu-id="42ce8-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="42ce8-109">de Tamaño, en bytes, de `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="42ce8-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42ce8-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="42ce8-110">Return Value</span></span>  
 <span data-ttu-id="42ce8-111">`S_OK`Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="42ce8-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42ce8-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="42ce8-112">Remarks</span></span>  
 <span data-ttu-id="42ce8-113">Use el método [ICLRStrongName:: StrongNameKeyDelete (](iclrstrongname-strongnamekeydelete-method.md) para eliminar el contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="42ce8-113">Use the [ICLRStrongName::StrongNameKeyDelete](iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42ce8-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42ce8-114">Requirements</span></span>  
 <span data-ttu-id="42ce8-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42ce8-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42ce8-116">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="42ce8-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="42ce8-117">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="42ce8-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42ce8-118">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42ce8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42ce8-119">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="42ce8-119">See also</span></span>

- [<span data-ttu-id="42ce8-120">Método StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="42ce8-120">StrongNameKeyDelete Method</span></span>](iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="42ce8-121">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="42ce8-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
