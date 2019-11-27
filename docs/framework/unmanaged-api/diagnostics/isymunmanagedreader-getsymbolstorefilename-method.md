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
ms.openlocfilehash: b3674c4058dba2f6185418b55b35eefb14c312f6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431242"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="83d23-102">ISymUnmanagedReader::GetSymbolStoreFileName (Método)</span><span class="sxs-lookup"><span data-stu-id="83d23-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="83d23-103">Proporciona el nombre de archivo en disco del almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="83d23-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83d23-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83d23-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83d23-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="83d23-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="83d23-106">de Tamaño del búfer de `szName`.</span><span class="sxs-lookup"><span data-stu-id="83d23-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="83d23-107">enuncia Puntero a la variable que recibe la longitud del nombre devuelto en `szName`, incluida la terminación null.</span><span class="sxs-lookup"><span data-stu-id="83d23-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="83d23-108">enuncia Puntero a la variable que recibe el nombre de archivo del almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="83d23-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83d23-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="83d23-109">Return Value</span></span>  
 <span data-ttu-id="83d23-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="83d23-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83d23-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="83d23-111">Requirements</span></span>  
 <span data-ttu-id="83d23-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="83d23-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83d23-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="83d23-113">See also</span></span>

- [<span data-ttu-id="83d23-114">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="83d23-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
