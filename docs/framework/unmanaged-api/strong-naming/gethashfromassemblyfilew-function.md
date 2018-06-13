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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 832d66eee14680870e70f1e0e8d40987eff3257f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457579"
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="bb9b9-102">GetHashFromAssemblyFileW (Función)</span><span class="sxs-lookup"><span data-stu-id="bb9b9-102">GetHashFromAssemblyFileW Function</span></span>
<span data-ttu-id="bb9b9-103">Obtiene un valor hash del archivo de ensamblado especificado, utilizando el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="bb9b9-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="bb9b9-104">La ruta de acceso al archivo de ensamblado debe especificarse como una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="bb9b9-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="bb9b9-105">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="bb9b9-105">This function has been deprecated.</span></span> <span data-ttu-id="bb9b9-106">Use la [ICLRStrongName:: GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="bb9b9-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb9b9-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb9b9-107">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb9b9-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bb9b9-108">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="bb9b9-109">[in] La ruta de acceso al archivo que se aplica un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="bb9b9-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="bb9b9-110">Este parámetro debe ser una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="bb9b9-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="bb9b9-111">[entrada, salida] Una constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="bb9b9-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="bb9b9-112">Utilice un cero para el algoritmo hash predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bb9b9-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="bb9b9-113">[out] El búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="bb9b9-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="bb9b9-114">[in] El tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="bb9b9-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="bb9b9-115">[out] La devuelve el tamaño, en bytes, de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="bb9b9-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb9b9-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb9b9-116">Requirements</span></span>  
 <span data-ttu-id="bb9b9-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb9b9-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb9b9-118">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="bb9b9-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="bb9b9-119">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bb9b9-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bb9b9-120">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb9b9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb9b9-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb9b9-121">See Also</span></span>  
 [<span data-ttu-id="bb9b9-122">GetHashFromAssemblyFileW (método)</span><span class="sxs-lookup"><span data-stu-id="bb9b9-122">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="bb9b9-123">GetHashFromAssemblyFile (método)</span><span class="sxs-lookup"><span data-stu-id="bb9b9-123">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [<span data-ttu-id="bb9b9-124">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb9b9-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
