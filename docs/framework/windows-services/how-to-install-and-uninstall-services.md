---
title: "Cómo: Instalar y desinstalar servicios"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, Windows Services
- installation, Windows Services
- uninstalling Windows Services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
caps.latest.revision: "19"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 1fcbc8e7a84b16d244561e0cd69f8661236e63de
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-install-and-uninstall-services"></a><span data-ttu-id="9e55a-102">Cómo: Instalar y desinstalar servicios</span><span class="sxs-lookup"><span data-stu-id="9e55a-102">How to: Install and Uninstall Services</span></span>
<span data-ttu-id="9e55a-103">Si desarrolla un servicio de Windows mediante .NET Framework, puede instalar rápidamente la aplicación de servicio mediante una utilidad de línea de comandos denominada InstallUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="9e55a-103">If you’re developing a Windows Service by using the .NET Framework, you can quickly install your service application by using a command-line utility called InstallUtil.exe.</span></span> <span data-ttu-id="9e55a-104">Si es desarrollador y desea publicar un servicio de Windows que los usuarios puedan instalar y desinstalar, debe usar InstallShield.</span><span class="sxs-lookup"><span data-stu-id="9e55a-104">If you’re a developer who wants to release a Windows Service that users can install and uninstall  you should use InstallShield.</span></span> <span data-ttu-id="9e55a-105">Vea [implementación de Windows Installer](http://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0).</span><span class="sxs-lookup"><span data-stu-id="9e55a-105">See [Windows Installer Deployment](http://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="9e55a-106">Si desea desinstalar un servicio del equipo, no siga los pasos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="9e55a-106">If you want to uninstall a service from your computer, don’t follow the steps in this article.</span></span> <span data-ttu-id="9e55a-107">En su lugar, averigüe qué paquete de software o programa instaló el servicio y, a continuación, elija **agregar o quitar programas** en el Panel de Control para desinstalar el programa.</span><span class="sxs-lookup"><span data-stu-id="9e55a-107">Instead, find out which program or software package installed the service, and then choose **Add/Remove Programs** in Control Panel to uninstall that program.</span></span> <span data-ttu-id="9e55a-108">Tenga en cuenta que muchos servicios forman parte de Windows; si los quita, podría causar inestabilidad en el sistema.</span><span class="sxs-lookup"><span data-stu-id="9e55a-108">Note that many services are integral parts of Windows; if you remove them, you might cause system instability.</span></span>  
  
 <span data-ttu-id="9e55a-109">Para poder seguir los pasos de este artículo, primero debe agregar un instalador del servicio al servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="9e55a-109">In order to use the steps in this article, you first need to add a service installer to your Windows Service.</span></span> <span data-ttu-id="9e55a-110">Vea [Tutorial: crear una ventana de la aplicación en el Diseñador de componentes de servicio](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="9e55a-110">See [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
 <span data-ttu-id="9e55a-111">Los proyectos de servicio de Windows no se pueden ejecutar directamente desde el entorno de desarrollo de Visual Studio presionando F5.</span><span class="sxs-lookup"><span data-stu-id="9e55a-111">Windows Service projects cannot be run directly from the Visual Studio development environment by pressing F5.</span></span> <span data-ttu-id="9e55a-112">Esto es porque el servicio del proyecto debe estar instalado para poder ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="9e55a-112">This is because the service in the project must be installed before you can run the project.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="9e55a-113">Puede iniciar **Explorador de servidores** y compruebe que el servicio se ha instalado o desinstalado.</span><span class="sxs-lookup"><span data-stu-id="9e55a-113">You can launch **Server Explorer** and verify that your service has been installed or uninstalled.</span></span> <span data-ttu-id="9e55a-114">Para obtener más información, vea Cómo: acceso e inicializar el Explorador de explorador de bases de datos de servidor.</span><span class="sxs-lookup"><span data-stu-id="9e55a-114">For more information, see How to: Access and Initialize Server Explorer-Database Explorer.</span></span>  
  
### <a name="to-install-your-service-manually"></a><span data-ttu-id="9e55a-115">Para instalar el servicio manualmente</span><span class="sxs-lookup"><span data-stu-id="9e55a-115">To install your service manually</span></span>  
  
1.  <span data-ttu-id="9e55a-116">En las ventanas **iniciar** menú o **iniciar** , elija **Visual Studio** , **Visual Studio Tools**, **para desarrolladores Símbolo del sistema**.</span><span class="sxs-lookup"><span data-stu-id="9e55a-116">On the Windows **Start** menu or **Start** screen, choose **Visual Studio** , **Visual Studio Tools**, **Developer Command Prompt**.</span></span>  
  
     <span data-ttu-id="9e55a-117">Aparece un símbolo del sistema de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9e55a-117">A Visual Studio command prompt appears.</span></span>  
  
2.  <span data-ttu-id="9e55a-118">Obtenga acceso al directorio donde se encuentra el archivo ejecutable compilado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9e55a-118">Access the directory where your project's compiled executable file is located.</span></span>  
  
3.  <span data-ttu-id="9e55a-119">Ejecute InstallUtil.exe desde la línea de comandos con el archivo ejecutable del proyecto como parámetro:</span><span class="sxs-lookup"><span data-stu-id="9e55a-119">Run InstallUtil.exe from the command prompt with your project's executable as a parameter:</span></span>  
  
    ```  
    installutil <yourproject>.exe  
    ```  
  
     <span data-ttu-id="9e55a-120">Si usa el símbolo del sistema de Visual Studio, InstallUtil.exe debe estar en la ruta de acceso del sistema.</span><span class="sxs-lookup"><span data-stu-id="9e55a-120">If you’re using the Visual Studio command prompt, InstallUtil.exe should be on the system path.</span></span> <span data-ttu-id="9e55a-121">Si no es así, puede agregarlo a la ruta de acceso o usar la ruta de acceso completa para invocarlo.</span><span class="sxs-lookup"><span data-stu-id="9e55a-121">If not, you can add it to the path, or use the fully qualified path to invoke it.</span></span> <span data-ttu-id="9e55a-122">Esta herramienta se instala con .NET Framework y su ruta de acceso es `%WINDIR%\Microsoft.NET\Framework[64]\<framework_version>`.</span><span class="sxs-lookup"><span data-stu-id="9e55a-122">This tool is installed with the .NET Framework, and its path is `%WINDIR%\Microsoft.NET\Framework[64]\<framework_version>`.</span></span> <span data-ttu-id="9e55a-123">Por ejemplo, para la versión de 32 bits de .NET Framework 4 o 4.5\*, si el directorio de instalación de Windows es C:\Windows, la ruta de acceso es `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`.</span><span class="sxs-lookup"><span data-stu-id="9e55a-123">For example, for the 32-bit version of the .NET Framework 4 or 4.5.\*, if your Windows installation directory is C:\Windows, the path is `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`.</span></span> <span data-ttu-id="9e55a-124">Para la versión de 64 bits de .NET Framework 4 o 4.5. \*, la ruta predeterminada es `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe`.</span><span class="sxs-lookup"><span data-stu-id="9e55a-124">For the 64-bit version of the .NET Framework 4 or 4.5.\*, the default path is `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe`.</span></span>  
  
### <a name="to-uninstall-your-service-manually"></a><span data-ttu-id="9e55a-125">Para desinstalar el servicio manualmente</span><span class="sxs-lookup"><span data-stu-id="9e55a-125">To uninstall your service manually</span></span>  
  
1.  <span data-ttu-id="9e55a-126">En las ventanas **iniciar** menú o **iniciar** , elija **Visual Studio**, **Visual Studio Tools**, **para desarrolladores Símbolo del sistema**.</span><span class="sxs-lookup"><span data-stu-id="9e55a-126">On the Windows **Start** menu or **Start** screen, choose **Visual Studio**, **Visual Studio Tools**, **Developer Command Prompt**.</span></span>  
  
     <span data-ttu-id="9e55a-127">Aparece un símbolo del sistema de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9e55a-127">A Visual Studio command prompt appears.</span></span>  
  
2.  <span data-ttu-id="9e55a-128">Ejecute InstallUtil.exe desde la línea de comandos con la salida del proyecto como parámetro:</span><span class="sxs-lookup"><span data-stu-id="9e55a-128">Run InstallUtil.exe from the command prompt with your project's output as a parameter:</span></span>  
  
    ```  
    installutil /u <yourproject>.exe  
    ```  
  
3.  <span data-ttu-id="9e55a-129">A veces, después de eliminar el archivo ejecutable de un servicio, es posible que el servicio permanezca en el Registro.</span><span class="sxs-lookup"><span data-stu-id="9e55a-129">Sometimes, after the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="9e55a-130">En ese caso, use el comando [sc delete](http://technet.microsoft.com/library/cc742045.aspx) para quitar la entrada para el servicio del registro.</span><span class="sxs-lookup"><span data-stu-id="9e55a-130">In that case, use the command [sc delete](http://technet.microsoft.com/library/cc742045.aspx) to remove the entry for the service from the registry.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e55a-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e55a-131">See Also</span></span>  
 [<span data-ttu-id="9e55a-132">Introducción a las aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="9e55a-132">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="9e55a-133">Creación de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="9e55a-133">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="9e55a-134">Adición de instaladores a una aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="9e55a-134">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="9e55a-135">Installutil.exe (Herramienta Installer)</span><span class="sxs-lookup"><span data-stu-id="9e55a-135">Installutil.exe (Installer Tool)</span></span>](../../../docs/framework/tools/installutil-exe-installer-tool.md)
