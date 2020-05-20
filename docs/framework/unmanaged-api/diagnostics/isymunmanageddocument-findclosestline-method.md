---
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
ms.openlocfilehash: 9e6134d39096c4ab157aa545646d83339f92a0b8
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441037"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="74a39-102">ISymUnmanagedDocument::FindClosestLine (Método)</span><span class="sxs-lookup"><span data-stu-id="74a39-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>
<span data-ttu-id="74a39-103">Devuelve la línea más cercana que es un punto de secuencia, dada una línea de este documento que puede ser o no un punto de secuencia.</span><span class="sxs-lookup"><span data-stu-id="74a39-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74a39-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74a39-104">Syntax</span></span>  
  
```cpp  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74a39-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74a39-105">Parameters</span></span>  
 `line`  
 <span data-ttu-id="74a39-106">de Una línea en este documento.</span><span class="sxs-lookup"><span data-stu-id="74a39-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="74a39-107">enuncia Puntero a una variable que recibe la línea.</span><span class="sxs-lookup"><span data-stu-id="74a39-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74a39-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="74a39-108">Return Value</span></span>  
 <span data-ttu-id="74a39-109">S_OK si el método se ejecuta correctamente; de lo contrario, un código de error.</span><span class="sxs-lookup"><span data-stu-id="74a39-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74a39-110">Consulta también</span><span class="sxs-lookup"><span data-stu-id="74a39-110">See also</span></span>

- [<span data-ttu-id="74a39-111">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74a39-111">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
