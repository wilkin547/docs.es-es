---
description: 'Más información acerca de: interfaz ISymUnmanagedBinder'
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
ms.openlocfilehash: 14ebccb028ab3388a8058dd05504c56a6df74c95
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689929"
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="02cb0-103">ISymUnmanagedBinder (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="02cb0-103">ISymUnmanagedBinder Interface</span></span>

<span data-ttu-id="02cb0-104">Representa un enlazador de símbolos para código no administrado.</span><span class="sxs-lookup"><span data-stu-id="02cb0-104">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="02cb0-105">Se trata de un riesgo para la seguridad de abrir un archivo de base de datos de programa (PDB) desde un origen que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="02cb0-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="02cb0-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="02cb0-106">Methods</span></span>  
  
|<span data-ttu-id="02cb0-107">Método</span><span class="sxs-lookup"><span data-stu-id="02cb0-107">Method</span></span>|<span data-ttu-id="02cb0-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="02cb0-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="02cb0-109">Método GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="02cb0-109">GetReaderForFile Method</span></span>](isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="02cb0-110">Dada una interfaz de metadatos y un nombre de archivo, devuelve la estructura [ISymUnmanagedReader](isymunmanagedreader-interface.md) correcta que leerá los símbolos de depuración asociados al módulo.</span><span class="sxs-lookup"><span data-stu-id="02cb0-110">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="02cb0-111">Método GetReaderFromStream</span><span class="sxs-lookup"><span data-stu-id="02cb0-111">GetReaderFromStream Method</span></span>](isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="02cb0-112">Dada una interfaz de metadatos y una secuencia que contiene el almacén de símbolos, devuelve la estructura [ISymUnmanagedReader](isymunmanagedreader-interface.md) correcta que leerá los símbolos de depuración del almacén de símbolos determinado.</span><span class="sxs-lookup"><span data-stu-id="02cb0-112">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="02cb0-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02cb0-113">Requirements</span></span>  

 <span data-ttu-id="02cb0-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="02cb0-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02cb0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="02cb0-115">See also</span></span>

- [<span data-ttu-id="02cb0-116">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="02cb0-116">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="02cb0-117">ISymUnmanagedBinder2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="02cb0-117">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="02cb0-118">ISymUnmanagedBinder3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="02cb0-118">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
