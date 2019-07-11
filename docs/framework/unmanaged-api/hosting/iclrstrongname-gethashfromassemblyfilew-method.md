---
title: ICLRStrongName::GetHashFromAssemblyFileW (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 371ed85f53109856d9c8f64e42aadca10302c269
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748211"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="4895b-102">ICLRStrongName::GetHashFromAssemblyFileW (Método)</span><span class="sxs-lookup"><span data-stu-id="4895b-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>
<span data-ttu-id="4895b-103">Genera un hash a partir del contenido del archivo especificado por una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="4895b-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4895b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4895b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4895b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4895b-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="4895b-106">[in] La ruta de acceso al archivo que se aplica un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="4895b-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="4895b-107">Este parámetro debe ser una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="4895b-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="4895b-108">[in, out] Una constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="4895b-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="4895b-109">Usar cero para el algoritmo hash predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4895b-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="4895b-110">[out] El búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="4895b-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="4895b-111">[in] El tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="4895b-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="4895b-112">[out] La ha devuelto el tamaño, en bytes, de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="4895b-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4895b-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4895b-113">Return Value</span></span>  
 <span data-ttu-id="4895b-114">`S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="4895b-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4895b-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4895b-115">Requirements</span></span>  
 <span data-ttu-id="4895b-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4895b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4895b-117">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="4895b-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4895b-118">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4895b-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4895b-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4895b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4895b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="4895b-120">See also</span></span>

- [<span data-ttu-id="4895b-121">GetHashFromAssemblyFile (método)</span><span class="sxs-lookup"><span data-stu-id="4895b-121">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="4895b-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4895b-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
