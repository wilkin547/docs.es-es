---
title: "ISymUnmanagedMethod::GetSourceStartEnd (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetSourceStartEnd
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetSourceStartEnd
helpviewer_keywords:
- GetSourceStartEnd method [.NET Framework debugging]
- ISymUnmanagedMethod::GetSourceStartEnd method [.NET Framework debugging]
ms.assetid: 2a420900-01f1-4461-8777-3a34a6dc1426
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f2bdc044d4560b616bd6eeb8d642567add1f659f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="97f48-102">ISymUnmanagedMethod::GetSourceStartEnd (Método)</span><span class="sxs-lookup"><span data-stu-id="97f48-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>
<span data-ttu-id="97f48-103">Obtiene las posiciones de documento de inicio y finalización para el origen de este método.</span><span class="sxs-lookup"><span data-stu-id="97f48-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="97f48-104">La primera posición de la matriz es el inicio y la segunda posición de la matriz es el final.</span><span class="sxs-lookup"><span data-stu-id="97f48-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97f48-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97f48-105">Syntax</span></span>  
  
```  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97f48-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="97f48-106">Parameters</span></span>  
 `docs`  
 <span data-ttu-id="97f48-107">[in] Las iniciales y finales documentos de origen.</span><span class="sxs-lookup"><span data-stu-id="97f48-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="97f48-108">[in] Documentos de origen de las líneas iniciales y finales en las correspondientes.</span><span class="sxs-lookup"><span data-stu-id="97f48-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="97f48-109">[in] Documentos de origen de las columnas iniciales y finales en las correspondientes.</span><span class="sxs-lookup"><span data-stu-id="97f48-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="97f48-110">[out] `true` si se definieron posiciones; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="97f48-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97f48-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="97f48-111">Return Value</span></span>  
 <span data-ttu-id="97f48-112">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="97f48-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97f48-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="97f48-113">Requirements</span></span>  
 <span data-ttu-id="97f48-114">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="97f48-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97f48-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="97f48-115">See Also</span></span>  
 [<span data-ttu-id="97f48-116">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="97f48-116">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
