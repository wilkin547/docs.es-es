---
title: ISymUnmanagedReader::GetSymbolStoreFileName (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymbolStoreFileName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymbolStoreFileName
helpviewer_keywords:
- GetSymbolStoreFileName method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymbolStoreFileName method [.NET Framework debugging]
ms.assetid: c84f4846-9bc8-44a4-9a76-e39106d6d8b2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b36f4007f286938169cc5d583908493916b9e6f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425345"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="080a1-102">ISymUnmanagedReader::GetSymbolStoreFileName (Método)</span><span class="sxs-lookup"><span data-stu-id="080a1-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="080a1-103">Proporciona el nombre de archivo en disco del almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="080a1-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="080a1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="080a1-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="080a1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="080a1-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="080a1-106">[in] El tamaño de la `szName` búfer.</span><span class="sxs-lookup"><span data-stu-id="080a1-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="080a1-107">[out] Un puntero a la variable que recibe la longitud del nombre devuelto en `szName`, incluida la terminación null.</span><span class="sxs-lookup"><span data-stu-id="080a1-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="080a1-108">[out] Un puntero a la variable que recibe el nombre de archivo del almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="080a1-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="080a1-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="080a1-109">Return Value</span></span>  
 <span data-ttu-id="080a1-110">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="080a1-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="080a1-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="080a1-111">Requirements</span></span>  
 <span data-ttu-id="080a1-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="080a1-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="080a1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="080a1-113">See Also</span></span>  
 [<span data-ttu-id="080a1-114">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="080a1-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
