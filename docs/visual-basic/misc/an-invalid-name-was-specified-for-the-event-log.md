---
title: Se ha especificado un valor no válido para el registro de eventos.
ms.date: 07/20/2015
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
ms.openlocfilehash: 2b9c934272d0f3392c845dcd2f0062a98dc50c7b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940678"
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a><span data-ttu-id="cb93f-102">Se ha especificado un valor no válido para el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="cb93f-102">An invalid name was specified for the event log</span></span>
<span data-ttu-id="cb93f-103">Se ha especificado un valor no válido para el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="cb93f-103">An invalid name was specified for the event log.</span></span> <span data-ttu-id="cb93f-104">Normalmente, se genera por caracteres no válidos en el nombre, un nombre de archivo en blanco o un nombre de archivo es demasiado largo.</span><span class="sxs-lookup"><span data-stu-id="cb93f-104">Usually this is a result of invalid characters in the name, a blank file name, or a file name that is too long.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cb93f-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="cb93f-105">To correct this error</span></span>  
  
- <span data-ttu-id="cb93f-106">Si el nombre especificado tiene más de ocho caracteres, asegúrese de que no haya ningún conflicto con los nombres de otros registros de eventos.</span><span class="sxs-lookup"><span data-stu-id="cb93f-106">If the specified name is more than eight characters, make sure there is no conflict with the names of other event logs.</span></span> <span data-ttu-id="cb93f-107">Al determinar si el nombre es único, se evalúan solo los primeros ocho caracteres.</span><span class="sxs-lookup"><span data-stu-id="cb93f-107">Only the first eight characters are evaluated when determining if the name is unique.</span></span>  
  
- <span data-ttu-id="cb93f-108">Si se proporciona una ruta de acceso, asegúrese de que se analiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="cb93f-108">If supplying a path, make sure it is parsed correctly.</span></span>  
  
- <span data-ttu-id="cb93f-109">Compruebe que no hay ningún carácter no válido en el nombre.</span><span class="sxs-lookup"><span data-stu-id="cb93f-109">Check that there are no invalid characters in the name.</span></span> <span data-ttu-id="cb93f-110">Los caracteres que no se pueden usar en un nombre de archivo incluyen `<`, `>`, `:`, `"`, `/`, `\`y `|`.</span><span class="sxs-lookup"><span data-stu-id="cb93f-110">Characters that cannot be used in a file name include `<`, `>`, `:`, `"`, `/`, `\`, and `|`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb93f-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb93f-111">See also</span></span>

- [<span data-ttu-id="cb93f-112">Cómo: Analizar rutas de acceso a archivos</span><span class="sxs-lookup"><span data-stu-id="cb93f-112">How to: Parse File Paths</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
- [<span data-ttu-id="cb93f-113">Cómo: Cambiar el nombre de un archivo</span><span class="sxs-lookup"><span data-stu-id="cb93f-113">How to: Rename a File</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
