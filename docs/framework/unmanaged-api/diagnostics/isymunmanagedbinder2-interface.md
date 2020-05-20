---
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
ms.openlocfilehash: 8a4fbb40ec2426d000628fbd6d5f0241d3152c18
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441674"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="88ab4-102">ISymUnmanagedBinder2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="88ab4-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="88ab4-103">Representa un enlazador de símbolos para código no administrado y extiende la interfaz [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="88ab4-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="88ab4-104">Se trata de un riesgo para la seguridad de abrir un archivo de base de datos de programa (PDB) desde un origen que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="88ab4-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="88ab4-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="88ab4-105">Methods</span></span>  
  
|<span data-ttu-id="88ab4-106">Método</span><span class="sxs-lookup"><span data-stu-id="88ab4-106">Method</span></span>|<span data-ttu-id="88ab4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="88ab4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="88ab4-108">Método GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="88ab4-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="88ab4-109">Dada una interfaz de metadatos y un nombre de archivo, devuelve la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) correcta que leerá los símbolos de depuración asociados al módulo.</span><span class="sxs-lookup"><span data-stu-id="88ab4-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="88ab4-110">Proporciona una búsqueda más extensa que el método [ISymUnmanagedBinder:: GetReaderForFile (](isymunmanagedbinder-getreaderforfile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="88ab4-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="88ab4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88ab4-111">Requirements</span></span>  
 <span data-ttu-id="88ab4-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="88ab4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88ab4-113">Consulta también</span><span class="sxs-lookup"><span data-stu-id="88ab4-113">See also</span></span>

- [<span data-ttu-id="88ab4-114">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="88ab4-114">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="88ab4-115">ISymUnmanagedBinder (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="88ab4-115">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="88ab4-116">ISymUnmanagedBinder3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="88ab4-116">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
