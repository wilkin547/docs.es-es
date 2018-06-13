---
title: Error de acceso al archivo de la ruta de acceso
ms.date: 07/20/2015
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
ms.openlocfilehash: 83ce8615b173a6f5835347ebc561a793655ec8f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598588"
---
# <a name="pathfile-access-error"></a><span data-ttu-id="03a51-102">Error de acceso a la ruta o al archivo</span><span class="sxs-lookup"><span data-stu-id="03a51-102">Path/File access error</span></span>
<span data-ttu-id="03a51-103">Durante una operación de acceso a archivos o acceso al disco, el sistema operativo no pudo realizar una conexión entre la ruta de acceso y el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="03a51-103">During a file-access or disk-access operation, the operating system could not make a connection between the path and the file name.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="03a51-104">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="03a51-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="03a51-105">Asegúrese de que la especificación de archivo tiene el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="03a51-105">Make sure the file specification is correctly formatted.</span></span> <span data-ttu-id="03a51-106">Un nombre de archivo puede contener un acceso completa (absoluta) o relativa ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="03a51-106">A file name can contain a fully qualified (absolute) or relative path.</span></span> <span data-ttu-id="03a51-107">Ruta de acceso completa se inicia con el nombre de unidad (si la ruta de acceso está en otra unidad) y muestra la ruta de acceso explícita desde la raíz en el archivo.</span><span class="sxs-lookup"><span data-stu-id="03a51-107">A fully qualified path starts with the drive name (if the path is on another drive) and lists the explicit path from the root to the file.</span></span> <span data-ttu-id="03a51-108">Cualquier ruta de acceso que no es un nombre completo es relativa a la unidad actual y el directorio.</span><span class="sxs-lookup"><span data-stu-id="03a51-108">Any path that is not fully qualified is relative to the current drive and directory.</span></span>  
  
2.  <span data-ttu-id="03a51-109">Asegúrese de que no ha intentado guardar un archivo que reemplaza un archivo de sólo lectura existente.</span><span class="sxs-lookup"><span data-stu-id="03a51-109">Make sure that you did not attempt to save a file that would replace an existing read-only file.</span></span> <span data-ttu-id="03a51-110">Si este es el caso, cambie el atributo de sólo lectura del archivo de destino o guarde el archivo con un nombre de archivo diferente.</span><span class="sxs-lookup"><span data-stu-id="03a51-110">If this is the case, change the read-only attribute of the target file, or save the file with a different file name.</span></span>  
  
3.  <span data-ttu-id="03a51-111">Asegúrese de que no ha intentado abrir un archivo de solo lectura en secuencial `Output` o `Append` modo.</span><span class="sxs-lookup"><span data-stu-id="03a51-111">Make sure you did not attempt to open a read-only file in sequential `Output` or `Append` mode.</span></span> <span data-ttu-id="03a51-112">Si este es el caso, abra el archivo en `Input` modo o cambiar el atributo de sólo lectura del archivo.</span><span class="sxs-lookup"><span data-stu-id="03a51-112">If this is the case, open the file in `Input` mode or change the read-only attribute of the file.</span></span>  
  
4.  <span data-ttu-id="03a51-113">Asegúrese de que no intentó cambiar un proyecto de Visual Basic dentro de una base de datos o el documento.</span><span class="sxs-lookup"><span data-stu-id="03a51-113">Make sure you did not attempt to change a Visual Basic project within a database or document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03a51-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="03a51-114">See Also</span></span>  
 [<span data-ttu-id="03a51-115">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="03a51-115">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
