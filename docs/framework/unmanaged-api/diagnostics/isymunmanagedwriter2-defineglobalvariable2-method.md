---
title: "ISymUnmanagedWriter2::DefineGlobalVariable2 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter2.DefineGlobalVariable2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d1214a7bc8cb2826e31c310c88bce8158aefd4f7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a><span data-ttu-id="68320-102">ISymUnmanagedWriter2::DefineGlobalVariable2 (Método)</span><span class="sxs-lookup"><span data-stu-id="68320-102">ISymUnmanagedWriter2::DefineGlobalVariable2 Method</span></span>
<span data-ttu-id="68320-103">Define una única variable global.</span><span class="sxs-lookup"><span data-stu-id="68320-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68320-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68320-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="68320-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="68320-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="68320-106">[in] El nombre de variable global.</span><span class="sxs-lookup"><span data-stu-id="68320-106">[in] The global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="68320-107">[in] Atributos de la variable globales.</span><span class="sxs-lookup"><span data-stu-id="68320-107">[in] The global variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="68320-108">[in] El token de metadatos de la firma.</span><span class="sxs-lookup"><span data-stu-id="68320-108">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="68320-109">[in] El tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="68320-109">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="68320-110">[in] La primera dirección para la especificación de parámetros.</span><span class="sxs-lookup"><span data-stu-id="68320-110">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="68320-111">[in] La segunda dirección para la especificación de parámetros.</span><span class="sxs-lookup"><span data-stu-id="68320-111">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="68320-112">[in] La tercera dirección de la especificación de parámetros.</span><span class="sxs-lookup"><span data-stu-id="68320-112">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="68320-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="68320-113">Return Value</span></span>  
 <span data-ttu-id="68320-114">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="68320-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68320-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="68320-115">Requirements</span></span>  
 <span data-ttu-id="68320-116">**Encabezado:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="68320-116">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68320-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="68320-117">See Also</span></span>  
 [<span data-ttu-id="68320-118">ISymUnmanagedWriter2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="68320-118">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [<span data-ttu-id="68320-119">DefineGlobalVariable (método)</span><span class="sxs-lookup"><span data-stu-id="68320-119">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
