---
description: 'Más información acerca de: Gethashfromassemblyfile ((función)'
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
ms.openlocfilehash: 79cc6289ebcf33f5a9ea8b4ef139c4b2a67e55e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736783"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="106f7-103">GetHashFromAssemblyFile (Función)</span><span class="sxs-lookup"><span data-stu-id="106f7-103">GetHashFromAssemblyFile Function</span></span>

<span data-ttu-id="106f7-104">Obtiene un hash del archivo de ensamblado especificado mediante un algoritmo hash concreto.</span><span class="sxs-lookup"><span data-stu-id="106f7-104">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="106f7-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="106f7-105">This function has been deprecated.</span></span> <span data-ttu-id="106f7-106">Use el método [ICLRStrongName:: gethashfromassemblyfile (](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="106f7-106">Use the [ICLRStrongName::GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="106f7-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="106f7-107">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="106f7-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="106f7-108">Parameters</span></span>  

 `szFilePath`  
 <span data-ttu-id="106f7-109">de Ruta de acceso al archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="106f7-109">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="106f7-110">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="106f7-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="106f7-111">Use cero para el algoritmo hash predeterminado.</span><span class="sxs-lookup"><span data-stu-id="106f7-111">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="106f7-112">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="106f7-112">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="106f7-113">de Tamaño máximo solicitado de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="106f7-113">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="106f7-114">enuncia El tamaño devuelto, en bytes, de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="106f7-114">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="106f7-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="106f7-115">Requirements</span></span>  

 <span data-ttu-id="106f7-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="106f7-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="106f7-117">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="106f7-117">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="106f7-118">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="106f7-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="106f7-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="106f7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="106f7-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="106f7-120">See also</span></span>

- [<span data-ttu-id="106f7-121">Método GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="106f7-121">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="106f7-122">Método GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="106f7-122">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="106f7-123">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="106f7-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
