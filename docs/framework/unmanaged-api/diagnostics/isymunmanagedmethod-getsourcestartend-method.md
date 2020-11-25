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
ms.openlocfilehash: f53afa5f87f1502f287b25e3d9756f9a54ad6869
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699292"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="5a0f8-102">ISymUnmanagedMethod::GetSourceStartEnd (Método)</span><span class="sxs-lookup"><span data-stu-id="5a0f8-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>

<span data-ttu-id="5a0f8-103">Obtiene las posiciones de documento inicial y final para el origen de este método.</span><span class="sxs-lookup"><span data-stu-id="5a0f8-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="5a0f8-104">La primera posición de la matriz es el inicio y la segunda posición de la matriz es el final.</span><span class="sxs-lookup"><span data-stu-id="5a0f8-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a0f8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a0f8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a0f8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5a0f8-106">Parameters</span></span>  

 `docs`  
 <span data-ttu-id="5a0f8-107">de Documentos de origen iniciales y finales.</span><span class="sxs-lookup"><span data-stu-id="5a0f8-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="5a0f8-108">de Líneas inicial y final de los documentos de origen correspondientes.</span><span class="sxs-lookup"><span data-stu-id="5a0f8-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="5a0f8-109">de Columnas inicial y final de los documentos de origen correspondientes.</span><span class="sxs-lookup"><span data-stu-id="5a0f8-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="5a0f8-110">[out] `true` Si se definieron las posiciones; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="5a0f8-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a0f8-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5a0f8-111">Return Value</span></span>  

 <span data-ttu-id="5a0f8-112">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="5a0f8-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a0f8-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a0f8-113">Requirements</span></span>  

 <span data-ttu-id="5a0f8-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="5a0f8-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a0f8-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5a0f8-115">See also</span></span>

- [<span data-ttu-id="5a0f8-116">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a0f8-116">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
