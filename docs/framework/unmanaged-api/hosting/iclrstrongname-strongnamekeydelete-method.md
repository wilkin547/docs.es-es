---
description: 'Más información sobre: ICLRStrongName:: StrongNameKeyDelete ((método)'
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
ms.openlocfilehash: 5b782785921eb24394db53d29a66600a3867b489
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799582"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="fa681-103">ICLRStrongName::StrongNameKeyDelete (Método)</span><span class="sxs-lookup"><span data-stu-id="fa681-103">ICLRStrongName::StrongNameKeyDelete Method</span></span>

<span data-ttu-id="fa681-104">Elimina el contenedor de claves especificado.</span><span class="sxs-lookup"><span data-stu-id="fa681-104">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa681-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa681-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa681-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fa681-106">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="fa681-107">de Nombre del contenedor de claves que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="fa681-107">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa681-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fa681-108">Return Value</span></span>  

 <span data-ttu-id="fa681-109">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="fa681-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa681-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fa681-110">Remarks</span></span>  

 <span data-ttu-id="fa681-111">Use el método [ICLRStrongName:: StrongNameKeyInstall (](iclrstrongname-strongnamekeyinstall-method.md) para importar un par de claves pública y privada en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="fa681-111">Use the [ICLRStrongName::StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa681-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa681-112">Requirements</span></span>  

 <span data-ttu-id="fa681-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa681-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa681-114">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="fa681-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fa681-115">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fa681-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa681-116">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa681-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa681-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa681-117">See also</span></span>

- [<span data-ttu-id="fa681-118">Método StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="fa681-118">StrongNameKeyInstall Method</span></span>](iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="fa681-119">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa681-119">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
