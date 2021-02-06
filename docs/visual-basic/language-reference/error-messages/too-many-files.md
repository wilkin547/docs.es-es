---
description: 'Más información acerca de: demasiados archivos'
title: Demasiados archivos
ms.date: 07/20/2015
f1_keywords:
- vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
ms.openlocfilehash: 85d246c49f765cf618bf889d75dcc9c10b780280
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641231"
---
# <a name="too-many-files"></a><span data-ttu-id="c9c57-103">Demasiados archivos</span><span class="sxs-lookup"><span data-stu-id="c9c57-103">Too many files</span></span>

<span data-ttu-id="c9c57-104">Se han creado más archivos en el directorio raíz que los que permite el sistema operativo, o se han abierto más archivos que el número especificado en la configuración **archivos =** en el archivo de CONFIG.SYS.</span><span class="sxs-lookup"><span data-stu-id="c9c57-104">Either more files have been created in the root directory than the operating system permits, or more files have been opened than the number specified in the **files=** setting in your CONFIG.SYS file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c9c57-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="c9c57-105">To correct this error</span></span>  
  
1. <span data-ttu-id="c9c57-106">Si el programa está abriendo, cerrando o guardando archivos en el directorio raíz, cambie el programa para que use un subdirectorio.</span><span class="sxs-lookup"><span data-stu-id="c9c57-106">If your program is opening, closing, or saving files in the root directory, change your program so that it uses a subdirectory.</span></span>  
  
2. <span data-ttu-id="c9c57-107">Aumente el número de archivos especificados en la configuración de **archivos =** en el archivo de CONFIG.SYS y reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="c9c57-107">Increase the number of files specified in your **files=** setting in your CONFIG.SYS file, and restart your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9c57-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9c57-108">See also</span></span>

- [<span data-ttu-id="c9c57-109">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="c9c57-109">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
