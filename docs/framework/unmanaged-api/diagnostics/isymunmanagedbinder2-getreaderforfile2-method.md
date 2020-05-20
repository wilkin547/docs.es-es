---
title: ISymUnmanagedBinder2::GetReaderForFile2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2.GetReaderForFile2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2
helpviewer_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2 method [.NET Framework debugging]
- GetReaderForFile2 method [.NET Framework debugging]
ms.assetid: dd92dcaf-403c-464d-a254-21594985dddd
topic_type:
- apiref
ms.openlocfilehash: 97b9fa537fdd9147d6d9eda036013add5393e33c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441713"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a><span data-ttu-id="0948a-102">ISymUnmanagedBinder2::GetReaderForFile2 (Método)</span><span class="sxs-lookup"><span data-stu-id="0948a-102">ISymUnmanagedBinder2::GetReaderForFile2 Method</span></span>
<span data-ttu-id="0948a-103">Dada una interfaz de metadatos y un nombre de archivo, devuelve la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) correcta que leerá los símbolos de depuración asociados al módulo.</span><span class="sxs-lookup"><span data-stu-id="0948a-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="0948a-104">Este método proporciona una búsqueda más extensa del archivo de base de datos de programa (PDB) que el método [ISymUnmanagedBinder:: GetReaderForFile (](isymunmanagedbinder-getreaderforfile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0948a-104">This method provides a more extensive search for the program database (PDB) file than the [ISymUnmanagedBinder::GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0948a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0948a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0948a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0948a-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="0948a-107">de Puntero a la interfaz de importación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="0948a-107">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="0948a-108">de Puntero al nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="0948a-108">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="0948a-109">de Puntero a la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0948a-109">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="0948a-110">de Un valor de la enumeración [corsymsearchpolicyattributes (](corsymsearchpolicyattributes-enumeration.md) que especifica la Directiva que se va a usar al realizar una búsqueda de un lector de símbolos.</span><span class="sxs-lookup"><span data-stu-id="0948a-110">[in] A value of the [CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="0948a-111">enuncia Puntero que se establece en la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="0948a-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0948a-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0948a-112">Return Value</span></span>  
 <span data-ttu-id="0948a-113">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="0948a-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0948a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0948a-114">Requirements</span></span>  
 <span data-ttu-id="0948a-115">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0948a-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0948a-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0948a-116">Remarks</span></span>  
 <span data-ttu-id="0948a-117">Esta versión del método puede buscar el archivo PDB en áreas distintas de la derecha junto al módulo.</span><span class="sxs-lookup"><span data-stu-id="0948a-117">This version of the method can search for the PDB file in areas other than right next to the module.</span></span> <span data-ttu-id="0948a-118">La Directiva de búsqueda se puede controlar mediante la combinación de [corsymsearchpolicyattributes (](corsymsearchpolicyattributes-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="0948a-118">The search policy can be controlled by combining [CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md).</span></span> <span data-ttu-id="0948a-119">Por ejemplo, `AllowReferencePathAccess | AllowSymbolServerAccess` busca el archivo PDB junto al archivo ejecutable y en un servidor de símbolos, pero no consulta el registro o usa la ruta de acceso en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="0948a-119">For example, `AllowReferencePathAccess | AllowSymbolServerAccess` looks for the PDB next to the executable file and on a symbol server, but does not query the registry or use the path in the executable file.</span></span> <span data-ttu-id="0948a-120">Si `searchPath` se proporciona el parámetro, se buscará siempre esos directorios.</span><span class="sxs-lookup"><span data-stu-id="0948a-120">If the `searchPath` parameter is provided, those directories will always be searched.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0948a-121">Consulta también</span><span class="sxs-lookup"><span data-stu-id="0948a-121">See also</span></span>

- [<span data-ttu-id="0948a-122">ISymUnmanagedBinder2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0948a-122">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="0948a-123">Método GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="0948a-123">GetReaderForFile Method</span></span>](isymunmanagedbinder-getreaderforfile-method.md)
