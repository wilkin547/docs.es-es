---
title: Procedimiento Instalación y desinstalación de servicios
ms.date: 03/30/2017
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
author: ghogen
ms.openlocfilehash: 937c559130ea70ab125935ce26ecc5f9bd315ad1
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221224"
---
# <a name="how-to-install-and-uninstall-services"></a><span data-ttu-id="46a15-102">Procedimiento Instalación y desinstalación de servicios</span><span class="sxs-lookup"><span data-stu-id="46a15-102">How to: Install and Uninstall Services</span></span>
<span data-ttu-id="46a15-103">Si desarrolla un servicio de Windows mediante .NET Framework, puede instalar rápidamente la aplicación de servicio mediante una utilidad de línea de comandos denominada InstallUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="46a15-103">If you’re developing a Windows Service by using the .NET Framework, you can quickly install your service application by using a command-line utility called InstallUtil.exe.</span></span> <span data-ttu-id="46a15-104">Si es desarrollador y desea publicar un servicio de Windows que los usuarios puedan instalar y desinstalar, debe usar InstallShield.</span><span class="sxs-lookup"><span data-stu-id="46a15-104">If you’re a developer who wants to release a Windows Service that users can install and uninstall  you should use InstallShield.</span></span> <span data-ttu-id="46a15-105">Consulte [Implementación de Windows Installer](https://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0).</span><span class="sxs-lookup"><span data-stu-id="46a15-105">See [Windows Installer Deployment](https://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="46a15-106">Si desea desinstalar un servicio del equipo, no siga los pasos descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="46a15-106">If you want to uninstall a service from your computer, don’t follow the steps in this article.</span></span> <span data-ttu-id="46a15-107">En su lugar, averigüe qué paquete de software o programa instaló el servicio y, a continuación, elija **Agregar o quitar programas** en el Panel de control para desinstalar el programa.</span><span class="sxs-lookup"><span data-stu-id="46a15-107">Instead, find out which program or software package installed the service, and then choose **Add/Remove Programs** in Control Panel to uninstall that program.</span></span> <span data-ttu-id="46a15-108">Tenga en cuenta que muchos servicios forman parte de Windows; si los quita, podría causar inestabilidad en el sistema.</span><span class="sxs-lookup"><span data-stu-id="46a15-108">Note that many services are integral parts of Windows; if you remove them, you might cause system instability.</span></span>  
  
 <span data-ttu-id="46a15-109">Para poder seguir los pasos de este artículo, primero debe agregar un instalador del servicio al servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="46a15-109">In order to use the steps in this article, you first need to add a service installer to your Windows Service.</span></span> <span data-ttu-id="46a15-110">Vea [Tutorial: Creación de una aplicación de servicios de Windows en el Diseñador de componentes](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="46a15-110">See [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
 <span data-ttu-id="46a15-111">Los proyectos de servicio de Windows no se pueden ejecutar directamente desde el entorno de desarrollo de Visual Studio presionando F5.</span><span class="sxs-lookup"><span data-stu-id="46a15-111">Windows Service projects cannot be run directly from the Visual Studio development environment by pressing F5.</span></span> <span data-ttu-id="46a15-112">Esto es porque el servicio del proyecto debe estar instalado para poder ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="46a15-112">This is because the service in the project must be installed before you can run the project.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="46a15-113">Puede iniciar el **Explorador de servidores** y comprobar que el servicio se ha instalado o desinstalado.</span><span class="sxs-lookup"><span data-stu-id="46a15-113">You can launch **Server Explorer** and verify that your service has been installed or uninstalled.</span></span> <span data-ttu-id="46a15-114">Para obtener más información, vea el artículo sobre cómo acceder al Explorador de servidores y al Explorador de bases de datos e inicializarlos.</span><span class="sxs-lookup"><span data-stu-id="46a15-114">For more information, see How to: Access and Initialize Server Explorer-Database Explorer.</span></span>  
  
### <a name="to-install-your-service-manually"></a><span data-ttu-id="46a15-115">Para instalar el servicio manualmente</span><span class="sxs-lookup"><span data-stu-id="46a15-115">To install your service manually</span></span>  
  
1.  <span data-ttu-id="46a15-116">En el menú **Inicio** o la pantalla **Inicio** de Windows, elija **Visual Studio**, **Visual Studio Tools**, **Símbolo del sistema para desarrolladores**.</span><span class="sxs-lookup"><span data-stu-id="46a15-116">On the Windows **Start** menu or **Start** screen, choose **Visual Studio** , **Visual Studio Tools**, **Developer Command Prompt**.</span></span>  
  
     <span data-ttu-id="46a15-117">Aparece Símbolo del sistema para desarrolladores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="46a15-117">A Developer Command Prompt for Visual Studio appears.</span></span>  
  
2.  <span data-ttu-id="46a15-118">Obtenga acceso al directorio donde se encuentra el archivo ejecutable compilado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="46a15-118">Access the directory where your project's compiled executable file is located.</span></span>  
  
3.  <span data-ttu-id="46a15-119">Ejecute InstallUtil.exe desde la línea de comandos con el archivo ejecutable del proyecto como parámetro:</span><span class="sxs-lookup"><span data-stu-id="46a15-119">Run InstallUtil.exe from the command prompt with your project's executable as a parameter:</span></span>  
  
    ```  
    installutil <yourproject>.exe  
    ```  
  
     <span data-ttu-id="46a15-120">Si usa Símbolo del sistema para desarrolladores de Visual Studio, InstallUtil.exe debe estar en la ruta de acceso del sistema.</span><span class="sxs-lookup"><span data-stu-id="46a15-120">If you’re using the Developer Command Prompt for Visual Studio, InstallUtil.exe should be on the system path.</span></span> <span data-ttu-id="46a15-121">Si no es así, puede agregarlo a la ruta de acceso o usar la ruta de acceso completa para invocarlo.</span><span class="sxs-lookup"><span data-stu-id="46a15-121">If not, you can add it to the path, or use the fully qualified path to invoke it.</span></span> <span data-ttu-id="46a15-122">Esta herramienta se instala con .NET Framework y su ruta de acceso es `%WINDIR%\Microsoft.NET\Framework[64]\<framework_version>`.</span><span class="sxs-lookup"><span data-stu-id="46a15-122">This tool is installed with the .NET Framework, and its path is `%WINDIR%\Microsoft.NET\Framework[64]\<framework_version>`.</span></span> <span data-ttu-id="46a15-123">Por ejemplo, para la versión de 32 bits de .NET Framework 4 o 4.5\*, si el directorio de instalación de Windows es C:\Windows, la ruta de acceso es `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`.</span><span class="sxs-lookup"><span data-stu-id="46a15-123">For example, for the 32-bit version of the .NET Framework 4 or 4.5.\*, if your Windows installation directory is C:\Windows, the path is `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`.</span></span> <span data-ttu-id="46a15-124">Para la versión de 64 bits de .NET Framework 4 o 4.5\*, la ruta de acceso predeterminada es `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe`.</span><span class="sxs-lookup"><span data-stu-id="46a15-124">For the 64-bit version of the .NET Framework 4 or 4.5.\*, the default path is `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe`.</span></span>  
  
### <a name="to-uninstall-your-service-manually"></a><span data-ttu-id="46a15-125">Para desinstalar el servicio manualmente</span><span class="sxs-lookup"><span data-stu-id="46a15-125">To uninstall your service manually</span></span>  
  
1.  <span data-ttu-id="46a15-126">En el menú **Inicio** o la pantalla **Inicio** de Windows, elija **Visual Studio**, **Visual Studio Tools**, **Símbolo del sistema para desarrolladores**.</span><span class="sxs-lookup"><span data-stu-id="46a15-126">On the Windows **Start** menu or **Start** screen, choose **Visual Studio**, **Visual Studio Tools**, **Developer Command Prompt**.</span></span>  
  
     <span data-ttu-id="46a15-127">Aparece Símbolo del sistema para desarrolladores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="46a15-127">A Developer Command Prompt for Visual Studio appears.</span></span>  
  
2.  <span data-ttu-id="46a15-128">Ejecute InstallUtil.exe desde la línea de comandos con la salida del proyecto como parámetro:</span><span class="sxs-lookup"><span data-stu-id="46a15-128">Run InstallUtil.exe from the command prompt with your project's output as a parameter:</span></span>  
  
    ```  
    installutil /u <yourproject>.exe  
    ```  
  
3.  <span data-ttu-id="46a15-129">A veces, después de eliminar el archivo ejecutable de un servicio, es posible que el servicio permanezca en el Registro.</span><span class="sxs-lookup"><span data-stu-id="46a15-129">Sometimes, after the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="46a15-130">En ese caso, use el comando [sc delete](/windows-server/administration/windows-commands/sc-delete) para quitar la entrada del servicio del Registro.</span><span class="sxs-lookup"><span data-stu-id="46a15-130">In that case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46a15-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="46a15-131">See Also</span></span>  
 [<span data-ttu-id="46a15-132">Introducción a las aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="46a15-132">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="46a15-133">Cómo: Creación de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="46a15-133">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="46a15-134">Cómo: Adición de instaladores a una aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="46a15-134">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="46a15-135">Installutil.exe (Herramienta Installer)</span><span class="sxs-lookup"><span data-stu-id="46a15-135">Installutil.exe (Installer Tool)</span></span>](../../../docs/framework/tools/installutil-exe-installer-tool.md)
