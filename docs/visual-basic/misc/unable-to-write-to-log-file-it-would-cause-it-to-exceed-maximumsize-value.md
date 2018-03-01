---
title: "No se puede escribir en el archivo de registro porque se superaría el valor de MaximumSize"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrApplicationLog_FileExceedsMaximumSize
ms.assetid: 61747a9c-e460-424b-a365-73cdba9dd428
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4004dca2a3b9f13583cfdfe43f89bc4bff5dd6d6
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-cause-it-to-exceed-maximumsize-value"></a><span data-ttu-id="20574-102">No se puede escribir en el archivo de registro porque se superaría el valor de MaximumSize</span><span class="sxs-lookup"><span data-stu-id="20574-102">Unable to write to log file because writing to it would cause it to exceed MaximumSize value</span></span>
<span data-ttu-id="20574-103">La clase <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> no pudo escribir en el archivo de registro porque:</span><span class="sxs-lookup"><span data-stu-id="20574-103">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not write to the log file because:</span></span>  
  
-   <span data-ttu-id="20574-104">El tamaño del archivo de registro (en bytes) es mayor que el valor de la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> </span><span class="sxs-lookup"><span data-stu-id="20574-104">The log file size (in bytes) is greater than the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> property</span></span>  
  
     <span data-ttu-id="20574-105">y</span><span class="sxs-lookup"><span data-stu-id="20574-105">—and—</span></span>  
  
-   <span data-ttu-id="20574-106">El valor de la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> es <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span><span class="sxs-lookup"><span data-stu-id="20574-106">The value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property was <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="20574-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="20574-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="20574-108">Almacene los registros existentes y quítelos del equipo para permitir que el objeto <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> cree nuevos registros.</span><span class="sxs-lookup"><span data-stu-id="20574-108">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
2.  <span data-ttu-id="20574-109">Cambie el valor de la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> para permitir que los registros tengan mayor tamaño.</span><span class="sxs-lookup"><span data-stu-id="20574-109">Change the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> property to allow for larger logs.</span></span>  
  
3.  <span data-ttu-id="20574-110">Establezca la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> en <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> para descartar los mensajes sin advertir si el registro es demasiado grande.</span><span class="sxs-lookup"><span data-stu-id="20574-110">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property to <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> to discard messages without warning if the log is too large.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20574-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="20574-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>  
 [<span data-ttu-id="20574-112">My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="20574-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)  
 [<span data-ttu-id="20574-113">My.Application.Info.DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="20574-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
