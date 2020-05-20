---
title: ISymUnmanagedBinder::GetReaderForFile (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderForFile
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderForFile
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderForFile method [.NET Framework debugging]
- GetReaderForFile method [.NET Framework debugging]
ms.assetid: 46c06258-831e-47c8-a50a-8650af6b637e
topic_type:
- apiref
ms.openlocfilehash: c4416e8e4395c4e1967155310d12a1eb68c42d83
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441739"
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="d4638-102">ISymUnmanagedBinder::GetReaderForFile (Método)</span><span class="sxs-lookup"><span data-stu-id="d4638-102">ISymUnmanagedBinder::GetReaderForFile Method</span></span>
<span data-ttu-id="d4638-103">Dada una interfaz de metadatos y un nombre de archivo, devuelve la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) correcta que leerá los símbolos de depuración asociados al módulo.</span><span class="sxs-lookup"><span data-stu-id="d4638-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="d4638-104">Este método abrirá el archivo de base de datos de programa (PDB) solo si se encuentra junto al archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="d4638-104">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="d4638-105">Este cambio se ha realizado por motivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d4638-105">This change has been made for security purposes.</span></span> <span data-ttu-id="d4638-106">Si necesita una búsqueda más amplia para el archivo PDB, use el método [isymunmanagedbinder2 (:: getreaderforfile2 (](isymunmanagedbinder2-getreaderforfile2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d4638-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4638-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4638-107">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4638-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d4638-108">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="d4638-109">de Puntero a la interfaz de importación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="d4638-109">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="d4638-110">de Puntero al nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="d4638-110">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="d4638-111">de Puntero a la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d4638-111">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="d4638-112">enuncia Puntero que se establece en la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="d4638-112">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4638-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d4638-113">Return Value</span></span>  
 <span data-ttu-id="d4638-114">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="d4638-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4638-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4638-115">Requirements</span></span>  
 <span data-ttu-id="d4638-116">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="d4638-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4638-117">Consulta también</span><span class="sxs-lookup"><span data-stu-id="d4638-117">See also</span></span>

- [<span data-ttu-id="d4638-118">ISymUnmanagedBinder (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4638-118">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="d4638-119">Método GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="d4638-119">GetReaderForFile2 Method</span></span>](isymunmanagedbinder2-getreaderforfile2-method.md)
