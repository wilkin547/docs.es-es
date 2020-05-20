---
title: ISymENCUnmanagedMethod::GetSourceExtentInDocument (Método)
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetSourceExtentInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetSourceExtentInDocument
helpviewer_keywords:
- GetSourceExtentInDocument method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetSourceExtentInDocument method [.NET Framework debugging]
ms.assetid: 9c5566ab-4ec7-4b61-9753-839bb90ae78c
topic_type:
- apiref
ms.openlocfilehash: 3ac8bb3a20ce82b734a572832a9cbb75fa2568c4
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441908"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a><span data-ttu-id="aa26c-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument (Método)</span><span class="sxs-lookup"><span data-stu-id="aa26c-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument Method</span></span>
<span data-ttu-id="aa26c-103">Obtiene la línea de inicio más pequeña y la línea de finalización más grande para el método en un documento específico.</span><span class="sxs-lookup"><span data-stu-id="aa26c-103">Gets the smallest start line and largest end line for the method in a specific document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa26c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa26c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa26c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aa26c-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="aa26c-106">de Puntero al documento.</span><span class="sxs-lookup"><span data-stu-id="aa26c-106">[in] A pointer to the document.</span></span>  
  
 `pstartLine`  
 <span data-ttu-id="aa26c-107">enuncia Un puntero a un `ULONG32` que recibe la línea de inicio.</span><span class="sxs-lookup"><span data-stu-id="aa26c-107">[out] A pointer to a `ULONG32` that receives the start line.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="aa26c-108">enuncia Un puntero a un `ULONG32` que recibe la línea final.</span><span class="sxs-lookup"><span data-stu-id="aa26c-108">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa26c-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="aa26c-109">Return Value</span></span>  
 <span data-ttu-id="aa26c-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="aa26c-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa26c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa26c-111">Requirements</span></span>  
 <span data-ttu-id="aa26c-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="aa26c-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa26c-113">Consulta también</span><span class="sxs-lookup"><span data-stu-id="aa26c-113">See also</span></span>

- [<span data-ttu-id="aa26c-114">ISymENCUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa26c-114">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
