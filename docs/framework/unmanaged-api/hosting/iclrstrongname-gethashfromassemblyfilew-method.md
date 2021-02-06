---
description: 'Más información sobre: ICLRStrongName:: Gethashfromassemblyfilew ((método)'
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
ms.openlocfilehash: 27123ed8217d49765fe3fd7c19efc92f4e770722
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637084"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="5f599-103">ICLRStrongName::GetHashFromAssemblyFileW (Método)</span><span class="sxs-lookup"><span data-stu-id="5f599-103">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>

<span data-ttu-id="5f599-104">Genera un hash a partir del contenido del archivo especificado por una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="5f599-104">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f599-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f599-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f599-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5f599-106">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="5f599-107">de Ruta de acceso al archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="5f599-107">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="5f599-108">Este parámetro debe ser una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="5f599-108">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="5f599-109">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="5f599-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="5f599-110">Use cero para el algoritmo hash predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5f599-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="5f599-111">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="5f599-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="5f599-112">de Tamaño máximo solicitado de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="5f599-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="5f599-113">enuncia El tamaño devuelto, en bytes, de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="5f599-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f599-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5f599-114">Return Value</span></span>  

 <span data-ttu-id="5f599-115">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="5f599-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f599-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f599-116">Requirements</span></span>  

 <span data-ttu-id="5f599-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f599-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f599-118">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="5f599-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5f599-119">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5f599-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f599-120">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f599-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f599-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f599-121">See also</span></span>

- [<span data-ttu-id="5f599-122">Método GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="5f599-122">GetHashFromAssemblyFile Method</span></span>](iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="5f599-123">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f599-123">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
