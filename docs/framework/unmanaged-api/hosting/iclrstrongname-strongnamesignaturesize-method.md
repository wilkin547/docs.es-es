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
ms.openlocfilehash: e789996af3aedd17251fc52cde52a336f65053ec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176349"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="a3e3f-102">ICLRStrongName::StrongNameSignatureSize (Método)</span><span class="sxs-lookup"><span data-stu-id="a3e3f-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="a3e3f-103">Devuelve el tamaño de la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="a3e3f-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="a3e3f-104">Este método se utiliza normalmente por los compiladores para determinar cuánto espacio se debe reservar en el archivo al crear un ensamblado firmado con retraso.</span><span class="sxs-lookup"><span data-stu-id="a3e3f-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3e3f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3e3f-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="a3e3f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a3e3f-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="a3e3f-107">[en] Estructura de tipo [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) que contiene la parte pública del par de claves utilizado para generar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="a3e3f-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="a3e3f-108">[en] El tamaño, en `pbPublicKeyBlob`bytes, de .</span><span class="sxs-lookup"><span data-stu-id="a3e3f-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="a3e3f-109">[en] El número de bytes necesarios para almacenar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="a3e3f-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3e3f-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a3e3f-110">Return Value</span></span>  
 <span data-ttu-id="a3e3f-111">`S_OK`si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (consulte [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="a3e3f-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3e3f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3e3f-112">Requirements</span></span>  
 <span data-ttu-id="a3e3f-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3e3f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3e3f-114">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a3e3f-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a3e3f-115">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a3e3f-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3e3f-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3e3f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3e3f-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3e3f-117">See also</span></span>

- [<span data-ttu-id="a3e3f-118">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3e3f-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
