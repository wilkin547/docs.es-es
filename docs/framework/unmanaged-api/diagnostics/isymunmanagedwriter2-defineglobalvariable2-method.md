---
title: ISymUnmanagedWriter2::DefineGlobalVariable2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineGlobalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 067be401b793c227d8b5caa2706f84a59d3a09df
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499048"
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a><span data-ttu-id="954bb-102">ISymUnmanagedWriter2::DefineGlobalVariable2 (Método)</span><span class="sxs-lookup"><span data-stu-id="954bb-102">ISymUnmanagedWriter2::DefineGlobalVariable2 Method</span></span>
<span data-ttu-id="954bb-103">Define una única variable global.</span><span class="sxs-lookup"><span data-stu-id="954bb-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="954bb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="954bb-104">Syntax</span></span>  
  
```  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="954bb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="954bb-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="954bb-106">[in] El nombre de variable global.</span><span class="sxs-lookup"><span data-stu-id="954bb-106">[in] The global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="954bb-107">[in] Atributos de la variable globales.</span><span class="sxs-lookup"><span data-stu-id="954bb-107">[in] The global variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="954bb-108">[in] El token de metadatos de la firma.</span><span class="sxs-lookup"><span data-stu-id="954bb-108">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="954bb-109">[in] El tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="954bb-109">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="954bb-110">[in] La primera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="954bb-110">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="954bb-111">[in] La segunda dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="954bb-111">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="954bb-112">[in] Tercera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="954bb-112">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="954bb-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="954bb-113">Return Value</span></span>  
 <span data-ttu-id="954bb-114">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="954bb-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="954bb-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="954bb-115">Requirements</span></span>  
 <span data-ttu-id="954bb-116">**Encabezado**: CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="954bb-116">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="954bb-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="954bb-117">See also</span></span>
- [<span data-ttu-id="954bb-118">ISymUnmanagedWriter2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="954bb-118">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="954bb-119">DefineGlobalVariable (método)</span><span class="sxs-lookup"><span data-stu-id="954bb-119">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
