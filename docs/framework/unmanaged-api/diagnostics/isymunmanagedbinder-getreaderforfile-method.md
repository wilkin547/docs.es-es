---
description: 'Más información sobre: ISymUnmanagedBinder:: GetReaderForFile ((método)'
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
ms.openlocfilehash: ede494cbc1bbe4059b98a639c1d0621dc2cbdfa6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790222"
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="ed724-103">ISymUnmanagedBinder::GetReaderForFile (Método)</span><span class="sxs-lookup"><span data-stu-id="ed724-103">ISymUnmanagedBinder::GetReaderForFile Method</span></span>

<span data-ttu-id="ed724-104">Dada una interfaz de metadatos y un nombre de archivo, devuelve la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) correcta que leerá los símbolos de depuración asociados al módulo.</span><span class="sxs-lookup"><span data-stu-id="ed724-104">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="ed724-105">Este método abrirá el archivo de base de datos de programa (PDB) solo si se encuentra junto al archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="ed724-105">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="ed724-106">Este cambio se ha realizado por motivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ed724-106">This change has been made for security purposes.</span></span> <span data-ttu-id="ed724-107">Si necesita una búsqueda más amplia para el archivo PDB, use el método [isymunmanagedbinder2 (:: getreaderforfile2 (](isymunmanagedbinder2-getreaderforfile2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ed724-107">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed724-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed724-108">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed724-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ed724-109">Parameters</span></span>  

 `importer`  
 <span data-ttu-id="ed724-110">de Puntero a la interfaz de importación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="ed724-110">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="ed724-111">de Puntero al nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="ed724-111">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="ed724-112">de Puntero a la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ed724-112">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="ed724-113">enuncia Puntero que se establece en la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="ed724-113">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed724-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ed724-114">Return Value</span></span>  

 <span data-ttu-id="ed724-115">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="ed724-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed724-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed724-116">Requirements</span></span>  

 <span data-ttu-id="ed724-117">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="ed724-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed724-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed724-118">See also</span></span>

- [<span data-ttu-id="ed724-119">ISymUnmanagedBinder (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed724-119">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="ed724-120">Método GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="ed724-120">GetReaderForFile2 Method</span></span>](isymunmanagedbinder2-getreaderforfile2-method.md)
