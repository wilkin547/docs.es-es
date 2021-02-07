---
description: 'Más información acerca de: ISymUnmanagedDocument:: Findclosestline ((método)'
title: ISymUnmanagedDocument::FindClosestLine (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.FindClosestLine
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type:
- apiref
ms.openlocfilehash: 0409a5cc29bf148a49a5267d34662f763fc302d9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737836"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="c2609-103">ISymUnmanagedDocument::FindClosestLine (Método)</span><span class="sxs-lookup"><span data-stu-id="c2609-103">ISymUnmanagedDocument::FindClosestLine Method</span></span>

<span data-ttu-id="c2609-104">Devuelve la línea más cercana que es un punto de secuencia, dada una línea de este documento que puede ser o no un punto de secuencia.</span><span class="sxs-lookup"><span data-stu-id="c2609-104">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2609-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2609-105">Syntax</span></span>  
  
```cpp  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2609-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c2609-106">Parameters</span></span>  

 `line`  
 <span data-ttu-id="c2609-107">de Una línea en este documento.</span><span class="sxs-lookup"><span data-stu-id="c2609-107">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="c2609-108">enuncia Puntero a una variable que recibe la línea.</span><span class="sxs-lookup"><span data-stu-id="c2609-108">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2609-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c2609-109">Return Value</span></span>  

 <span data-ttu-id="c2609-110">S_OK si el método se ejecuta correctamente; de lo contrario, un código de error.</span><span class="sxs-lookup"><span data-stu-id="c2609-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2609-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2609-111">See also</span></span>

- [<span data-ttu-id="c2609-112">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2609-112">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
