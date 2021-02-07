---
description: 'Más información acerca de: interfaz Isymunmanagedbinder2 ('
title: ISymUnmanagedBinder2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2 Interface
helpviewer_keywords:
- ISymUnmanagedBinder2 interface [.NET Framework debugging]
ms.assetid: 7a59f405-73e8-4434-8bcc-a9dc45ea08e6
topic_type:
- apiref
ms.openlocfilehash: 73847cdc9366ec18974fac261cbbad4d7dc6ccc6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689890"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="40c0e-103">ISymUnmanagedBinder2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="40c0e-103">ISymUnmanagedBinder2 Interface</span></span>

<span data-ttu-id="40c0e-104">Representa un enlazador de símbolos para código no administrado y extiende la interfaz [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="40c0e-104">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="40c0e-105">Se trata de un riesgo para la seguridad de abrir un archivo de base de datos de programa (PDB) desde un origen que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="40c0e-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="40c0e-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="40c0e-106">Methods</span></span>  
  
|<span data-ttu-id="40c0e-107">Método</span><span class="sxs-lookup"><span data-stu-id="40c0e-107">Method</span></span>|<span data-ttu-id="40c0e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="40c0e-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="40c0e-109">Método GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="40c0e-109">GetReaderForFile2 Method</span></span>](isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="40c0e-110">Dada una interfaz de metadatos y un nombre de archivo, devuelve la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) correcta que leerá los símbolos de depuración asociados al módulo.</span><span class="sxs-lookup"><span data-stu-id="40c0e-110">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="40c0e-111">Proporciona una búsqueda más extensa que el método [ISymUnmanagedBinder:: GetReaderForFile (](isymunmanagedbinder-getreaderforfile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="40c0e-111">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="40c0e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40c0e-112">Requirements</span></span>  

 <span data-ttu-id="40c0e-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="40c0e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40c0e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="40c0e-114">See also</span></span>

- [<span data-ttu-id="40c0e-115">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="40c0e-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="40c0e-116">ISymUnmanagedBinder (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="40c0e-116">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="40c0e-117">ISymUnmanagedBinder3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="40c0e-117">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
