---
title: Demasiados archivos
ms.date: 07/20/2015
f1_keywords:
- vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
ms.openlocfilehash: 38d39ad20f350137d714ae5d09db5d2204b83621
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84362805"
---
# <a name="too-many-files"></a><span data-ttu-id="77308-102">Demasiados archivos</span><span class="sxs-lookup"><span data-stu-id="77308-102">Too many files</span></span>
<span data-ttu-id="77308-103">Se han creado más archivos en el directorio raíz que los que permite el sistema operativo, o se han abierto más archivos que el número especificado en el valor **files =** en la configuración. Archivo SYS.</span><span class="sxs-lookup"><span data-stu-id="77308-103">Either more files have been created in the root directory than the operating system permits, or more files have been opened than the number specified in the **files=** setting in your CONFIG.SYS file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="77308-104">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="77308-104">To correct this error</span></span>  
  
1. <span data-ttu-id="77308-105">Si el programa está abriendo, cerrando o guardando archivos en el directorio raíz, cambie el programa para que use un subdirectorio.</span><span class="sxs-lookup"><span data-stu-id="77308-105">If your program is opening, closing, or saving files in the root directory, change your program so that it uses a subdirectory.</span></span>  
  
2. <span data-ttu-id="77308-106">Aumente el número de archivos especificados en la configuración de **archivos =** en su configuración. SYS y reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="77308-106">Increase the number of files specified in your **files=** setting in your CONFIG.SYS file, and restart your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77308-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="77308-107">See also</span></span>

- [<span data-ttu-id="77308-108">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="77308-108">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
