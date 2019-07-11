---
title: ISymUnmanagedMethod::GetSourceStartEnd (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSourceStartEnd
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSourceStartEnd
helpviewer_keywords:
- GetSourceStartEnd method [.NET Framework debugging]
- ISymUnmanagedMethod::GetSourceStartEnd method [.NET Framework debugging]
ms.assetid: 2a420900-01f1-4461-8777-3a34a6dc1426
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a75fed4c46ea7e31177ac0446c8fae7805535323
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759428"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="76e25-102">ISymUnmanagedMethod::GetSourceStartEnd (Método)</span><span class="sxs-lookup"><span data-stu-id="76e25-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>
<span data-ttu-id="76e25-103">Obtiene las posiciones de documento de inicio y finalización para el origen de este método.</span><span class="sxs-lookup"><span data-stu-id="76e25-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="76e25-104">La primera posición de la matriz es el inicio y la segunda posición de la matriz es el final.</span><span class="sxs-lookup"><span data-stu-id="76e25-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76e25-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76e25-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76e25-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="76e25-106">Parameters</span></span>  
 `docs`  
 <span data-ttu-id="76e25-107">[in] Las iniciales y finales documentos de origen.</span><span class="sxs-lookup"><span data-stu-id="76e25-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="76e25-108">[in] Documentos de origen iniciales y finales de líneas en las correspondientes.</span><span class="sxs-lookup"><span data-stu-id="76e25-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="76e25-109">[in] Documentos de origen de las columnas iniciales y finales en las correspondientes.</span><span class="sxs-lookup"><span data-stu-id="76e25-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="76e25-110">[out] `true` si las posiciones se definieron; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="76e25-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76e25-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="76e25-111">Return Value</span></span>  
 <span data-ttu-id="76e25-112">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="76e25-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76e25-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76e25-113">Requirements</span></span>  
 <span data-ttu-id="76e25-114">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="76e25-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76e25-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="76e25-115">See also</span></span>

- [<span data-ttu-id="76e25-116">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="76e25-116">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
