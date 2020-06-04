---
title: Modo de archivo incorrecto
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: 534ea2d8316dc29cace798c5ad9b7697a290026f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409874"
---
# <a name="bad-file-mode"></a><span data-ttu-id="fa308-102">Modo de archivo incorrecto</span><span class="sxs-lookup"><span data-stu-id="fa308-102">Bad file mode</span></span>
<span data-ttu-id="fa308-103">Las instrucciones usadas para manipular el contenido del archivo deben ser adecuadas para el modo en el que se abrió el archivo.</span><span class="sxs-lookup"><span data-stu-id="fa308-103">Statements used in manipulating file contents must be appropriate to the mode in which the file was opened.</span></span> <span data-ttu-id="fa308-104">Entre las posibles causas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="fa308-104">Possible causes include:</span></span>  
  
- <span data-ttu-id="fa308-105">Una `FilePutObject` `FileGetObject` instrucción o especifica un archivo secuencial.</span><span class="sxs-lookup"><span data-stu-id="fa308-105">A `FilePutObject` or `FileGetObject` statement specifies a sequential file.</span></span>  
  
- <span data-ttu-id="fa308-106">Una `Print` instrucción especifica un archivo abierto para un modo de acceso distinto de `Output` o `Append` .</span><span class="sxs-lookup"><span data-stu-id="fa308-106">A `Print` statement specifies a file opened for an access mode other than `Output` or `Append`.</span></span>  
  
- <span data-ttu-id="fa308-107">Una `Input` instrucción especifica un archivo abierto para un modo de acceso distinto de`Input`</span><span class="sxs-lookup"><span data-stu-id="fa308-107">An `Input` statement specifies a file opened for an access mode other than `Input`</span></span>  
  
- <span data-ttu-id="fa308-108">Intento de escribir en un archivo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="fa308-108">An attempt to write to a read-only file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fa308-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="fa308-109">To correct this error</span></span>  
  
- <span data-ttu-id="fa308-110">Asegúrese de `FilePutObject` que `FileGetObject` solo se hace referencia a los archivos abiertos para `Random` o `Binary` acceso.</span><span class="sxs-lookup"><span data-stu-id="fa308-110">Make sure `FilePutObject` and `FileGetObject` are only referring to files open for `Random` or `Binary` access.</span></span>  
  
- <span data-ttu-id="fa308-111">Asegúrese `Print` de que especifica un archivo abierto para `Output` el `Append` modo de acceso o.</span><span class="sxs-lookup"><span data-stu-id="fa308-111">Make sure `Print` specifies a file opened for either `Output` or `Append` access mode.</span></span> <span data-ttu-id="fa308-112">Si no es así, use una instrucción diferente para colocar datos en el archivo o vuelva a abrir el archivo en un modo adecuado.</span><span class="sxs-lookup"><span data-stu-id="fa308-112">If not, use a different statement to place data in the file, or reopen the file in an appropriate mode.</span></span>  
  
- <span data-ttu-id="fa308-113">Asegúrese `Input` de que especifica un archivo abierto para `Input` .</span><span class="sxs-lookup"><span data-stu-id="fa308-113">Make sure `Input` specifies a file opened for `Input`.</span></span> <span data-ttu-id="fa308-114">Si no es así, use una instrucción diferente para colocar datos en el archivo o vuelva a abrir el archivo en un modo adecuado.</span><span class="sxs-lookup"><span data-stu-id="fa308-114">If not, use a different statement to place data in the file or reopen the file in an appropriate mode.</span></span>  
  
- <span data-ttu-id="fa308-115">Si está escribiendo en un archivo de solo lectura, cambie el estado de lectura y escritura del archivo o no intente escribir en él.</span><span class="sxs-lookup"><span data-stu-id="fa308-115">If you are writing to a read-only file, change the read/write status of the file or do not try to write to it.</span></span>  
  
- <span data-ttu-id="fa308-116">Use la funcionalidad disponible en el objeto `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="fa308-116">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa308-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa308-117">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem>
- [<span data-ttu-id="fa308-118">Solución del problema: leer y escribir en archivos de texto</span><span class="sxs-lookup"><span data-stu-id="fa308-118">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
