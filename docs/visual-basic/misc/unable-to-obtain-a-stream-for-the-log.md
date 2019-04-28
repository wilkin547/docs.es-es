---
title: No se pudo obtener un flujo para el registro
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
ms.openlocfilehash: 540ff3fbba72d33b2efaa58ad7a8019628f5e83f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922543"
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a><span data-ttu-id="b3926-102">No se pudo obtener un flujo para el registro</span><span class="sxs-lookup"><span data-stu-id="b3926-102">Unable to obtain a stream for the log</span></span>
<span data-ttu-id="b3926-103">No se pudo obtener un flujo para el registro.</span><span class="sxs-lookup"><span data-stu-id="b3926-103">Unable to obtain a stream for the log.</span></span> <span data-ttu-id="b3926-104">Nombres de archivo potenciales basados en \<nombre > ya están en uso.</span><span class="sxs-lookup"><span data-stu-id="b3926-104">Potential file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="b3926-105">El <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> clase no pudo crear un nuevo archivo de registro porque todos los posibles nombres de archivo de registro según \<nombre > ya están en uso.</span><span class="sxs-lookup"><span data-stu-id="b3926-105">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not create a new log file because all potential log file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="b3926-106">Si dispone de demasiados archivos de registro, podría ser un indicador de un problema de arquitectura con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b3926-106">Having too many log files may indicate an architectural problem with the application.</span></span> <span data-ttu-id="b3926-107">Consulte la documentación sobre la clase <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> para más información.</span><span class="sxs-lookup"><span data-stu-id="b3926-107">See the documentation for the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class for more information.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b3926-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="b3926-108">To correct this error</span></span>  
  
1. <span data-ttu-id="b3926-109">Establezca la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> en <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> o <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> para incluir una marca de fecha en el nombre del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="b3926-109">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> property to <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> or <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> to include a date-stamp in the log file name.</span></span>  
  
2. <span data-ttu-id="b3926-110">Almacene los registros existentes y quítelos del equipo para permitir que el objeto <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> cree nuevos registros.</span><span class="sxs-lookup"><span data-stu-id="b3926-110">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3926-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3926-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>
- [<span data-ttu-id="b3926-112">My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="b3926-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [<span data-ttu-id="b3926-113">My.Application.Info.DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="b3926-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
