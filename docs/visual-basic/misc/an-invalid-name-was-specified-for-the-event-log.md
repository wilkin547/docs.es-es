---
title: Se ha especificado un valor no válido para el registro de eventos.
ms.date: 07/20/2015
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
ms.openlocfilehash: 36e2bc91a671a22e808d0e30e292471729b1e50b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91083883"
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a><span data-ttu-id="6bf21-102">Se ha especificado un valor no válido para el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="6bf21-102">An invalid name was specified for the event log</span></span>

<span data-ttu-id="6bf21-103">Se ha especificado un valor no válido para el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="6bf21-103">An invalid name was specified for the event log.</span></span> <span data-ttu-id="6bf21-104">Normalmente, se genera por caracteres no válidos en el nombre, un nombre de archivo en blanco o un nombre de archivo es demasiado largo.</span><span class="sxs-lookup"><span data-stu-id="6bf21-104">Usually this is a result of invalid characters in the name, a blank file name, or a file name that is too long.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6bf21-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="6bf21-105">To correct this error</span></span>  
  
- <span data-ttu-id="6bf21-106">Si el nombre especificado tiene más de ocho caracteres, asegúrese de que no haya ningún conflicto con los nombres de otros registros de eventos.</span><span class="sxs-lookup"><span data-stu-id="6bf21-106">If the specified name is more than eight characters, make sure there is no conflict with the names of other event logs.</span></span> <span data-ttu-id="6bf21-107">Al determinar si el nombre es único, se evalúan solo los primeros ocho caracteres.</span><span class="sxs-lookup"><span data-stu-id="6bf21-107">Only the first eight characters are evaluated when determining if the name is unique.</span></span>  
  
- <span data-ttu-id="6bf21-108">Si se proporciona una ruta de acceso, asegúrese de que se analiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="6bf21-108">If supplying a path, make sure it is parsed correctly.</span></span>  
  
- <span data-ttu-id="6bf21-109">Compruebe que no hay ningún carácter no válido en el nombre.</span><span class="sxs-lookup"><span data-stu-id="6bf21-109">Check that there are no invalid characters in the name.</span></span> <span data-ttu-id="6bf21-110">Los caracteres que no se pueden usar en un nombre de archivo incluyen `<`, `>`, `:`, `"`, `/`, `\`y `|`.</span><span class="sxs-lookup"><span data-stu-id="6bf21-110">Characters that cannot be used in a file name include `<`, `>`, `:`, `"`, `/`, `\`, and `|`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bf21-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bf21-111">See also</span></span>

- [<span data-ttu-id="6bf21-112">Procedimiento para analizar rutas de acceso a archivos</span><span class="sxs-lookup"><span data-stu-id="6bf21-112">How to: Parse File Paths</span></span>](../developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
- [<span data-ttu-id="6bf21-113">Procedimiento para cambiar el nombre de un archivo</span><span class="sxs-lookup"><span data-stu-id="6bf21-113">How to: Rename a File</span></span>](../developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
