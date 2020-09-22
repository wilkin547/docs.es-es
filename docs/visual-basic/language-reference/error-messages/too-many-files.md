---
title: Demasiados archivos
ms.date: 07/20/2015
f1_keywords:
- vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
ms.openlocfilehash: cd168ce86569d2d7558e21a5b4cc5ef385b28313
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873552"
---
# <a name="too-many-files"></a><span data-ttu-id="20f9b-102">Demasiados archivos</span><span class="sxs-lookup"><span data-stu-id="20f9b-102">Too many files</span></span>

<span data-ttu-id="20f9b-103">Se han creado más archivos en el directorio raíz que los que permite el sistema operativo, o se han abierto más archivos que el número especificado en la configuración **archivos =** en el archivo de CONFIG.SYS.</span><span class="sxs-lookup"><span data-stu-id="20f9b-103">Either more files have been created in the root directory than the operating system permits, or more files have been opened than the number specified in the **files=** setting in your CONFIG.SYS file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="20f9b-104">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="20f9b-104">To correct this error</span></span>  
  
1. <span data-ttu-id="20f9b-105">Si el programa está abriendo, cerrando o guardando archivos en el directorio raíz, cambie el programa para que use un subdirectorio.</span><span class="sxs-lookup"><span data-stu-id="20f9b-105">If your program is opening, closing, or saving files in the root directory, change your program so that it uses a subdirectory.</span></span>  
  
2. <span data-ttu-id="20f9b-106">Aumente el número de archivos especificados en la configuración de **archivos =** en el archivo de CONFIG.SYS y reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="20f9b-106">Increase the number of files specified in your **files=** setting in your CONFIG.SYS file, and restart your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20f9b-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="20f9b-107">See also</span></span>

- [<span data-ttu-id="20f9b-108">Tipos de errores</span><span class="sxs-lookup"><span data-stu-id="20f9b-108">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
