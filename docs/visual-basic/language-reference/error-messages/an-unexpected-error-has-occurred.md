---
title: Error inesperado porque no se puede conseguir un recurso del sistema operativo necesario para el inicio de una instancia única
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_CantGetMemoryMappedFile
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
ms.openlocfilehash: 9aa7ba0babe0a89942e320a76e07c05162b31700
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59313617"
---
# <a name="an-unexpected-error-has-occurred-because-an-operating-system-resource-required-for-single-instance-startup-cannot-be-acquired"></a><span data-ttu-id="d4391-102">Error inesperado porque no se puede conseguir un recurso del sistema operativo necesario para el inicio de una instancia única</span><span class="sxs-lookup"><span data-stu-id="d4391-102">An unexpected error has occurred because an operating system resource required for single instance startup cannot be acquired</span></span>
<span data-ttu-id="d4391-103">La aplicación no pudo obtener un recurso de sistema operativo necesario.</span><span class="sxs-lookup"><span data-stu-id="d4391-103">The application could not acquire a necessary operating system resource.</span></span> <span data-ttu-id="d4391-104">Algunas de las posibles causas de este problema son:</span><span class="sxs-lookup"><span data-stu-id="d4391-104">Some of the possible causes for this problem are:</span></span>  
  
-   <span data-ttu-id="d4391-105">La aplicación no tiene permisos para crear objetos de sistema operativo con nombre.</span><span class="sxs-lookup"><span data-stu-id="d4391-105">The application does not have permissions to create named operating-system objects.</span></span>  
  
-   <span data-ttu-id="d4391-106">Common Language Runtime no tiene permisos para crear archivos asignados a memoria.</span><span class="sxs-lookup"><span data-stu-id="d4391-106">The common language runtime does not have permissions to create memory-mapped files.</span></span>  
  
-   <span data-ttu-id="d4391-107">La aplicación necesita acceder a un objeto de sistema operativo, pero hay otro proceso que lo está utilizando.</span><span class="sxs-lookup"><span data-stu-id="d4391-107">The application needs to access an operating-system object, but another process is using it.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d4391-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d4391-108">To correct this error</span></span>  
  
1. <span data-ttu-id="d4391-109">Confirme que la aplicación tiene permisos suficientes para crear objetos de sistema operativo con nombre.</span><span class="sxs-lookup"><span data-stu-id="d4391-109">Check that the application has sufficient permissions to create named operating-system objects.</span></span>  
  
2. <span data-ttu-id="d4391-110">Confirme que Common Language Runtime tiene permisos suficientes para crear archivos asignados a memoria.</span><span class="sxs-lookup"><span data-stu-id="d4391-110">Check that the common language runtime has sufficient permissions to create memory-mapped files.</span></span>  
  
3. <span data-ttu-id="d4391-111">Reinicie el equipo para borrar cualquier proceso que pueda estar haciendo uso del recurso necesario para conectarse a la aplicación de instancia original.</span><span class="sxs-lookup"><span data-stu-id="d4391-111">Restart the computer to clear any process that may be using the resource needed to connect to the original instance application.</span></span>  
  
4. <span data-ttu-id="d4391-112">Anote las circunstancias en las que se ha produjo el error y llame a los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d4391-112">Note the circumstances under which the error occurred, and call Microsoft Product Support Services</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4391-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4391-113">See also</span></span>

- [<span data-ttu-id="d4391-114">Página de aplicación, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4391-114">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="d4391-115">Conceptos básicos del depurador</span><span class="sxs-lookup"><span data-stu-id="d4391-115">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)
- [<span data-ttu-id="d4391-116">Hable con nosotros</span><span class="sxs-lookup"><span data-stu-id="d4391-116">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
