---
description: 'Más información sobre: ICLRStrongName:: Gethashfromassemblyfile ((método)'
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
ms.openlocfilehash: 40a8e2aabe9ade00243c535d63389f4265cc6ab0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799709"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="d74a1-103">ICLRStrongName::GetHashFromAssemblyFile (Método)</span><span class="sxs-lookup"><span data-stu-id="d74a1-103">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>

<span data-ttu-id="d74a1-104">Obtiene un hash del archivo de ensamblado especificado mediante un algoritmo hash concreto.</span><span class="sxs-lookup"><span data-stu-id="d74a1-104">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d74a1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d74a1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d74a1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d74a1-106">Parameters</span></span>  

 `szFilePath`  
 <span data-ttu-id="d74a1-107">de Ruta de acceso al archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="d74a1-107">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="d74a1-108">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="d74a1-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="d74a1-109">Use cero para el algoritmo hash predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d74a1-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="d74a1-110">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="d74a1-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="d74a1-111">de Tamaño máximo solicitado de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="d74a1-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="d74a1-112">enuncia El tamaño devuelto, en bytes, de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="d74a1-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d74a1-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d74a1-113">Return Value</span></span>  

 <span data-ttu-id="d74a1-114">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="d74a1-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d74a1-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d74a1-115">Requirements</span></span>  

 <span data-ttu-id="d74a1-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d74a1-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d74a1-117">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="d74a1-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d74a1-118">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d74a1-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d74a1-119">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d74a1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d74a1-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d74a1-120">See also</span></span>

- [<span data-ttu-id="d74a1-121">Método GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="d74a1-121">GetHashFromAssemblyFileW Method</span></span>](iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="d74a1-122">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d74a1-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
