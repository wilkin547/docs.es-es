---
description: 'Más información acerca de: no se puede escribir en el archivo de registro porque si se escribe en él, se superará el valor de MaximumSize'
title: No se puede escribir en el archivo de registro porque se superaría el valor de MaximumSize
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_FileExceedsMaximumSize
ms.assetid: 61747a9c-e460-424b-a365-73cdba9dd428
ms.openlocfilehash: 5c305c550f7a63183a0ac529adc788fa79b5794f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100456944"
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-cause-it-to-exceed-maximumsize-value"></a><span data-ttu-id="96b5b-103">No se puede escribir en el archivo de registro porque se superaría el valor de MaximumSize</span><span class="sxs-lookup"><span data-stu-id="96b5b-103">Unable to write to log file because writing to it would cause it to exceed MaximumSize value</span></span>

<span data-ttu-id="96b5b-104">La clase <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> no pudo escribir en el archivo de registro porque:</span><span class="sxs-lookup"><span data-stu-id="96b5b-104">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not write to the log file because:</span></span>  
  
- <span data-ttu-id="96b5b-105">El tamaño del archivo de registro (en bytes) es mayor que el valor de la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A></span><span class="sxs-lookup"><span data-stu-id="96b5b-105">The log file size (in bytes) is greater than the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> property</span></span>  
  
     <span data-ttu-id="96b5b-106">y</span><span class="sxs-lookup"><span data-stu-id="96b5b-106">—and—</span></span>  
  
- <span data-ttu-id="96b5b-107">El valor de la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> es <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span><span class="sxs-lookup"><span data-stu-id="96b5b-107">The value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property was <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="96b5b-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="96b5b-108">To correct this error</span></span>  
  
1. <span data-ttu-id="96b5b-109">Almacene los registros existentes y quítelos del equipo para permitir que el objeto <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> cree nuevos registros.</span><span class="sxs-lookup"><span data-stu-id="96b5b-109">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
2. <span data-ttu-id="96b5b-110">Cambie el valor de la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> para permitir que los registros tengan mayor tamaño.</span><span class="sxs-lookup"><span data-stu-id="96b5b-110">Change the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> property to allow for larger logs.</span></span>  
  
3. <span data-ttu-id="96b5b-111">Establezca la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> en <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> para descartar los mensajes sin advertir si el registro es demasiado grande.</span><span class="sxs-lookup"><span data-stu-id="96b5b-111">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property to <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> to discard messages without warning if the log is too large.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96b5b-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="96b5b-112">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- [<span data-ttu-id="96b5b-113">My. Application. log</span><span class="sxs-lookup"><span data-stu-id="96b5b-113">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [<span data-ttu-id="96b5b-114">My. Application. info. DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="96b5b-114">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
