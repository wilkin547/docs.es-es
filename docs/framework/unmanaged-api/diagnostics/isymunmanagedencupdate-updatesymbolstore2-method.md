---
title: "ISymUnmanagedENCUpdate::UpdateSymbolStore2 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a366047530f3433ab1bfbb5f30d4b9b54c5bdb08
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a><span data-ttu-id="f9a21-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 (Método)</span><span class="sxs-lookup"><span data-stu-id="f9a21-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 Method</span></span>
<span data-ttu-id="f9a21-103">Permite a un compilador omitir las funciones que no se han modificado desde el flujo de programa (PDB) de la base de datos, siempre que la información de línea cumpla los requisitos.</span><span class="sxs-lookup"><span data-stu-id="f9a21-103">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided the line information meets the requirements.</span></span> <span data-ttu-id="f9a21-104">La información de línea correcta puede determinarse con la antigua información de línea PDB y un carácter delta para todas las líneas de la función.</span><span class="sxs-lookup"><span data-stu-id="f9a21-104">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9a21-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9a21-105">Syntax</span></span>  
  
```  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f9a21-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f9a21-106">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="f9a21-107">[in] Un puntero a un <xref:IStream> que contiene la información de línea.</span><span class="sxs-lookup"><span data-stu-id="f9a21-107">[in] A pointer to an <xref:IStream> that contains the line information.</span></span>  
  
 `pDeltaLines`  
 <span data-ttu-id="f9a21-108">[in] Un puntero a un [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) estructura que contiene las líneas que han cambiado.</span><span class="sxs-lookup"><span data-stu-id="f9a21-108">[in] A pointer to a [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) structure that contains the lines that have changed.</span></span>  
  
 `cDeltaLines`  
 <span data-ttu-id="f9a21-109">[in] Un `ULONG` que representa el número de líneas que han cambiado.</span><span class="sxs-lookup"><span data-stu-id="f9a21-109">[in] A `ULONG` that represents the number of lines that have changed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9a21-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f9a21-110">Return Value</span></span>  
 <span data-ttu-id="f9a21-111">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="f9a21-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9a21-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f9a21-112">Requirements</span></span>  
 <span data-ttu-id="f9a21-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f9a21-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9a21-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9a21-114">See Also</span></span>  
 [<span data-ttu-id="f9a21-115">ISymUnmanagedENCUpdate (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9a21-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
