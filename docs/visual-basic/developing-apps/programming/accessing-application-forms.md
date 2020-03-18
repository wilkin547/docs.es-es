---
title: Acceso a los formularios de las aplicaciones
ms.date: 07/20/2015
helpviewer_keywords:
- forms [Visual Basic], communicating between
- application forms [Visual Basic], accessing
- forms [Visual Basic], accessing one from another
- My.Forms object
- forms [Visual Basic], accessing all open
ms.assetid: 9aaf5aaf-2012-4f97-89c7-6e62b9d17863
ms.openlocfilehash: 332b6a7563160528b6c17210170af0db6e9bc0e7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74349238"
---
# <a name="accessing-application-forms-visual-basic"></a><span data-ttu-id="54d13-102">Acceso a los formularios de aplicaciones (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54d13-102">Accessing Application Forms (Visual Basic)</span></span>

<span data-ttu-id="54d13-103">El objeto `My.Forms` proporciona una manera fácil de tener acceso a una instancia de cada Windows Form declarado en el proyecto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="54d13-103">The `My.Forms` object provides an easy way to access an instance of each Windows Form declared in the application's project.</span></span> <span data-ttu-id="54d13-104">También puede usar propiedades del objeto `My.Application` para tener acceso a la pantalla de presentación y el formulario principal de la aplicación y para obtener una lista de los formularios abiertos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="54d13-104">You can also use properties of the `My.Application` object to access the application's splash screen and main form, and get a list of the application's open forms.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="54d13-105">Tareas</span><span class="sxs-lookup"><span data-stu-id="54d13-105">Tasks</span></span>  

 <span data-ttu-id="54d13-106">En la siguiente tabla se incluyen ejemplos que muestran cómo acceder a los formularios de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="54d13-106">The following table lists examples showing how to access an application's forms.</span></span>  
  
|<span data-ttu-id="54d13-107">Para</span><span class="sxs-lookup"><span data-stu-id="54d13-107">To</span></span>|<span data-ttu-id="54d13-108">Vea</span><span class="sxs-lookup"><span data-stu-id="54d13-108">See</span></span>|  
|---|---|  
|<span data-ttu-id="54d13-109">Tener acceso a un formulario desde otro formulario de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="54d13-109">Access one form from another form in an application.</span></span>|[<span data-ttu-id="54d13-110">My.Forms (objeto)</span><span class="sxs-lookup"><span data-stu-id="54d13-110">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)|  
|<span data-ttu-id="54d13-111">Mostrar los títulos de todos los formularios abiertos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="54d13-111">Display the titles of all the application's open forms.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>|  
|<span data-ttu-id="54d13-112">Actualizar la pantalla de presentación con información de estado como los inicios de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="54d13-112">Update the splash screen with status information as the application starts.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="54d13-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="54d13-113">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>
- [<span data-ttu-id="54d13-114">My.Forms (objeto)</span><span class="sxs-lookup"><span data-stu-id="54d13-114">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)
