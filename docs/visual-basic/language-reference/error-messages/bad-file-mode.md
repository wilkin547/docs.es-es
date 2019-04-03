---
title: Modo de archivo incorrecto
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: d3d0ebd003f178567ec9e9b19d6baccb8bc15f60
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819988"
---
# <a name="bad-file-mode"></a><span data-ttu-id="b29cd-102">Modo de archivo incorrecto</span><span class="sxs-lookup"><span data-stu-id="b29cd-102">Bad file mode</span></span>
<span data-ttu-id="b29cd-103">Las instrucciones que se utilizan para manipular el contenido del archivo deben ser adecuadas para el modo en que se abrió el archivo.</span><span class="sxs-lookup"><span data-stu-id="b29cd-103">Statements used in manipulating file contents must be appropriate to the mode in which the file was opened.</span></span> <span data-ttu-id="b29cd-104">Entre las posibles causas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="b29cd-104">Possible causes include:</span></span>  
  
-   <span data-ttu-id="b29cd-105">Un `FilePutObject` o `FileGetObject` instrucción especifica un archivo secuencial.</span><span class="sxs-lookup"><span data-stu-id="b29cd-105">A `FilePutObject` or `FileGetObject` statement specifies a sequential file.</span></span>  
  
-   <span data-ttu-id="b29cd-106">Un `Print` instrucción especifica un archivo abierto para un modo de acceso distinto `Output` o `Append`.</span><span class="sxs-lookup"><span data-stu-id="b29cd-106">A `Print` statement specifies a file opened for an access mode other than `Output` or `Append`.</span></span>  
  
-   <span data-ttu-id="b29cd-107">Un `Input` instrucción especifica un archivo abierto para un modo de acceso distinto `Input`</span><span class="sxs-lookup"><span data-stu-id="b29cd-107">An `Input` statement specifies a file opened for an access mode other than `Input`</span></span>  
  
-   <span data-ttu-id="b29cd-108">Se intenta escribir en un archivo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="b29cd-108">An attempt to write to a read-only file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b29cd-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="b29cd-109">To correct this error</span></span>  
  
-   <span data-ttu-id="b29cd-110">Asegúrese de que `FilePutObject` y `FileGetObject` sólo hacen referencia a archivos abiertos para `Random` o `Binary` acceso.</span><span class="sxs-lookup"><span data-stu-id="b29cd-110">Make sure `FilePutObject` and `FileGetObject` are only referring to files open for `Random` or `Binary` access.</span></span>  
  
-   <span data-ttu-id="b29cd-111">Asegúrese de que `Print` especifica un archivo abierto para cualquiera `Output` o `Append` modo de acceso.</span><span class="sxs-lookup"><span data-stu-id="b29cd-111">Make sure `Print` specifies a file opened for either `Output` or `Append` access mode.</span></span> <span data-ttu-id="b29cd-112">Si no es así, utilice otra instrucción para colocar datos en el archivo o vuelva a abrir el archivo en un modo adecuado.</span><span class="sxs-lookup"><span data-stu-id="b29cd-112">If not, use a different statement to place data in the file, or reopen the file in an appropriate mode.</span></span>  
  
-   <span data-ttu-id="b29cd-113">Asegúrese de que `Input` especifica un archivo abierto para `Input`.</span><span class="sxs-lookup"><span data-stu-id="b29cd-113">Make sure `Input` specifies a file opened for `Input`.</span></span> <span data-ttu-id="b29cd-114">Si no es así, utilice otra instrucción para colocar datos en el archivo o vuelva a abrir el archivo en un modo adecuado.</span><span class="sxs-lookup"><span data-stu-id="b29cd-114">If not, use a different statement to place data in the file or reopen the file in an appropriate mode.</span></span>  
  
-   <span data-ttu-id="b29cd-115">Si está escribiendo en un archivo de solo lectura, cambie el estado de lectura/escritura del archivo o no intente escribir en él.</span><span class="sxs-lookup"><span data-stu-id="b29cd-115">If you are writing to a read-only file, change the read/write status of the file or do not try to write to it.</span></span>  
  
-   <span data-ttu-id="b29cd-116">Use la funcionalidad disponible en el objeto `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="b29cd-116">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b29cd-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b29cd-117">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem>
- [<span data-ttu-id="b29cd-118">Solución de problemas: Leer y escribir en archivos de texto</span><span class="sxs-lookup"><span data-stu-id="b29cd-118">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
