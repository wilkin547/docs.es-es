---
title: GetHashFromAssemblyFile (Función)
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFile
helpviewer_keywords:
- GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e9c0abcd395caf09ebe11e060a4b922e78ad1e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457937"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="e94c9-102">GetHashFromAssemblyFile (Función)</span><span class="sxs-lookup"><span data-stu-id="e94c9-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="e94c9-103">Obtiene un valor hash del archivo de ensamblado especificado, utilizando el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="e94c9-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="e94c9-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="e94c9-104">This function has been deprecated.</span></span> <span data-ttu-id="e94c9-105">Use la [ICLRStrongName:: GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e94c9-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e94c9-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e94c9-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e94c9-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e94c9-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="e94c9-108">[in] La ruta de acceso al archivo que se aplica un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="e94c9-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="e94c9-109">[entrada, salida] Una constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="e94c9-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="e94c9-110">Utilice un cero para el algoritmo hash predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e94c9-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="e94c9-111">[out] El búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="e94c9-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="e94c9-112">[in] El tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="e94c9-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="e94c9-113">[out] La devuelve el tamaño, en bytes, de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="e94c9-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e94c9-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e94c9-114">Requirements</span></span>  
 <span data-ttu-id="e94c9-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e94c9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e94c9-116">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="e94c9-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e94c9-117">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e94c9-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e94c9-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e94c9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e94c9-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e94c9-119">See Also</span></span>  
 [<span data-ttu-id="e94c9-120">GetHashFromAssemblyFile (método)</span><span class="sxs-lookup"><span data-stu-id="e94c9-120">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [<span data-ttu-id="e94c9-121">GetHashFromAssemblyFileW (método)</span><span class="sxs-lookup"><span data-stu-id="e94c9-121">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="e94c9-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94c9-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
