---
title: ISymUnmanagedWriter::SetMethodSourceRange (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetMethodSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetMethodSourceRange
helpviewer_keywords:
- SetMethodSourceRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetMethodSourceRange method [.NET Framework debugging]
ms.assetid: c698b86e-ace7-4b21-9549-f52d6a034959
topic_type:
- apiref
ms.openlocfilehash: 4ba3f31ae6d6b67d7beaa2f709bf6174b721136d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609526"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a><span data-ttu-id="6d9c0-102">ISymUnmanagedWriter::SetMethodSourceRange (Método)</span><span class="sxs-lookup"><span data-stu-id="6d9c0-102">ISymUnmanagedWriter::SetMethodSourceRange Method</span></span>
<span data-ttu-id="6d9c0-103">Especifica el principio y final reales de un método dentro de un archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="6d9c0-103">Specifies the true start and end of a method within a source file.</span></span> <span data-ttu-id="6d9c0-104">Utilice este método para especificar la extensión de un método independientemente de los puntos de secuencia que existen dentro del método.</span><span class="sxs-lookup"><span data-stu-id="6d9c0-104">Use this method to specify the extent of a method independently of the sequence points that exist within the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d9c0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d9c0-105">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d9c0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6d9c0-106">Parameters</span></span>  
 `startDoc`  
 <span data-ttu-id="6d9c0-107">de Puntero al documento que contiene la posición inicial.</span><span class="sxs-lookup"><span data-stu-id="6d9c0-107">[in] A pointer to the document containing the starting position.</span></span>  
  
 `startLine`  
 <span data-ttu-id="6d9c0-108">de Número de línea inicial.</span><span class="sxs-lookup"><span data-stu-id="6d9c0-108">[in] The starting line number.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="6d9c0-109">de Columna inicial.</span><span class="sxs-lookup"><span data-stu-id="6d9c0-109">[in] The starting column.</span></span>  
  
 `endDoc`  
 <span data-ttu-id="6d9c0-110">de Puntero al documento que contiene la posición final.</span><span class="sxs-lookup"><span data-stu-id="6d9c0-110">[in] A pointer to the document containing the ending position.</span></span>  
  
 `endLine`  
 <span data-ttu-id="6d9c0-111">de El número de línea final.</span><span class="sxs-lookup"><span data-stu-id="6d9c0-111">[in] The ending line number.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="6d9c0-112">de Número de la columna final.</span><span class="sxs-lookup"><span data-stu-id="6d9c0-112">[in] The ending column number.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d9c0-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6d9c0-113">Return Value</span></span>  
 <span data-ttu-id="6d9c0-114">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="6d9c0-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d9c0-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d9c0-115">Requirements</span></span>  
 <span data-ttu-id="6d9c0-116">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="6d9c0-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d9c0-117">Consulta también</span><span class="sxs-lookup"><span data-stu-id="6d9c0-117">See also</span></span>

- [<span data-ttu-id="6d9c0-118">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d9c0-118">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
