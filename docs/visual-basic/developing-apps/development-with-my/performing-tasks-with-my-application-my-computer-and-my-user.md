---
title: Realizar tareas con My.Application, My.Computer y My.User (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: bc2b0521598c00cdb398d936d61d65874a9cf274
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583401"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a><span data-ttu-id="f34b9-102">Realizar tareas con My.Application, My.Computer y My.User (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f34b9-102">Performing Tasks with My.Application, My.Computer, and My.User (Visual Basic)</span></span>
<span data-ttu-id="f34b9-103">El centro de tres `My` son objetos que proporcionan acceso a la información y normalmente funcionalidad `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), y `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span><span class="sxs-lookup"><span data-stu-id="f34b9-103">The three central `My` objects that provide access to information and commonly used functionality are `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), and `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span></span> <span data-ttu-id="f34b9-104">Estos objetos se pueden utilizar para tener acceso a información que está relacionado con la aplicación actual, el equipo que se instala la aplicación en o el usuario actual de la aplicación, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="f34b9-104">You can use these objects to access information that is related to the current application, the computer that the application is installed on, or the current user of the application, respectively.</span></span>  
  
## <a name="myapplication-mycomputer-and-myuser"></a><span data-ttu-id="f34b9-105">My.Application, My.Computer y My.User</span><span class="sxs-lookup"><span data-stu-id="f34b9-105">My.Application, My.Computer, and My.User</span></span>  
 <span data-ttu-id="f34b9-106">Los ejemplos siguientes muestran cómo información se puede recuperar mediante `My`.</span><span class="sxs-lookup"><span data-stu-id="f34b9-106">The following examples demonstrate how information can be retrieved using `My`.</span></span>  
  
 [!code-vb[VbVbcnMy#1](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_1.vb)]  
  
 [!code-vb[VbVbcnMy#2](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_2.vb)]  
  
 <span data-ttu-id="f34b9-107">Además de la información de recuperación, los miembros expuestos a través de estos tres objetos también permiten ejecutar métodos relacionados con ese objeto.</span><span class="sxs-lookup"><span data-stu-id="f34b9-107">In addition to retrieving information, the members exposed through these three objects also allow you to execute methods related to that object.</span></span> <span data-ttu-id="f34b9-108">Por ejemplo, puede tener acceso a una variedad de métodos para manipular archivos o actualizar el registro a través de `My.Computer`.</span><span class="sxs-lookup"><span data-stu-id="f34b9-108">For instance, you can access a variety of methods to manipulate files or update the registry through `My.Computer`.</span></span>  
  
 <span data-ttu-id="f34b9-109">E/S de archivos es mucho más fácil y rápido con `My`, que incluye una serie de métodos y propiedades para manipular archivos, directorios y unidades.</span><span class="sxs-lookup"><span data-stu-id="f34b9-109">File I/O is significantly easier and faster with `My`, which includes a variety of methods and properties for manipulating files, directories, and drives.</span></span> <span data-ttu-id="f34b9-110">La <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> objeto le permite leer de archivos estructurados grandes delimitados o campos de ancho fijo.</span><span class="sxs-lookup"><span data-stu-id="f34b9-110">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object allows you to read from large structured files that have delimited or fixed-width fields.</span></span> <span data-ttu-id="f34b9-111">En este ejemplo se abre la `TextFieldParser``reader` y se utiliza para leer de `C:\TestFolder1\test1.txt`.</span><span class="sxs-lookup"><span data-stu-id="f34b9-111">This example opens the `TextFieldParser``reader` and uses it to read from `C:\TestFolder1\test1.txt`.</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#23](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_3.vb)]  
  
 <span data-ttu-id="f34b9-112">`My.Application` permite cambiar la referencia cultural para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f34b9-112">`My.Application` allows you to change the culture for your application.</span></span> <span data-ttu-id="f34b9-113">En el ejemplo siguiente se muestra cómo se puede llamar a este método.</span><span class="sxs-lookup"><span data-stu-id="f34b9-113">The following example demonstrates how this method can be called.</span></span>  
  
 [!code-vb[VbVbcnMy#3](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f34b9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f34b9-114">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [<span data-ttu-id="f34b9-115">Cómo My depende del tipo de proyecto</span><span class="sxs-lookup"><span data-stu-id="f34b9-115">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
