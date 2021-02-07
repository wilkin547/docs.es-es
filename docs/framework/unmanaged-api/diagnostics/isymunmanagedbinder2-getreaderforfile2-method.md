---
description: 'Más información sobre: Isymunmanagedbinder2 (:: Getreaderforfile2 ((método)'
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
ms.openlocfilehash: c1a180ceec07c3087150613365acfce646adc34e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689942"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a><span data-ttu-id="5946f-103">ISymUnmanagedBinder2::GetReaderForFile2 (Método)</span><span class="sxs-lookup"><span data-stu-id="5946f-103">ISymUnmanagedBinder2::GetReaderForFile2 Method</span></span>

<span data-ttu-id="5946f-104">Dada una interfaz de metadatos y un nombre de archivo, devuelve la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) correcta que leerá los símbolos de depuración asociados al módulo.</span><span class="sxs-lookup"><span data-stu-id="5946f-104">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="5946f-105">Este método proporciona una búsqueda más extensa del archivo de base de datos de programa (PDB) que el método [ISymUnmanagedBinder:: GetReaderForFile (](isymunmanagedbinder-getreaderforfile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5946f-105">This method provides a more extensive search for the program database (PDB) file than the [ISymUnmanagedBinder::GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5946f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5946f-106">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5946f-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5946f-107">Parameters</span></span>  

 `importer`  
 <span data-ttu-id="5946f-108">de Puntero a la interfaz de importación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="5946f-108">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="5946f-109">de Puntero al nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="5946f-109">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="5946f-110">de Puntero a la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="5946f-110">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="5946f-111">de Un valor de la enumeración [corsymsearchpolicyattributes (](corsymsearchpolicyattributes-enumeration.md) que especifica la Directiva que se va a usar al realizar una búsqueda de un lector de símbolos.</span><span class="sxs-lookup"><span data-stu-id="5946f-111">[in] A value of the [CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="5946f-112">enuncia Puntero que se establece en la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="5946f-112">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5946f-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5946f-113">Return Value</span></span>  

 <span data-ttu-id="5946f-114">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="5946f-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5946f-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5946f-115">Requirements</span></span>  

 <span data-ttu-id="5946f-116">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="5946f-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5946f-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5946f-117">Remarks</span></span>  

 <span data-ttu-id="5946f-118">Esta versión del método puede buscar el archivo PDB en áreas distintas de la derecha junto al módulo.</span><span class="sxs-lookup"><span data-stu-id="5946f-118">This version of the method can search for the PDB file in areas other than right next to the module.</span></span> <span data-ttu-id="5946f-119">La Directiva de búsqueda se puede controlar mediante la combinación de [corsymsearchpolicyattributes (](corsymsearchpolicyattributes-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="5946f-119">The search policy can be controlled by combining [CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md).</span></span> <span data-ttu-id="5946f-120">Por ejemplo, `AllowReferencePathAccess | AllowSymbolServerAccess` busca el archivo PDB junto al archivo ejecutable y en un servidor de símbolos, pero no consulta el registro o usa la ruta de acceso en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="5946f-120">For example, `AllowReferencePathAccess | AllowSymbolServerAccess` looks for the PDB next to the executable file and on a symbol server, but does not query the registry or use the path in the executable file.</span></span> <span data-ttu-id="5946f-121">Si `searchPath` se proporciona el parámetro, se buscará siempre esos directorios.</span><span class="sxs-lookup"><span data-stu-id="5946f-121">If the `searchPath` parameter is provided, those directories will always be searched.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5946f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5946f-122">See also</span></span>

- [<span data-ttu-id="5946f-123">ISymUnmanagedBinder2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5946f-123">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="5946f-124">Método GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="5946f-124">GetReaderForFile Method</span></span>](isymunmanagedbinder-getreaderforfile-method.md)
