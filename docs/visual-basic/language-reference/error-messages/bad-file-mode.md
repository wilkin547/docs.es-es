---
description: 'Más información acerca de: modo de archivo incorrecto'
title: Modo de archivo incorrecto
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: da792407fb37f5c206be7ff39da14d314ef1e2d2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797086"
---
# <a name="bad-file-mode"></a><span data-ttu-id="1eb12-103">Modo de archivo incorrecto</span><span class="sxs-lookup"><span data-stu-id="1eb12-103">Bad file mode</span></span>

<span data-ttu-id="1eb12-104">Las instrucciones usadas para manipular el contenido del archivo deben ser adecuadas para el modo en el que se abrió el archivo.</span><span class="sxs-lookup"><span data-stu-id="1eb12-104">Statements used in manipulating file contents must be appropriate to the mode in which the file was opened.</span></span> <span data-ttu-id="1eb12-105">Entre las causas posibles se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="1eb12-105">Possible causes include:</span></span>  
  
- <span data-ttu-id="1eb12-106">Una `FilePutObject` `FileGetObject` instrucción o especifica un archivo secuencial.</span><span class="sxs-lookup"><span data-stu-id="1eb12-106">A `FilePutObject` or `FileGetObject` statement specifies a sequential file.</span></span>  
  
- <span data-ttu-id="1eb12-107">Una `Print` instrucción especifica un archivo abierto para un modo de acceso distinto de `Output` o `Append` .</span><span class="sxs-lookup"><span data-stu-id="1eb12-107">A `Print` statement specifies a file opened for an access mode other than `Output` or `Append`.</span></span>  
  
- <span data-ttu-id="1eb12-108">Una `Input` instrucción especifica un archivo abierto para un modo de acceso distinto de `Input`</span><span class="sxs-lookup"><span data-stu-id="1eb12-108">An `Input` statement specifies a file opened for an access mode other than `Input`</span></span>  
  
- <span data-ttu-id="1eb12-109">Intento de escribir en un archivo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="1eb12-109">An attempt to write to a read-only file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1eb12-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="1eb12-110">To correct this error</span></span>  
  
- <span data-ttu-id="1eb12-111">Asegúrese de `FilePutObject` que `FileGetObject` solo se hace referencia a los archivos abiertos para `Random` o `Binary` acceso.</span><span class="sxs-lookup"><span data-stu-id="1eb12-111">Make sure `FilePutObject` and `FileGetObject` are only referring to files open for `Random` or `Binary` access.</span></span>  
  
- <span data-ttu-id="1eb12-112">Asegúrese `Print` de que especifica un archivo abierto para `Output` el `Append` modo de acceso o.</span><span class="sxs-lookup"><span data-stu-id="1eb12-112">Make sure `Print` specifies a file opened for either `Output` or `Append` access mode.</span></span> <span data-ttu-id="1eb12-113">Si no es así, use una instrucción diferente para colocar datos en el archivo o vuelva a abrir el archivo en un modo adecuado.</span><span class="sxs-lookup"><span data-stu-id="1eb12-113">If not, use a different statement to place data in the file, or reopen the file in an appropriate mode.</span></span>  
  
- <span data-ttu-id="1eb12-114">Asegúrese `Input` de que especifica un archivo abierto para `Input` .</span><span class="sxs-lookup"><span data-stu-id="1eb12-114">Make sure `Input` specifies a file opened for `Input`.</span></span> <span data-ttu-id="1eb12-115">Si no es así, use una instrucción diferente para colocar datos en el archivo o vuelva a abrir el archivo en un modo adecuado.</span><span class="sxs-lookup"><span data-stu-id="1eb12-115">If not, use a different statement to place data in the file or reopen the file in an appropriate mode.</span></span>  
  
- <span data-ttu-id="1eb12-116">Si está escribiendo en un archivo de solo lectura, cambie el estado de lectura y escritura del archivo o no intente escribir en él.</span><span class="sxs-lookup"><span data-stu-id="1eb12-116">If you are writing to a read-only file, change the read/write status of the file or do not try to write to it.</span></span>  
  
- <span data-ttu-id="1eb12-117">Use la funcionalidad disponible en el objeto `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="1eb12-117">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eb12-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="1eb12-118">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem>
- [<span data-ttu-id="1eb12-119">Solución del problema: leer y escribir en archivos de texto</span><span class="sxs-lookup"><span data-stu-id="1eb12-119">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
