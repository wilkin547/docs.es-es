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
ms.openlocfilehash: a918b5c2334683348adc6a7382527faedb52d7b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683542"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a><span data-ttu-id="cf97e-102">ISymUnmanagedWriter::SetMethodSourceRange (Método)</span><span class="sxs-lookup"><span data-stu-id="cf97e-102">ISymUnmanagedWriter::SetMethodSourceRange Method</span></span>

<span data-ttu-id="cf97e-103">Especifica el principio y final reales de un método dentro de un archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="cf97e-103">Specifies the true start and end of a method within a source file.</span></span> <span data-ttu-id="cf97e-104">Utilice este método para especificar la extensión de un método independientemente de los puntos de secuencia que existen dentro del método.</span><span class="sxs-lookup"><span data-stu-id="cf97e-104">Use this method to specify the extent of a method independently of the sequence points that exist within the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf97e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf97e-105">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf97e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf97e-106">Parameters</span></span>  

 `startDoc`  
 <span data-ttu-id="cf97e-107">de Puntero al documento que contiene la posición inicial.</span><span class="sxs-lookup"><span data-stu-id="cf97e-107">[in] A pointer to the document containing the starting position.</span></span>  
  
 `startLine`  
 <span data-ttu-id="cf97e-108">de Número de línea inicial.</span><span class="sxs-lookup"><span data-stu-id="cf97e-108">[in] The starting line number.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="cf97e-109">de Columna inicial.</span><span class="sxs-lookup"><span data-stu-id="cf97e-109">[in] The starting column.</span></span>  
  
 `endDoc`  
 <span data-ttu-id="cf97e-110">de Puntero al documento que contiene la posición final.</span><span class="sxs-lookup"><span data-stu-id="cf97e-110">[in] A pointer to the document containing the ending position.</span></span>  
  
 `endLine`  
 <span data-ttu-id="cf97e-111">de El número de línea final.</span><span class="sxs-lookup"><span data-stu-id="cf97e-111">[in] The ending line number.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="cf97e-112">de Número de la columna final.</span><span class="sxs-lookup"><span data-stu-id="cf97e-112">[in] The ending column number.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf97e-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cf97e-113">Return Value</span></span>  

 <span data-ttu-id="cf97e-114">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="cf97e-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf97e-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf97e-115">Requirements</span></span>  

 <span data-ttu-id="cf97e-116">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="cf97e-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf97e-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cf97e-117">See also</span></span>

- [<span data-ttu-id="cf97e-118">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf97e-118">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
