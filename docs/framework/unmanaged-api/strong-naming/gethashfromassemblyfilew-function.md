---
description: 'Más información acerca de: Gethashfromassemblyfilew ((función)'
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
ms.openlocfilehash: 7f44106f12a2d21ea67acb874b577c5b303632b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736679"
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="1c34d-103">GetHashFromAssemblyFileW (Función)</span><span class="sxs-lookup"><span data-stu-id="1c34d-103">GetHashFromAssemblyFileW Function</span></span>

<span data-ttu-id="1c34d-104">Obtiene un hash del archivo de ensamblado especificado mediante un algoritmo hash concreto.</span><span class="sxs-lookup"><span data-stu-id="1c34d-104">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="1c34d-105">La ruta de acceso al archivo de ensamblado debe especificarse como una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="1c34d-105">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="1c34d-106">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="1c34d-106">This function has been deprecated.</span></span> <span data-ttu-id="1c34d-107">Use el método [ICLRStrongName:: gethashfromassemblyfilew (](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="1c34d-107">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c34d-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c34d-108">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c34d-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1c34d-109">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="1c34d-110">de Ruta de acceso al archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="1c34d-110">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="1c34d-111">Este parámetro debe ser una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="1c34d-111">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="1c34d-112">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="1c34d-112">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="1c34d-113">Use cero para el algoritmo hash predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1c34d-113">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="1c34d-114">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="1c34d-114">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="1c34d-115">de Tamaño máximo solicitado de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="1c34d-115">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="1c34d-116">enuncia El tamaño devuelto, en bytes, de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="1c34d-116">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c34d-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c34d-117">Requirements</span></span>  

 <span data-ttu-id="1c34d-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c34d-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c34d-119">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="1c34d-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="1c34d-120">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1c34d-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1c34d-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c34d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c34d-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c34d-122">See also</span></span>

- [<span data-ttu-id="1c34d-123">Método GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="1c34d-123">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="1c34d-124">Método GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="1c34d-124">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="1c34d-125">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c34d-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
