---
title: GetHashFromAssemblyFileW (Función)
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFileW
helpviewer_keywords:
- GetHashFromAssemblyFileW function [.NET Framework strong naming]
ms.assetid: d1b2b172-5353-42af-a877-cf653c68ece0
topic_type:
- apiref
ms.openlocfilehash: b895c77850c0457fd2a152c1128c016093599f76
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730986"
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="f2654-102">GetHashFromAssemblyFileW (Función)</span><span class="sxs-lookup"><span data-stu-id="f2654-102">GetHashFromAssemblyFileW Function</span></span>

<span data-ttu-id="f2654-103">Obtiene un hash del archivo de ensamblado especificado mediante un algoritmo hash concreto.</span><span class="sxs-lookup"><span data-stu-id="f2654-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="f2654-104">La ruta de acceso al archivo de ensamblado debe especificarse como una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="f2654-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="f2654-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="f2654-105">This function has been deprecated.</span></span> <span data-ttu-id="f2654-106">Use el método [ICLRStrongName:: gethashfromassemblyfilew (](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="f2654-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2654-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2654-107">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2654-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f2654-108">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="f2654-109">de Ruta de acceso al archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="f2654-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="f2654-110">Este parámetro debe ser una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="f2654-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="f2654-111">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="f2654-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="f2654-112">Use cero para el algoritmo hash predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f2654-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="f2654-113">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="f2654-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="f2654-114">de Tamaño máximo solicitado de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="f2654-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="f2654-115">enuncia El tamaño devuelto, en bytes, de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="f2654-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2654-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2654-116">Requirements</span></span>  

 <span data-ttu-id="f2654-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2654-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2654-118">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="f2654-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="f2654-119">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f2654-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f2654-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2654-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2654-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f2654-121">See also</span></span>

- [<span data-ttu-id="f2654-122">Método GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="f2654-122">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="f2654-123">Método GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="f2654-123">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="f2654-124">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2654-124">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
