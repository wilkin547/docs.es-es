---
description: 'Más información acerca de: ISymUnmanagedReader:: Getmethodfromdocumentposition ((método)'
title: ISymUnmanagedReader::GetMethodFromDocumentPosition (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodFromDocumentPosition
helpviewer_keywords:
- GetMethodFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 55773dbc-9053-46e3-8a3c-86caa9d91fb4
topic_type:
- apiref
ms.openlocfilehash: 1289b02f8ea8440dcd1b308b6c91a46a213cabb2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764091"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="d2e40-103">ISymUnmanagedReader::GetMethodFromDocumentPosition (Método)</span><span class="sxs-lookup"><span data-stu-id="d2e40-103">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>

<span data-ttu-id="d2e40-104">Devuelve el método que contiene el punto de interrupción en la posición especificada de un documento.</span><span class="sxs-lookup"><span data-stu-id="d2e40-104">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2e40-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2e40-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2e40-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d2e40-106">Parameters</span></span>  

 `document`  
 <span data-ttu-id="d2e40-107">de Documento especificado.</span><span class="sxs-lookup"><span data-stu-id="d2e40-107">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="d2e40-108">de Línea del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="d2e40-108">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="d2e40-109">de Columna del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="d2e40-109">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="d2e40-110">enuncia Puntero a la dirección de un objeto de [interfaz ISymUnmanagedMethod](isymunmanagedmethod-interface.md) que representa el método que contiene el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="d2e40-110">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2e40-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d2e40-111">Return Value</span></span>  

 <span data-ttu-id="d2e40-112">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="d2e40-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2e40-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2e40-113">Requirements</span></span>  

 <span data-ttu-id="d2e40-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="d2e40-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2e40-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2e40-115">See also</span></span>

- [<span data-ttu-id="d2e40-116">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d2e40-116">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
