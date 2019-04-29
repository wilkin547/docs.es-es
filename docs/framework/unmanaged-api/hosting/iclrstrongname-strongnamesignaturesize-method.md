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
ms.openlocfilehash: b0c81b51deb6affb3dd39677184ea0a4b2e6ff61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782582"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="96775-102">ICLRStrongName::StrongNameSignatureSize (Método)</span><span class="sxs-lookup"><span data-stu-id="96775-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="96775-103">Devuelve el tamaño de la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="96775-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="96775-104">Este método se utiliza normalmente los compiladores para determinar la cantidad de espacio que se reserva en el archivo al crear un ensamblado con firma retrasada.</span><span class="sxs-lookup"><span data-stu-id="96775-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96775-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96775-105">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="96775-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="96775-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="96775-107">[in] Una estructura de tipo [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) que contiene la parte pública del par de claves utilizado para generar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="96775-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="96775-108">[in] El tamaño, en bytes, de `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="96775-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="96775-109">[in] El número de bytes necesarios para almacenar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="96775-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96775-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="96775-110">Return Value</span></span>  
 <span data-ttu-id="96775-111">`S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="96775-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96775-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="96775-112">Requirements</span></span>  
 <span data-ttu-id="96775-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96775-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96775-114">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="96775-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="96775-115">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="96775-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96775-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96775-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96775-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="96775-117">See also</span></span>

- [<span data-ttu-id="96775-118">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="96775-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
