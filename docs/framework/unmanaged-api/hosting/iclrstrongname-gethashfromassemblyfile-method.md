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
ms.openlocfilehash: 0a15a4d237f63da54615ee1801e6cd39620e8274
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727866"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="2df2f-102">ICLRStrongName::GetHashFromAssemblyFile (Método)</span><span class="sxs-lookup"><span data-stu-id="2df2f-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>

<span data-ttu-id="2df2f-103">Obtiene un hash del archivo de ensamblado especificado mediante un algoritmo hash concreto.</span><span class="sxs-lookup"><span data-stu-id="2df2f-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2df2f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2df2f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2df2f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2df2f-105">Parameters</span></span>  

 `szFilePath`  
 <span data-ttu-id="2df2f-106">de Ruta de acceso al archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="2df2f-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="2df2f-107">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="2df2f-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="2df2f-108">Use cero para el algoritmo hash predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2df2f-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="2df2f-109">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="2df2f-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="2df2f-110">de Tamaño máximo solicitado de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="2df2f-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="2df2f-111">enuncia El tamaño devuelto, en bytes, de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="2df2f-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2df2f-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2df2f-112">Return Value</span></span>  

 <span data-ttu-id="2df2f-113">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="2df2f-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2df2f-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2df2f-114">Requirements</span></span>  

 <span data-ttu-id="2df2f-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2df2f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2df2f-116">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="2df2f-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2df2f-117">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2df2f-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2df2f-118">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2df2f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2df2f-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2df2f-119">See also</span></span>

- [<span data-ttu-id="2df2f-120">Método GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="2df2f-120">GetHashFromAssemblyFileW Method</span></span>](iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="2df2f-121">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2df2f-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
