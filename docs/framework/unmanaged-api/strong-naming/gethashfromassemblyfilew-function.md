---
title: "GetHashFromAssemblyFileW (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromAssemblyFileW
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromAssemblyFileW
helpviewer_keywords: GetHashFromAssemblyFileW function [.NET Framework strong naming]
ms.assetid: d1b2b172-5353-42af-a877-cf653c68ece0
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aa88de90f831e1faaca2624a77a556d6a2b566c2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="167cf-102">GetHashFromAssemblyFileW (Función)</span><span class="sxs-lookup"><span data-stu-id="167cf-102">GetHashFromAssemblyFileW Function</span></span>
<span data-ttu-id="167cf-103">Obtiene un valor hash del archivo de ensamblado especificado, utilizando el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="167cf-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="167cf-104">La ruta de acceso al archivo de ensamblado debe especificarse como una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="167cf-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="167cf-105">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="167cf-105">This function has been deprecated.</span></span> <span data-ttu-id="167cf-106">Use la [ICLRStrongName:: GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="167cf-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="167cf-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="167cf-107">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="167cf-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="167cf-108">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="167cf-109">[in] La ruta de acceso al archivo que se aplica un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="167cf-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="167cf-110">Este parámetro debe ser una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="167cf-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="167cf-111">[entrada, salida] Una constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="167cf-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="167cf-112">Utilice un cero para el algoritmo hash predeterminado.</span><span class="sxs-lookup"><span data-stu-id="167cf-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="167cf-113">[out] El búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="167cf-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="167cf-114">[in] El tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="167cf-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="167cf-115">[out] La devuelve el tamaño, en bytes, de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="167cf-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="167cf-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="167cf-116">Requirements</span></span>  
 <span data-ttu-id="167cf-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="167cf-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="167cf-118">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="167cf-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="167cf-119">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="167cf-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="167cf-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="167cf-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="167cf-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="167cf-121">See Also</span></span>  
 [<span data-ttu-id="167cf-122">GetHashFromAssemblyFileW (método)</span><span class="sxs-lookup"><span data-stu-id="167cf-122">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="167cf-123">GetHashFromAssemblyFile (método)</span><span class="sxs-lookup"><span data-stu-id="167cf-123">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [<span data-ttu-id="167cf-124">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="167cf-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
