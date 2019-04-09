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
ms.openlocfilehash: 578dd7941ad7a2cf1d39a3aeed7fa823eb7efa79
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162171"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="a2055-102">ICLRStrongName::GetHashFromAssemblyFileW (Método)</span><span class="sxs-lookup"><span data-stu-id="a2055-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>
<span data-ttu-id="a2055-103">Genera un hash a partir del contenido del archivo especificado por una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="a2055-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2055-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a2055-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2055-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a2055-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="a2055-106">[in] La ruta de acceso al archivo que se aplica un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="a2055-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="a2055-107">Este parámetro debe ser una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="a2055-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="a2055-108">[in, out] Una constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="a2055-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="a2055-109">Usar cero para el algoritmo hash predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a2055-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="a2055-110">[out] El búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="a2055-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="a2055-111">[in] El tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="a2055-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="a2055-112">[out] La ha devuelto el tamaño, en bytes, de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="a2055-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a2055-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a2055-113">Return Value</span></span>  
 `S_OK` <span data-ttu-id="a2055-114">Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="a2055-114">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2055-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a2055-115">Requirements</span></span>  
 <span data-ttu-id="a2055-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2055-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2055-117">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a2055-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a2055-118">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a2055-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a2055-119">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a2055-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a2055-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2055-120">See also</span></span>

- [<span data-ttu-id="a2055-121">Método GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="a2055-121">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="a2055-122">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a2055-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
