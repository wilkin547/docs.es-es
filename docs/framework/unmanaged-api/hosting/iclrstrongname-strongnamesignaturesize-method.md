---
title: ICLRStrongName::StrongNameSignatureSize (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureSize
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureSize method [.NET Framework hosting]
- StrongNameSignatureSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 76d4f93a-5e25-4399-abcc-a1389549481d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6641490908b1f384bf8192fd46b7dadb4ff5e23
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431947"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="3bee9-102">ICLRStrongName::StrongNameSignatureSize (Método)</span><span class="sxs-lookup"><span data-stu-id="3bee9-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="3bee9-103">Devuelve el tamaño de la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="3bee9-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="3bee9-104">Este método suele usarse por los compiladores para determinar la cantidad de espacio que se reserva en el archivo al crear un ensamblado con firma retrasada.</span><span class="sxs-lookup"><span data-stu-id="3bee9-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bee9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3bee9-105">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="3bee9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3bee9-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="3bee9-107">[in] Una estructura de tipo [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) que contiene la parte pública del par de claves utilizado para generar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="3bee9-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="3bee9-108">[in] El tamaño, en bytes, de `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="3bee9-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="3bee9-109">[in] El número de bytes necesarios para almacenar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="3bee9-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3bee9-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3bee9-110">Return Value</span></span>  
 <span data-ttu-id="3bee9-111">`S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (vea [valores HRESULT comunes](http://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="3bee9-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bee9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3bee9-112">Requirements</span></span>  
 <span data-ttu-id="3bee9-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bee9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bee9-114">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="3bee9-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3bee9-115">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3bee9-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3bee9-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bee9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bee9-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3bee9-117">See Also</span></span>  
 [<span data-ttu-id="3bee9-118">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3bee9-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
