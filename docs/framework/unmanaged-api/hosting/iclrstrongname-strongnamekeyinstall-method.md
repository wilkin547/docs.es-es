---
description: 'Más información sobre: ICLRStrongName:: StrongNameKeyInstall ((método)'
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
ms.openlocfilehash: 8f9e7bfebff555a6430a3970c8ee1c481e341f58
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799517"
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="a55f8-103">ICLRStrongName::StrongNameKeyInstall (Método)</span><span class="sxs-lookup"><span data-stu-id="a55f8-103">ICLRStrongName::StrongNameKeyInstall Method</span></span>

<span data-ttu-id="a55f8-104">Importa un par de claves pública y privada a un contenedor.</span><span class="sxs-lookup"><span data-stu-id="a55f8-104">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a55f8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a55f8-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a55f8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a55f8-106">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="a55f8-107">de Nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="a55f8-107">[in] The name of the key container.</span></span> <span data-ttu-id="a55f8-108">`wszKeyContainer` debe ser una cadena no vacía.</span><span class="sxs-lookup"><span data-stu-id="a55f8-108">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="a55f8-109">de Par de claves binarias.</span><span class="sxs-lookup"><span data-stu-id="a55f8-109">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="a55f8-110">de Tamaño, en bytes, de `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="a55f8-110">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a55f8-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a55f8-111">Return Value</span></span>  

 <span data-ttu-id="a55f8-112">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="a55f8-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a55f8-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a55f8-113">Remarks</span></span>  

 <span data-ttu-id="a55f8-114">Use el método [ICLRStrongName:: StrongNameKeyDelete (](iclrstrongname-strongnamekeydelete-method.md) para eliminar el contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="a55f8-114">Use the [ICLRStrongName::StrongNameKeyDelete](iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a55f8-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a55f8-115">Requirements</span></span>  

 <span data-ttu-id="a55f8-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a55f8-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a55f8-117">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="a55f8-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a55f8-118">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a55f8-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a55f8-119">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a55f8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a55f8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a55f8-120">See also</span></span>

- [<span data-ttu-id="a55f8-121">Método StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="a55f8-121">StrongNameKeyDelete Method</span></span>](iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="a55f8-122">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a55f8-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
