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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b5a7d678d03435aa483ae4a4102672df504199d6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550622"
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a><span data-ttu-id="5dd2a-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 (Método)</span><span class="sxs-lookup"><span data-stu-id="5dd2a-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 Method</span></span>
<span data-ttu-id="5dd2a-103">Permite que un compilador que omita las funciones que no se han modificado desde el flujo de programa (PDB) de la base de datos, siempre que la información de línea cumpla los requisitos.</span><span class="sxs-lookup"><span data-stu-id="5dd2a-103">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided the line information meets the requirements.</span></span> <span data-ttu-id="5dd2a-104">Con la antigua información de línea PDB y un carácter delta para todas las líneas en la función se puede determinar la información de línea correctos.</span><span class="sxs-lookup"><span data-stu-id="5dd2a-104">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dd2a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5dd2a-105">Syntax</span></span>  
  
```  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5dd2a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5dd2a-106">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="5dd2a-107">[in] Un puntero a un [IStream](/windows/desktop/api/objidl/nn-objidl-istream) que contiene la información de línea.</span><span class="sxs-lookup"><span data-stu-id="5dd2a-107">[in] A pointer to an [IStream](/windows/desktop/api/objidl/nn-objidl-istream) that contains the line information.</span></span>  
  
 `pDeltaLines`  
 <span data-ttu-id="5dd2a-108">[in] Un puntero a un [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) estructura que contiene las líneas que han cambiado.</span><span class="sxs-lookup"><span data-stu-id="5dd2a-108">[in] A pointer to a [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) structure that contains the lines that have changed.</span></span>  
  
 `cDeltaLines`  
 <span data-ttu-id="5dd2a-109">[in] Un `ULONG` que representa el número de líneas que han cambiado.</span><span class="sxs-lookup"><span data-stu-id="5dd2a-109">[in] A `ULONG` that represents the number of lines that have changed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5dd2a-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5dd2a-110">Return Value</span></span>  
 <span data-ttu-id="5dd2a-111">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="5dd2a-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dd2a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5dd2a-112">Requirements</span></span>  
 <span data-ttu-id="5dd2a-113">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5dd2a-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dd2a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5dd2a-114">See also</span></span>
- [<span data-ttu-id="5dd2a-115">ISymUnmanagedENCUpdate (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5dd2a-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
