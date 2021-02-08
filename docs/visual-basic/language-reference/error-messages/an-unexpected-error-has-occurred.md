---
description: 'Más información acerca de: se ha producido un error inesperado porque no se puede adquirir un recurso del sistema operativo necesario para el inicio de una sola instancia'
title: Error inesperado porque no se puede conseguir un recurso del sistema operativo necesario para el inicio de una instancia única
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_CantGetMemoryMappedFile
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
ms.openlocfilehash: 43ac84e053def32cd5fa0dfc798bd47a022c0471
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797177"
---
# <a name="an-unexpected-error-has-occurred-because-an-operating-system-resource-required-for-single-instance-startup-cannot-be-acquired"></a><span data-ttu-id="6f7be-103">Error inesperado porque no se puede conseguir un recurso del sistema operativo necesario para el inicio de una instancia única</span><span class="sxs-lookup"><span data-stu-id="6f7be-103">An unexpected error has occurred because an operating system resource required for single instance startup cannot be acquired</span></span>

<span data-ttu-id="6f7be-104">La aplicación no pudo obtener un recurso de sistema operativo necesario.</span><span class="sxs-lookup"><span data-stu-id="6f7be-104">The application could not acquire a necessary operating system resource.</span></span> <span data-ttu-id="6f7be-105">Algunas de las posibles causas de este problema son:</span><span class="sxs-lookup"><span data-stu-id="6f7be-105">Some of the possible causes for this problem are:</span></span>  
  
- <span data-ttu-id="6f7be-106">La aplicación no tiene permisos para crear objetos de sistema operativo con nombre.</span><span class="sxs-lookup"><span data-stu-id="6f7be-106">The application does not have permissions to create named operating-system objects.</span></span>  
  
- <span data-ttu-id="6f7be-107">Common Language Runtime no tiene permisos para crear archivos asignados a memoria.</span><span class="sxs-lookup"><span data-stu-id="6f7be-107">The common language runtime does not have permissions to create memory-mapped files.</span></span>  
  
- <span data-ttu-id="6f7be-108">La aplicación necesita acceder a un objeto de sistema operativo, pero hay otro proceso que lo está utilizando.</span><span class="sxs-lookup"><span data-stu-id="6f7be-108">The application needs to access an operating-system object, but another process is using it.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6f7be-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="6f7be-109">To correct this error</span></span>  
  
1. <span data-ttu-id="6f7be-110">Confirme que la aplicación tiene permisos suficientes para crear objetos de sistema operativo con nombre.</span><span class="sxs-lookup"><span data-stu-id="6f7be-110">Check that the application has sufficient permissions to create named operating-system objects.</span></span>  
  
2. <span data-ttu-id="6f7be-111">Confirme que Common Language Runtime tiene permisos suficientes para crear archivos asignados a memoria.</span><span class="sxs-lookup"><span data-stu-id="6f7be-111">Check that the common language runtime has sufficient permissions to create memory-mapped files.</span></span>  
  
3. <span data-ttu-id="6f7be-112">Reinicie el equipo para borrar cualquier proceso que pueda estar haciendo uso del recurso necesario para conectarse a la aplicación de instancia original.</span><span class="sxs-lookup"><span data-stu-id="6f7be-112">Restart the computer to clear any process that may be using the resource needed to connect to the original instance application.</span></span>  
  
4. <span data-ttu-id="6f7be-113">Anote las circunstancias en las que se ha produjo el error y llame a los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6f7be-113">Note the circumstances under which the error occurred, and call Microsoft Product Support Services</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f7be-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6f7be-114">See also</span></span>

- [<span data-ttu-id="6f7be-115">Página de aplicación, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f7be-115">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="6f7be-116">Conceptos básicos del depurador</span><span class="sxs-lookup"><span data-stu-id="6f7be-116">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)
- [<span data-ttu-id="6f7be-117">Hable con nosotros</span><span class="sxs-lookup"><span data-stu-id="6f7be-117">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
