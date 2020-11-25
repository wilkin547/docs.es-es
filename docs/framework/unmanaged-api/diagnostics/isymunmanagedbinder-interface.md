---
title: ISymUnmanagedBinder (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder
helpviewer_keywords:
- ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type:
- apiref
ms.openlocfilehash: 554e59484f00626726f7f024c69e93a5e6647130
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727385"
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="f3f9d-102">ISymUnmanagedBinder (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3f9d-102">ISymUnmanagedBinder Interface</span></span>

<span data-ttu-id="f3f9d-103">Representa un enlazador de símbolos para código no administrado.</span><span class="sxs-lookup"><span data-stu-id="f3f9d-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f3f9d-104">Se trata de un riesgo para la seguridad de abrir un archivo de base de datos de programa (PDB) desde un origen que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="f3f9d-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f3f9d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f3f9d-105">Methods</span></span>  
  
|<span data-ttu-id="f3f9d-106">Método</span><span class="sxs-lookup"><span data-stu-id="f3f9d-106">Method</span></span>|<span data-ttu-id="f3f9d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3f9d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f3f9d-108">Método GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="f3f9d-108">GetReaderForFile Method</span></span>](isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="f3f9d-109">Dada una interfaz de metadatos y un nombre de archivo, devuelve la estructura [ISymUnmanagedReader](isymunmanagedreader-interface.md) correcta que leerá los símbolos de depuración asociados al módulo.</span><span class="sxs-lookup"><span data-stu-id="f3f9d-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="f3f9d-110">Método GetReaderFromStream</span><span class="sxs-lookup"><span data-stu-id="f3f9d-110">GetReaderFromStream Method</span></span>](isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="f3f9d-111">Dada una interfaz de metadatos y una secuencia que contiene el almacén de símbolos, devuelve la estructura [ISymUnmanagedReader](isymunmanagedreader-interface.md) correcta que leerá los símbolos de depuración del almacén de símbolos determinado.</span><span class="sxs-lookup"><span data-stu-id="f3f9d-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f3f9d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3f9d-112">Requirements</span></span>  

 <span data-ttu-id="f3f9d-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f3f9d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3f9d-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f3f9d-114">See also</span></span>

- [<span data-ttu-id="f3f9d-115">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="f3f9d-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="f3f9d-116">ISymUnmanagedBinder2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3f9d-116">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="f3f9d-117">ISymUnmanagedBinder3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3f9d-117">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
