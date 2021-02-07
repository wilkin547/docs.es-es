---
description: 'Más información sobre: ISymENCUnmanagedMethod:: GetSourceExtentInDocument ((método)'
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
ms.openlocfilehash: 6fa9edb524a59b4420ebc737eb8d34eaf0c5c873
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737888"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a><span data-ttu-id="98f29-103">ISymENCUnmanagedMethod::GetSourceExtentInDocument (Método)</span><span class="sxs-lookup"><span data-stu-id="98f29-103">ISymENCUnmanagedMethod::GetSourceExtentInDocument Method</span></span>

<span data-ttu-id="98f29-104">Obtiene la línea de inicio más pequeña y la línea de finalización más grande para el método en un documento específico.</span><span class="sxs-lookup"><span data-stu-id="98f29-104">Gets the smallest start line and largest end line for the method in a specific document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98f29-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98f29-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98f29-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="98f29-106">Parameters</span></span>  

 `document`  
 <span data-ttu-id="98f29-107">de Puntero al documento.</span><span class="sxs-lookup"><span data-stu-id="98f29-107">[in] A pointer to the document.</span></span>  
  
 `pstartLine`  
 <span data-ttu-id="98f29-108">enuncia Un puntero a un `ULONG32` que recibe la línea de inicio.</span><span class="sxs-lookup"><span data-stu-id="98f29-108">[out] A pointer to a `ULONG32` that receives the start line.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="98f29-109">enuncia Un puntero a un `ULONG32` que recibe la línea final.</span><span class="sxs-lookup"><span data-stu-id="98f29-109">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98f29-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="98f29-110">Return Value</span></span>  

 <span data-ttu-id="98f29-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="98f29-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98f29-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98f29-112">Requirements</span></span>  

 <span data-ttu-id="98f29-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="98f29-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98f29-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="98f29-114">See also</span></span>

- [<span data-ttu-id="98f29-115">ISymENCUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="98f29-115">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
