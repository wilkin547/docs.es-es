---
title: Desarrollo con My (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MyWpfExtension.Windows
helpviewer_keywords:
- My object
- My namespace
- My feature
- Visual Basic, programming in
ms.assetid: f1d04509-5e46-4551-9f9f-94334a121fca
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2cf51e1f6292a61c071fe6d92f5fcbce4be84ff4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="development-with-my-visual-basic"></a><span data-ttu-id="911c1-102">Desarrollo con My (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="911c1-102">Development with My (Visual Basic)</span></span>
<span data-ttu-id="911c1-103">Visual Basic ofrece nuevas características para el desarrollo rápido de aplicaciones que mejoran la productividad y la facilidad de uso con la máxima eficacia.</span><span class="sxs-lookup"><span data-stu-id="911c1-103">Visual Basic provides new features for rapid application development that improve productivity and ease of use while delivering power.</span></span> <span data-ttu-id="911c1-104">Una de estas funciones, `My`, proporciona acceso a información y a las instancias de objetos predeterminados relacionados con la aplicación y su entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="911c1-104">One of these features, called `My`, provides access to information and default object instances that are related to the application and its run-time environment.</span></span> <span data-ttu-id="911c1-105">Esta información está organizada en un formato que se descubre mediante IntelliSense y se define lógicamente según su uso.</span><span class="sxs-lookup"><span data-stu-id="911c1-105">This information is organized in a format that is discoverable through IntelliSense and logically delineated according to use.</span></span>  
  
 <span data-ttu-id="911c1-106">Los miembros de nivel superior de `My` se exponen como objetos.</span><span class="sxs-lookup"><span data-stu-id="911c1-106">Top-level members of `My` are exposed as objects.</span></span> <span data-ttu-id="911c1-107">Cada objeto se comporta de forma similar a un espacio de nombres o una clase con miembros `Shared` y expone un conjunto de miembros relacionados.</span><span class="sxs-lookup"><span data-stu-id="911c1-107">Each object behaves similarly to a namespace or a class with `Shared` members, and it exposes a set of related members.</span></span>  
  
 <span data-ttu-id="911c1-108">Esta tabla muestra los objetos `My` de nivel superior y sus relaciones entre sí.</span><span class="sxs-lookup"><span data-stu-id="911c1-108">This table shows the top-level `My` objects and their relationship to each other.</span></span>  
  
 <span data-ttu-id="911c1-109">![Modelo de objeto para My](../../../visual-basic/developing-apps/development-with-my/media/myobjmodel.gif "MyObjModel")</span><span class="sxs-lookup"><span data-stu-id="911c1-109">![Object Model for My](../../../visual-basic/developing-apps/development-with-my/media/myobjmodel.gif "MyObjModel")</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="911c1-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="911c1-110">In This Section</span></span>  
 [<span data-ttu-id="911c1-111">Realizacion de tareas con My.Application, My.Computer y My.User</span><span class="sxs-lookup"><span data-stu-id="911c1-111">Performing Tasks with My.Application, My.Computer, and My.User</span></span>](../../../visual-basic/developing-apps/development-with-my/performing-tasks-with-my-application-my-computer-and-my-user.md)  
 <span data-ttu-id="911c1-112">Describe los tres objetos principales `My`, a saber, `My.Application`, `My.Computer` y `My.User`, que proporcionan acceso a información y funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="911c1-112">Describes the three central `My` objects, `My.Application`, `My.Computer`, and `My.User`, which provide access to information and functionality</span></span>  
  
 [<span data-ttu-id="911c1-113">Instancias de objeto predeterminadas proporcionadas por My.Forms y My.WebServices</span><span class="sxs-lookup"><span data-stu-id="911c1-113">Default Object Instances Provided by My.Forms and My.WebServices</span></span>](../../../visual-basic/developing-apps/development-with-my/default-object-instances-provided-by-my-forms-and-my-webservices.md)  
 <span data-ttu-id="911c1-114">Describe los objetos `My.Forms` y `My.WebServices`, que proporcionan acceso a formularios, orígenes de datos y servicios web XML utilizados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="911c1-114">Describes the `My.Forms` and `My.WebServices` objects, which provide access to forms, data sources, and XML Web services used by your application.</span></span>  
  
 [<span data-ttu-id="911c1-115">Desarrollo rápido de aplicaciones con My.Resources y My.Settings</span><span class="sxs-lookup"><span data-stu-id="911c1-115">Rapid Application Development with My.Resources and My.Settings</span></span>](../../../visual-basic/developing-apps/development-with-my/rapid-application-development-with-my-resources-and-my-settings.md)  
 <span data-ttu-id="911c1-116">Describe los objetos `My.Resources` y `My.Settings`, que proporcionan acceso a la configuración y los recursos de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="911c1-116">Describes the `My.Resources` and `My.Settings` objects, which provide access to an application's resources and settings.</span></span>  
  
 [<span data-ttu-id="911c1-117">Información general sobre el modelo de aplicaciones de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="911c1-117">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)  
 <span data-ttu-id="911c1-118">Describe el modelo de inicio y parada de la aplicación [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="911c1-118">Describes the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Application Startup/Shutdown model.</span></span>  
  
 [<span data-ttu-id="911c1-119">Cómo My depende del tipo de proyecto</span><span class="sxs-lookup"><span data-stu-id="911c1-119">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)  
 <span data-ttu-id="911c1-120">Proporciona información detallada sobre las características `My` disponibles en diferentes tipos de proyectos.</span><span class="sxs-lookup"><span data-stu-id="911c1-120">Gives details on which `My` features are available in different project types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="911c1-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="911c1-121">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [<span data-ttu-id="911c1-122">My.Forms (objeto)</span><span class="sxs-lookup"><span data-stu-id="911c1-122">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [<span data-ttu-id="911c1-123">My.WebServices (objeto)</span><span class="sxs-lookup"><span data-stu-id="911c1-123">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)  
 [<span data-ttu-id="911c1-124">Cómo My depende del tipo de proyecto</span><span class="sxs-lookup"><span data-stu-id="911c1-124">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
