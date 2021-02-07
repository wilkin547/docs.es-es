---
description: 'Más información acerca de: Gethashfromhandle ((función)'
title: GetHashFromHandle (Función)
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
ms.openlocfilehash: 5951a5befd9e66b13a3b3033398614fca1f1a9d8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736575"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="30c23-103">GetHashFromHandle (Función)</span><span class="sxs-lookup"><span data-stu-id="30c23-103">GetHashFromHandle Function</span></span>

<span data-ttu-id="30c23-104">Genera un hash a partir del contenido del archivo con el identificador de archivos especificado mediante un algoritmo hash concreto.</span><span class="sxs-lookup"><span data-stu-id="30c23-104">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="30c23-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="30c23-105">This function has been deprecated.</span></span> <span data-ttu-id="30c23-106">Use el método [ICLRStrongName:: gethashfromhandle (](../hosting/iclrstrongname-gethashfromhandle-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="30c23-106">Use the [ICLRStrongName::GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30c23-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30c23-107">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30c23-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="30c23-108">Parameters</span></span>  

 `hFile`  
 <span data-ttu-id="30c23-109">de Identificador del archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="30c23-109">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="30c23-110">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="30c23-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="30c23-111">Use cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="30c23-111">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="30c23-112">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="30c23-112">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="30c23-113">de Tamaño máximo solicitado de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="30c23-113">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="30c23-114">enuncia Tamaño, en bytes, del devuelto `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="30c23-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30c23-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30c23-115">Requirements</span></span>  

 <span data-ttu-id="30c23-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30c23-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30c23-117">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="30c23-117">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="30c23-118">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="30c23-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="30c23-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30c23-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30c23-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="30c23-120">See also</span></span>

- [<span data-ttu-id="30c23-121">Método GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="30c23-121">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="30c23-122">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="30c23-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
