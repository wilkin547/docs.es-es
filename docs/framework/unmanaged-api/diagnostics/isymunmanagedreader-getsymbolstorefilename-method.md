---
description: 'Más información acerca de: ISymUnmanagedReader:: Getsymbolstorefilename ((método)'
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
ms.openlocfilehash: 5cbb33a39cf2e93eab64d5f1f1fefc5ceba1d418
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763948"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="3ef09-103">ISymUnmanagedReader::GetSymbolStoreFileName (Método)</span><span class="sxs-lookup"><span data-stu-id="3ef09-103">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>

<span data-ttu-id="3ef09-104">Proporciona el nombre de archivo en disco del almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="3ef09-104">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ef09-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ef09-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ef09-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3ef09-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="3ef09-107">de Tamaño del `szName` búfer.</span><span class="sxs-lookup"><span data-stu-id="3ef09-107">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="3ef09-108">enuncia Puntero a la variable que recibe la longitud del nombre devuelto en `szName` , incluida la terminación null.</span><span class="sxs-lookup"><span data-stu-id="3ef09-108">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="3ef09-109">enuncia Puntero a la variable que recibe el nombre de archivo del almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="3ef09-109">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ef09-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3ef09-110">Return Value</span></span>  

 <span data-ttu-id="3ef09-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="3ef09-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ef09-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3ef09-112">Requirements</span></span>  

 <span data-ttu-id="3ef09-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="3ef09-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ef09-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ef09-114">See also</span></span>

- [<span data-ttu-id="3ef09-115">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ef09-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
