---
description: 'Más información sobre: Isymunmanagedbinder3 (:: Getreaderfromcallback ((método)'
title: ISymUnmanagedBinder3::GetReaderFromCallback (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3.GetReaderFromCallback
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3::GetReaderFromCallback
helpviewer_keywords:
- GetReaderFromCallback method [.NET Framework debugging]
- ISymUnmanagedBinder3::GetReaderFromCallback method [.NET Framework debugging]
ms.assetid: 4ef83bd2-3d8e-499e-8a12-d9d6fd6ced30
topic_type:
- apiref
ms.openlocfilehash: ba7c819678fee7625f3cddb29d99f5d7f4c6f991
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689877"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a><span data-ttu-id="99c4a-103">ISymUnmanagedBinder3::GetReaderFromCallback (Método)</span><span class="sxs-lookup"><span data-stu-id="99c4a-103">ISymUnmanagedBinder3::GetReaderFromCallback Method</span></span>

<span data-ttu-id="99c4a-104">Permite al usuario implementar o proporcionar a través `IID_IDiaReadExeAtRVACallback` `IID_IDiaReadExeAtOffsetCallback` de la devolución de llamada o para obtener la información del directorio de depuración de la memoria.</span><span class="sxs-lookup"><span data-stu-id="99c4a-104">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the debug directory information from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99c4a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99c4a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99c4a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="99c4a-106">Parameters</span></span>  

 `importer`  
 <span data-ttu-id="99c4a-107">de Puntero a la interfaz de importación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="99c4a-107">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="99c4a-108">de Puntero al nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="99c4a-108">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="99c4a-109">de Puntero a la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="99c4a-109">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="99c4a-110">de Un valor de la enumeración [corsymsearchpolicyattributes (](corsymsearchpolicyattributes-enumeration.md) que especifica la Directiva que se va a usar al realizar una búsqueda de un lector de símbolos.</span><span class="sxs-lookup"><span data-stu-id="99c4a-110">[in] A value of the [CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `callback`  
 <span data-ttu-id="99c4a-111">de Puntero a la función de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="99c4a-111">[in] A pointer to the callback function.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="99c4a-112">enuncia Puntero que se establece en la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="99c4a-112">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99c4a-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="99c4a-113">Return Value</span></span>  

 <span data-ttu-id="99c4a-114">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="99c4a-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99c4a-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99c4a-115">Requirements</span></span>  

 <span data-ttu-id="99c4a-116">**Encabezado:** CorSym. idl</span><span class="sxs-lookup"><span data-stu-id="99c4a-116">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99c4a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="99c4a-117">See also</span></span>

- [<span data-ttu-id="99c4a-118">ISymUnmanagedBinder3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="99c4a-118">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
