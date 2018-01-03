---
title: No se pudo obtener un flujo para el registro
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dba511ecd2a5c050fc2c037ac437e38715609e95
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a><span data-ttu-id="498b3-102">No se pudo obtener un flujo para el registro</span><span class="sxs-lookup"><span data-stu-id="498b3-102">Unable to obtain a stream for the log</span></span>
<span data-ttu-id="498b3-103">No se pudo obtener un flujo para el registro.</span><span class="sxs-lookup"><span data-stu-id="498b3-103">Unable to obtain a stream for the log.</span></span> <span data-ttu-id="498b3-104">Los nombres de archivo potenciales basados en \<nombre > ya están en uso.</span><span class="sxs-lookup"><span data-stu-id="498b3-104">Potential file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="498b3-105">El <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> clase no pudo crear un nuevo archivo de registro porque todos los posibles nombres de archivo de registro se basan en \<nombre > ya están en uso.</span><span class="sxs-lookup"><span data-stu-id="498b3-105">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not create a new log file because all potential log file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="498b3-106">Si dispone de demasiados archivos de registro, podría ser un indicador de un problema de arquitectura con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="498b3-106">Having too many log files may indicate an architectural problem with the application.</span></span> <span data-ttu-id="498b3-107">Consulte la documentación sobre la clase <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> para más información.</span><span class="sxs-lookup"><span data-stu-id="498b3-107">See the documentation for the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class for more information.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="498b3-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="498b3-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="498b3-109">Establezca la propiedad <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> en <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> o <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> para incluir una marca de fecha en el nombre del archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="498b3-109">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> property to <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> or <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> to include a date-stamp in the log file name.</span></span>  
  
2.  <span data-ttu-id="498b3-110">Almacene los registros existentes y quítelos del equipo para permitir que el objeto <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> cree nuevos registros.</span><span class="sxs-lookup"><span data-stu-id="498b3-110">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="498b3-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="498b3-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>  
 [<span data-ttu-id="498b3-112">My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="498b3-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)  
 [<span data-ttu-id="498b3-113">My.Application.Info.DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="498b3-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
