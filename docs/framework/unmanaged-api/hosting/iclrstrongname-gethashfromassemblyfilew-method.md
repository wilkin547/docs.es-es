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
ms.openlocfilehash: e94bfe6151ed42886355423a838f21e13748ec61
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685778"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="ab50e-102">ICLRStrongName::GetHashFromAssemblyFileW (Método)</span><span class="sxs-lookup"><span data-stu-id="ab50e-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>

<span data-ttu-id="ab50e-103">Genera un hash a partir del contenido del archivo especificado por una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="ab50e-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab50e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab50e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab50e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab50e-105">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="ab50e-106">de Ruta de acceso al archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="ab50e-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="ab50e-107">Este parámetro debe ser una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="ab50e-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="ab50e-108">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="ab50e-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="ab50e-109">Use cero para el algoritmo hash predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ab50e-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="ab50e-110">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="ab50e-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="ab50e-111">de Tamaño máximo solicitado de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="ab50e-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="ab50e-112">enuncia El tamaño devuelto, en bytes, de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="ab50e-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab50e-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ab50e-113">Return Value</span></span>  

 <span data-ttu-id="ab50e-114">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="ab50e-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab50e-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ab50e-115">Requirements</span></span>  

 <span data-ttu-id="ab50e-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab50e-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab50e-117">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="ab50e-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ab50e-118">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ab50e-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab50e-119">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab50e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab50e-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ab50e-120">See also</span></span>

- [<span data-ttu-id="ab50e-121">Método GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="ab50e-121">GetHashFromAssemblyFile Method</span></span>](iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="ab50e-122">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ab50e-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
