---
title: Implementación de aplicaciones que hacen referencia a controles Power Packs (Visual Studio)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Power Packs, deploying
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9d73c7111c3d89cadcad317c9a67e5f483da7125
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="deploying-applications-that-reference-power-packs-controls-visual-studio"></a><span data-ttu-id="7b3f5-102">Implementación de aplicaciones que hacen referencia a controles Power Packs (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="7b3f5-102">Deploying applications that reference Power Packs controls (Visual Studio)</span></span>
<span data-ttu-id="7b3f5-103">Si va a implementar una aplicación que hace referencia a los controles Power Packs (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, o <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), los controles deben instalarse en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-103">If you want to deploy an application that references the Power Packs controls (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, or <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), the controls must be installed on the destination computer.</span></span>  
  
## <a name="installing-the-power-packs-controls-as-a-prerequisite"></a><span data-ttu-id="7b3f5-104">Instalación de los controles Power Packs como requisito previo</span><span class="sxs-lookup"><span data-stu-id="7b3f5-104">Installing the Power Packs controls as a prerequisite</span></span>  
 <span data-ttu-id="7b3f5-105">Para implementar correctamente una aplicación, también debe implementar todos los componentes a los que hace referencia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-105">To successfully deploy an application, you must also deploy all components that are referenced by the application.</span></span> <span data-ttu-id="7b3f5-106">El proceso de instalación de componentes de requisito previo se conoce como *arranque*.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-106">The process of installing prerequisite components is known as *bootstrapping*.</span></span>  
  
 <span data-ttu-id="7b3f5-107">Cuando Visual Studio está instalado en el equipo de desarrollo, se agrega un paquete de programa previo de los Power Packs en el directorio de programa previo de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-107">When Visual Studio is installed on your development computer, a Power Packs bootstrapper package is added to the Visual Studio bootstrapper directory.</span></span> <span data-ttu-id="7b3f5-108">Este paquete está disponible al seguir los procedimientos para agregar requisitos previos para cualquier implementación de [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] o Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-108">This package is then available when you follow the procedures for adding prerequisites for either [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] or Windows Installer deployment.</span></span>  
  
 <span data-ttu-id="7b3f5-109">De forma predeterminada, los componentes de arranque se implementan desde la misma ubicación que el paquete de instalación.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-109">By default, bootstrapped components are deployed from the same location as the installation package.</span></span> <span data-ttu-id="7b3f5-110">Como alternativa, puede implementar los componentes desde una dirección URL o una ubicación de recurso compartido de archivo desde la que los usuarios pueden descargarlos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-110">Alternatively, you can choose to deploy the components from a URL or file share location from which users can download them as necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b3f5-111">Para instalar los componentes de arranque, el usuario podría necesitar permisos de usuario administrativo o similares en el equipo.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-111">To install bootstrapped components, the user might need administrative or similar user permissions on the computer.</span></span> <span data-ttu-id="7b3f5-112">Para las aplicaciones [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] , esto significa que el usuario necesitará permisos administrativos para instalar la aplicación, independientemente del nivel de seguridad especificado por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-112">For [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] applications, this means that the user will need administrative permissions to install the application, regardless of the security level specified by the application.</span></span> <span data-ttu-id="7b3f5-113">Una vez instalada la aplicación, el usuario puede ejecutarla sin permisos administrativos.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-113">After the application is installed, the user can run the application without administrative permissions.</span></span>  
  
 <span data-ttu-id="7b3f5-114">Durante la instalación, los usuarios se le pedirá que instale los controles Power Packs si no están presentes en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-114">During installation, users will be prompted to install the Power Packs controls if they are not present on the destination computer.</span></span>  
  
 <span data-ttu-id="7b3f5-115">Como alternativa al arranque, puede implementar previamente los controles Power Packs mediante un sistema de distribución electrónica de software como Microsoft Systems Management Server.</span><span class="sxs-lookup"><span data-stu-id="7b3f5-115">As an alternative to bootstrapping, you can pre-deploy the Power Packs controls by using an electronic software distribution system such as Microsoft Systems Management Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b3f5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b3f5-116">See also</span></span>  
 [<span data-ttu-id="7b3f5-117">Cómo: Instalar requisitos previos mediante una aplicación ClickOnce</span><span class="sxs-lookup"><span data-stu-id="7b3f5-117">How to: Install Prerequisites with a ClickOnce Application</span></span>](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)  
 [<span data-ttu-id="7b3f5-118">Controles de Power Packs de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7b3f5-118">Visual Basic Power Packs Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)
