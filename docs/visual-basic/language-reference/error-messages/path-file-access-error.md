---
description: 'Más información acerca de: error de acceso a un archivo o ruta'
title: Error de acceso a la ruta o al archivo
ms.date: 07/20/2015
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
ms.openlocfilehash: d4fc7e716f025c0a482ab414f4a25a2b521634e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795448"
---
# <a name="pathfile-access-error"></a><span data-ttu-id="ba625-103">Error de acceso a la ruta o al archivo</span><span class="sxs-lookup"><span data-stu-id="ba625-103">Path/File access error</span></span>

<span data-ttu-id="ba625-104">Durante una operación de acceso a archivos o de acceso al disco, el sistema operativo no pudo establecer una conexión entre la ruta de acceso y el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="ba625-104">During a file-access or disk-access operation, the operating system could not make a connection between the path and the file name.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ba625-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ba625-105">To correct this error</span></span>  
  
1. <span data-ttu-id="ba625-106">Asegúrese de que la especificación del archivo tiene el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="ba625-106">Make sure the file specification is correctly formatted.</span></span> <span data-ttu-id="ba625-107">Un nombre de archivo puede contener una ruta de acceso completa (absoluta) o relativa.</span><span class="sxs-lookup"><span data-stu-id="ba625-107">A file name can contain a fully qualified (absolute) or relative path.</span></span> <span data-ttu-id="ba625-108">Una ruta de acceso completa comienza con el nombre de la unidad (si la ruta de acceso está en otra unidad) y muestra la ruta de acceso explícita de la raíz al archivo.</span><span class="sxs-lookup"><span data-stu-id="ba625-108">A fully qualified path starts with the drive name (if the path is on another drive) and lists the explicit path from the root to the file.</span></span> <span data-ttu-id="ba625-109">Cualquier ruta de acceso que no sea completa es relativa a la unidad y el directorio actuales.</span><span class="sxs-lookup"><span data-stu-id="ba625-109">Any path that is not fully qualified is relative to the current drive and directory.</span></span>  
  
2. <span data-ttu-id="ba625-110">Asegúrese de que no ha intentado guardar un archivo que reemplazaría un archivo de solo lectura existente.</span><span class="sxs-lookup"><span data-stu-id="ba625-110">Make sure that you did not attempt to save a file that would replace an existing read-only file.</span></span> <span data-ttu-id="ba625-111">Si es así, cambie el atributo de solo lectura del archivo de destino o guarde el archivo con un nombre de archivo diferente.</span><span class="sxs-lookup"><span data-stu-id="ba625-111">If this is the case, change the read-only attribute of the target file, or save the file with a different file name.</span></span>  
  
3. <span data-ttu-id="ba625-112">Asegúrese de que no ha intentado abrir un archivo de solo lectura en modo secuencial `Output` o `Append` .</span><span class="sxs-lookup"><span data-stu-id="ba625-112">Make sure you did not attempt to open a read-only file in sequential `Output` or `Append` mode.</span></span> <span data-ttu-id="ba625-113">Si es así, abra el archivo en `Input` modo o cambie el atributo de solo lectura del archivo.</span><span class="sxs-lookup"><span data-stu-id="ba625-113">If this is the case, open the file in `Input` mode or change the read-only attribute of the file.</span></span>  
  
4. <span data-ttu-id="ba625-114">Asegúrese de que no ha intentado cambiar un proyecto de Visual Basic en una base de datos o un documento.</span><span class="sxs-lookup"><span data-stu-id="ba625-114">Make sure you did not attempt to change a Visual Basic project within a database or document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba625-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba625-115">See also</span></span>

- [<span data-ttu-id="ba625-116">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="ba625-116">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
