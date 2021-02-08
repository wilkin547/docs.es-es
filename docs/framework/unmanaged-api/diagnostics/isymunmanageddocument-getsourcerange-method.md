---
description: 'Más información acerca de: ISymUnmanagedDocument:: Getsourcerange ((método)'
title: ISymUnmanagedDocument::GetSourceRange (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type:
- apiref
ms.openlocfilehash: 98718298d7bf2f44d418a40f17ad19cdee0b6771
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790170"
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a><span data-ttu-id="cf6bb-103">ISymUnmanagedDocument::GetSourceRange (Método)</span><span class="sxs-lookup"><span data-stu-id="cf6bb-103">ISymUnmanagedDocument::GetSourceRange Method</span></span>

<span data-ttu-id="cf6bb-104">Devuelve el intervalo especificado del código fuente incrustado en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="cf6bb-104">Returns the specified range of the embedded source into the given buffer.</span></span> <span data-ttu-id="cf6bb-105">El búfer debe ser lo suficientemente grande como para contener el origen.</span><span class="sxs-lookup"><span data-stu-id="cf6bb-105">The buffer must be large enough to hold the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf6bb-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf6bb-106">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf6bb-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf6bb-107">Parameters</span></span>  

 `startLine`  
 <span data-ttu-id="cf6bb-108">de Línea inicial del documento actual.</span><span class="sxs-lookup"><span data-stu-id="cf6bb-108">[in] The starting line in the current document.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="cf6bb-109">de Columna inicial del documento actual.</span><span class="sxs-lookup"><span data-stu-id="cf6bb-109">[in] The starting column in the current document.</span></span>  
  
 `endLine`  
 <span data-ttu-id="cf6bb-110">de Última línea del documento actual.</span><span class="sxs-lookup"><span data-stu-id="cf6bb-110">[in] The final line in the current document.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="cf6bb-111">de Columna final del documento actual.</span><span class="sxs-lookup"><span data-stu-id="cf6bb-111">[in] The final column in the current document.</span></span>  
  
 `cSourceBytes`  
 <span data-ttu-id="cf6bb-112">de Tamaño del origen, en bytes.</span><span class="sxs-lookup"><span data-stu-id="cf6bb-112">[in] The size of the source, in bytes.</span></span>  
  
 `pcSourceBytes`  
 <span data-ttu-id="cf6bb-113">enuncia Puntero a una variable que recibe el tamaño de origen.</span><span class="sxs-lookup"><span data-stu-id="cf6bb-113">[out] A pointer to a variable that receives the source size.</span></span>  
  
 `source`  
 <span data-ttu-id="cf6bb-114">enuncia Tamaño y longitud del intervalo especificado del documento de origen, en bytes.</span><span class="sxs-lookup"><span data-stu-id="cf6bb-114">[out] The size and length of the specified range of the source document, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf6bb-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cf6bb-115">Return Value</span></span>  

 <span data-ttu-id="cf6bb-116">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="cf6bb-116">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf6bb-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf6bb-117">See also</span></span>

- [<span data-ttu-id="cf6bb-118">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf6bb-118">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
