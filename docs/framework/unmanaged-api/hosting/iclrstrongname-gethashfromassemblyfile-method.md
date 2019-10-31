---
title: ICLRStrongName::GetHashFromAssemblyFile (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type:
- apiref
ms.openlocfilehash: 3fd9efd3961be1d6e6e91b881327628c598e364e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092722"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="cd543-102">ICLRStrongName::GetHashFromAssemblyFile (Método)</span><span class="sxs-lookup"><span data-stu-id="cd543-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="cd543-103">Obtiene un hash del archivo de ensamblado especificado mediante un algoritmo hash concreto.</span><span class="sxs-lookup"><span data-stu-id="cd543-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd543-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd543-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd543-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cd543-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="cd543-106">de Ruta de acceso al archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="cd543-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="cd543-107">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="cd543-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="cd543-108">Use cero para el algoritmo hash predeterminado.</span><span class="sxs-lookup"><span data-stu-id="cd543-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="cd543-109">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="cd543-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="cd543-110">de Tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="cd543-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="cd543-111">enuncia El tamaño devuelto, en bytes, de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="cd543-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd543-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cd543-112">Return Value</span></span>  
 <span data-ttu-id="cd543-113">`S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para una lista).</span><span class="sxs-lookup"><span data-stu-id="cd543-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd543-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd543-114">Requirements</span></span>  
 <span data-ttu-id="cd543-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd543-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd543-116">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="cd543-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="cd543-117">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cd543-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd543-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd543-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd543-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd543-119">See also</span></span>

- [<span data-ttu-id="cd543-120">GetHashFromAssemblyFileW (método)</span><span class="sxs-lookup"><span data-stu-id="cd543-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="cd543-121">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd543-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
