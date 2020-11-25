---
title: ISymUnmanagedENCUpdate::UpdateSymbolStore2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type:
- apiref
ms.openlocfilehash: c68cf632b789a523b19cc78d8d919c2278b1befa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699578"
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a><span data-ttu-id="227aa-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 (Método)</span><span class="sxs-lookup"><span data-stu-id="227aa-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 Method</span></span>

<span data-ttu-id="227aa-103">Permite a un compilador omitir las funciones que no se han modificado desde la secuencia de la base de datos de programa (PDB), siempre que la información de línea cumpla los requisitos.</span><span class="sxs-lookup"><span data-stu-id="227aa-103">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided the line information meets the requirements.</span></span> <span data-ttu-id="227aa-104">La información de línea correcta se puede determinar con la información de línea de PDB antigua y una diferencia para todas las líneas de la función.</span><span class="sxs-lookup"><span data-stu-id="227aa-104">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="227aa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="227aa-105">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
## <a name="parameters"></a><span data-ttu-id="227aa-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="227aa-106">Parameters</span></span>  

 `pIStream`  
 <span data-ttu-id="227aa-107">de Puntero a una [IStream](/windows/desktop/api/objidl/nn-objidl-istream) que contiene la información de la línea.</span><span class="sxs-lookup"><span data-stu-id="227aa-107">[in] A pointer to an [IStream](/windows/desktop/api/objidl/nn-objidl-istream) that contains the line information.</span></span>  
  
 `pDeltaLines`  
 <span data-ttu-id="227aa-108">de Puntero a una estructura [symlinedelta (](symlinedelta-structure.md) que contiene las líneas que han cambiado.</span><span class="sxs-lookup"><span data-stu-id="227aa-108">[in] A pointer to a [SYMLINEDELTA](symlinedelta-structure.md) structure that contains the lines that have changed.</span></span>  
  
 `cDeltaLines`  
 <span data-ttu-id="227aa-109">de `ULONG` Que representa el número de líneas que han cambiado.</span><span class="sxs-lookup"><span data-stu-id="227aa-109">[in] A `ULONG` that represents the number of lines that have changed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="227aa-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="227aa-110">Return Value</span></span>  

 <span data-ttu-id="227aa-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="227aa-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="227aa-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="227aa-112">Requirements</span></span>  

 <span data-ttu-id="227aa-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="227aa-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="227aa-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="227aa-114">See also</span></span>

- [<span data-ttu-id="227aa-115">ISymUnmanagedENCUpdate (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="227aa-115">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
