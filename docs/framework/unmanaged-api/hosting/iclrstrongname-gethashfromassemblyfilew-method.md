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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984599"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="dd793-102">ICLRStrongName::GetHashFromAssemblyFileW (Método)</span><span class="sxs-lookup"><span data-stu-id="dd793-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>
<span data-ttu-id="dd793-103">Genera un hash a partir del contenido del archivo especificado por una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="dd793-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd793-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd793-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd793-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dd793-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="dd793-106">[in] La ruta de acceso al archivo que se aplica un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="dd793-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="dd793-107">Este parámetro debe ser una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="dd793-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="dd793-108">[in, out] Una constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="dd793-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="dd793-109">Usar cero para el algoritmo hash predeterminado.</span><span class="sxs-lookup"><span data-stu-id="dd793-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="dd793-110">[out] El búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="dd793-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="dd793-111">[in] El tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="dd793-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="dd793-112">[out] La ha devuelto el tamaño, en bytes, de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="dd793-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd793-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dd793-113">Return Value</span></span>  
 <span data-ttu-id="dd793-114">`S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="dd793-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd793-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd793-115">Requirements</span></span>  
 <span data-ttu-id="dd793-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd793-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd793-117">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="dd793-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="dd793-118">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dd793-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd793-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd793-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd793-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd793-120">See also</span></span>

- [<span data-ttu-id="dd793-121">GetHashFromAssemblyFile (método)</span><span class="sxs-lookup"><span data-stu-id="dd793-121">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="dd793-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd793-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
