---
description: 'Más información sobre: ISymUnmanagedMethod:: Getsourcestartend ((método)'
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
ms.openlocfilehash: 0d247427998970d86c1ad1ec37f5b32a846a6f7c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709989"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="d949b-103">ISymUnmanagedMethod::GetSourceStartEnd (Método)</span><span class="sxs-lookup"><span data-stu-id="d949b-103">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>

<span data-ttu-id="d949b-104">Obtiene las posiciones de documento inicial y final para el origen de este método.</span><span class="sxs-lookup"><span data-stu-id="d949b-104">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="d949b-105">La primera posición de la matriz es el inicio y la segunda posición de la matriz es el final.</span><span class="sxs-lookup"><span data-stu-id="d949b-105">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d949b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d949b-106">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d949b-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d949b-107">Parameters</span></span>  

 `docs`  
 <span data-ttu-id="d949b-108">de Documentos de origen iniciales y finales.</span><span class="sxs-lookup"><span data-stu-id="d949b-108">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="d949b-109">de Líneas inicial y final de los documentos de origen correspondientes.</span><span class="sxs-lookup"><span data-stu-id="d949b-109">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="d949b-110">de Columnas inicial y final de los documentos de origen correspondientes.</span><span class="sxs-lookup"><span data-stu-id="d949b-110">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="d949b-111">[out] `true` Si se definieron las posiciones; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="d949b-111">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d949b-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d949b-112">Return Value</span></span>  

 <span data-ttu-id="d949b-113">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="d949b-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d949b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d949b-114">Requirements</span></span>  

 <span data-ttu-id="d949b-115">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="d949b-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d949b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d949b-116">See also</span></span>

- [<span data-ttu-id="d949b-117">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d949b-117">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
