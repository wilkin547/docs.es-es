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
ms.openlocfilehash: caefc9773b0d208f8b20847b664f7bc017d2c076
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730999"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="419f0-102">GetHashFromAssemblyFile (Función)</span><span class="sxs-lookup"><span data-stu-id="419f0-102">GetHashFromAssemblyFile Function</span></span>

<span data-ttu-id="419f0-103">Obtiene un hash del archivo de ensamblado especificado mediante un algoritmo hash concreto.</span><span class="sxs-lookup"><span data-stu-id="419f0-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="419f0-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="419f0-104">This function has been deprecated.</span></span> <span data-ttu-id="419f0-105">Use el método [ICLRStrongName:: gethashfromassemblyfile (](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="419f0-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="419f0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="419f0-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="419f0-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="419f0-107">Parameters</span></span>  

 `szFilePath`  
 <span data-ttu-id="419f0-108">de Ruta de acceso al archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="419f0-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="419f0-109">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="419f0-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="419f0-110">Use cero para el algoritmo hash predeterminado.</span><span class="sxs-lookup"><span data-stu-id="419f0-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="419f0-111">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="419f0-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="419f0-112">de Tamaño máximo solicitado de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="419f0-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="419f0-113">enuncia El tamaño devuelto, en bytes, de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="419f0-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="419f0-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="419f0-114">Requirements</span></span>  

 <span data-ttu-id="419f0-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="419f0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="419f0-116">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="419f0-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="419f0-117">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="419f0-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="419f0-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="419f0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="419f0-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="419f0-119">See also</span></span>

- [<span data-ttu-id="419f0-120">Método GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="419f0-120">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="419f0-121">Método GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="419f0-121">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="419f0-122">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="419f0-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
