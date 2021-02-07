---
description: Más información acerca de cómo solucionar problemas de instalación
title: Solución de problemas de instalación
ms.date: 03/30/2017
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
ms.openlocfilehash: 8beb404040c15ade8f435772fe1b947eef766702
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703476"
---
# <a name="troubleshoot-setup-issues"></a><span data-ttu-id="6d5fc-103">Solucionar problemas de configuración</span><span class="sxs-lookup"><span data-stu-id="6d5fc-103">Troubleshoot setup issues</span></span>

<span data-ttu-id="6d5fc-104">En este artículo se describe cómo solucionar problemas de configuración de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="6d5fc-104">This article describes how to troubleshoot Windows Communication Foundation (WCF) setup issues.</span></span>  
  
## <a name="some-windows-communication-foundation-registry-keys-are-not-repaired-by-performing-an-msi-repair-operation-on-the-net-framework-30"></a><span data-ttu-id="6d5fc-105">Algunas claves del Registro de Windows Communication Foundation no se reparan mediante una operación de reparación de MSI en .NET Framework 3.0</span><span class="sxs-lookup"><span data-stu-id="6d5fc-105">Some Windows Communication Foundation Registry Keys are not Repaired by Performing an MSI Repair Operation on the .NET Framework 3.0</span></span>  

 <span data-ttu-id="6d5fc-106">Si elimina cualquiera de las claves del Registro siguientes:</span><span class="sxs-lookup"><span data-stu-id="6d5fc-106">If you delete any of the following registry keys:</span></span>  
  
- <span data-ttu-id="6d5fc-107">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0</span><span class="sxs-lookup"><span data-stu-id="6d5fc-107">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0</span></span>  
  
- <span data-ttu-id="6d5fc-108">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0</span><span class="sxs-lookup"><span data-stu-id="6d5fc-108">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0</span></span>  
  
- <span data-ttu-id="6d5fc-109">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0</span><span class="sxs-lookup"><span data-stu-id="6d5fc-109">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0</span></span>  
  
- <span data-ttu-id="6d5fc-110">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0</span><span class="sxs-lookup"><span data-stu-id="6d5fc-110">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0</span></span>  
  
- <span data-ttu-id="6d5fc-111">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0</span><span class="sxs-lookup"><span data-stu-id="6d5fc-111">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0</span></span>  
  
 <span data-ttu-id="6d5fc-112">Las claves no se vuelven a crear si ejecuta la reparación con el instalador .NET Framework 3,0 iniciado desde el applet **Agregar o quitar programas** del **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="6d5fc-112">The keys are not re-created if you run repair by using the .NET Framework 3.0 installer launched from the **Add/Remove Programs** applet in **Control Panel**.</span></span> <span data-ttu-id="6d5fc-113">Para volver a crear correctamente estas claves, el usuario debe desinstalar y reinstalar .NET Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="6d5fc-113">To recreate these keys correctly, the user must uninstall and reinstall the .NET Framework 3.0.</span></span>  
  
## <a name="wmi-service-corruption-blocks-installation-of-the-wmi-provider"></a><span data-ttu-id="6d5fc-114">Daños en el servicio WMI la instalación del proveedor WMI</span><span class="sxs-lookup"><span data-stu-id="6d5fc-114">WMI Service Corruption Blocks Installation of the WMI provider</span></span>

 <span data-ttu-id="6d5fc-115">Los daños en el servicio WMI pueden bloquear la instalación del Windows Communication Foundation proveedor WMI al instalar el paquete .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="6d5fc-115">WMI Service Corruption may block the installation of the Windows Communication Foundation WMI provider when installing the .NET Framework 3.0 package.</span></span> <span data-ttu-id="6d5fc-116">Durante la instalación, el instalador de Windows Communication Foundation no puede registrar el archivo WCF *. mof* mediante el componente *mofcomp.exe* .</span><span class="sxs-lookup"><span data-stu-id="6d5fc-116">During installation, the Windows Communication Foundation installer is unable to register the WCF *.mof* file using the *mofcomp.exe* component.</span></span> <span data-ttu-id="6d5fc-117">A continuación, se muestra una lista de síntomas:</span><span class="sxs-lookup"><span data-stu-id="6d5fc-117">The following is a list of symptoms:</span></span>  
  
1. <span data-ttu-id="6d5fc-118">La instalación de .NET Framework 3.0 finaliza correctamente, pero no se registra el proveedor de WCF WMI.</span><span class="sxs-lookup"><span data-stu-id="6d5fc-118">.NET Framework 3.0 installation completes successfully, but the WCF WMI provider is not registered.</span></span>  
  
2. <span data-ttu-id="6d5fc-119">Un evento de error aparece en el registro de eventos de la aplicación que hace referencia a problemas al registrar el proveedor de WMI para WCF o al ejecutar mofcomp.exe.</span><span class="sxs-lookup"><span data-stu-id="6d5fc-119">An error event appears in the application event log that references problems registering the WMI provider for WCF, or running mofcomp.exe.</span></span>  
  
3. <span data-ttu-id="6d5fc-120">El archivo de registro de instalación denominado dd_wcf_retCA\* en el directorio % temp% del usuario contiene referencias al error para registrar el proveedor de WCF WMI.</span><span class="sxs-lookup"><span data-stu-id="6d5fc-120">The setup log file named dd_wcf_retCA\* in the user's %temp% directory contains references to failure to register the WCF WMI provider.</span></span>  
  
4. <span data-ttu-id="6d5fc-121">Una excepción como una de las siguientes puede mostrarse en el registro de eventos o en el archivo de registro de traza de la instalación:</span><span class="sxs-lookup"><span data-stu-id="6d5fc-121">An exception such as one the following may be listed in the event log or setup trace log file:</span></span>  
  
     <span data-ttu-id="6d5fc-122">ServiceModelReg [11:09:59:046]: System.ApplicationException: Resultado inesperado 3 al ejecutar E:\WINDOWS\system32\wbem\mofcomp.exe con "E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof"</span><span class="sxs-lookup"><span data-stu-id="6d5fc-122">ServiceModelReg [11:09:59:046]: System.ApplicationException: Unexpected result 3 executing E:\WINDOWS\system32\wbem\mofcomp.exe with "E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof"</span></span>  
  
     <span data-ttu-id="6d5fc-123">O bien</span><span class="sxs-lookup"><span data-stu-id="6d5fc-123">or:</span></span>  
  
     <span data-ttu-id="6d5fc-124">ServiceModelReg [07:19:33:843]: System.TypeInitializationException: El inicializador de tipo para 'System.Management.ManagementPath' produjo una excepción.</span><span class="sxs-lookup"><span data-stu-id="6d5fc-124">ServiceModelReg [07:19:33:843]: System.TypeInitializationException: The type initializer for 'System.Management.ManagementPath' threw an exception.</span></span> <span data-ttu-id="6d5fc-125">---> System. Runtime. InteropServices. COMException (0x80040154): no se pudo recuperar el generador de clases COM para el componente con CLSID {CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA} debido al siguiente error: 80040154.</span><span class="sxs-lookup"><span data-stu-id="6d5fc-125">---> System.Runtime.InteropServices.COMException (0x80040154): Retrieving the COM class factory for component with CLSID {CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA} failed due to the following error: 80040154.</span></span>  
  
     <span data-ttu-id="6d5fc-126">O bien</span><span class="sxs-lookup"><span data-stu-id="6d5fc-126">or:</span></span>  
  
     <span data-ttu-id="6d5fc-127">ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: No pudo cargar el archivo ni ensamblado 'C:\WINDOWS\system32\wbem\mofcomp.exe' o uno de sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="6d5fc-127">ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: Could not load file or assembly 'C:\WINDOWS\system32\wbem\mofcomp.exe' or one of its dependencies.</span></span> <span data-ttu-id="6d5fc-128">El sistema no encuentra el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="6d5fc-128">The system cannot find the file specified.</span></span>  
  
     <span data-ttu-id="6d5fc-129">Nombre del archivo: 'C:\WINDOWS\system32\wbem\mofcomp.exe</span><span class="sxs-lookup"><span data-stu-id="6d5fc-129">File name: 'C:\WINDOWS\system32\wbem\mofcomp.exe</span></span>  
  
 <span data-ttu-id="6d5fc-130">Se deben seguir los pasos siguientes para resolver el problema descrito previamente.</span><span class="sxs-lookup"><span data-stu-id="6d5fc-130">The following steps must be followed to resolve the problem described previously.</span></span>  
  
1. <span data-ttu-id="6d5fc-131">Ejecute el Utilidad de diagnóstico de WMI para reparar el servicio WMI.</span><span class="sxs-lookup"><span data-stu-id="6d5fc-131">Run the WMI Diagnosis Utility to repair the WMI service.</span></span> <span data-ttu-id="6d5fc-132">Para obtener más información sobre el uso de esta herramienta, vea [utilidad de diagnóstico de WMI](/previous-versions/tn-archive/ff404265(v%3dmsdn.10)).</span><span class="sxs-lookup"><span data-stu-id="6d5fc-132">For more information about using this tool, see [WMI Diagnosis Utility](/previous-versions/tn-archive/ff404265(v%3dmsdn.10)).</span></span>  
  
 <span data-ttu-id="6d5fc-133">Repare la instalación de .NET Framework 3,0 mediante el applet **Agregar o quitar programas** que se encuentra en el **Panel de control**, o bien desinstale o vuelva a instalar el .NET Framework 3,0.</span><span class="sxs-lookup"><span data-stu-id="6d5fc-133">Repair the .NET Framework 3.0 installation by using the **Add/Remove Programs** applet located in **Control Panel**, or uninstall/reinstall the .NET Framework 3.0.</span></span>  
  
## <a name="repair-net-framework-30-after-net-framework-35-installation"></a><span data-ttu-id="6d5fc-134">Reparar .NET Framework 3,0 después de la instalación de .NET Framework 3,5</span><span class="sxs-lookup"><span data-stu-id="6d5fc-134">Repair .NET Framework 3.0 after .NET Framework 3.5 Installation</span></span>

 <span data-ttu-id="6d5fc-135">Si realiza una reparación de .NET Framework 3,0 después de instalar .NET Framework 3,5, se quitan los elementos de configuración introducidos por .NET Framework 3,5 en *machine.config* .</span><span class="sxs-lookup"><span data-stu-id="6d5fc-135">If you do a repair of .NET Framework 3.0 after you installed .NET Framework 3.5, configuration elements introduced by .NET Framework 3.5 in *machine.config* are removed.</span></span> <span data-ttu-id="6d5fc-136">Sin embargo, el archivo de *web.config* permanece intacto.</span><span class="sxs-lookup"><span data-stu-id="6d5fc-136">However, the *web.config* file remains intact.</span></span> <span data-ttu-id="6d5fc-137">La solución consiste en reparar .NET Framework 3,5 después de hacerlo a través de ARP, o usar la [herramienta de registro del servicio de flujo de trabajo (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) con el `/c` modificador.</span><span class="sxs-lookup"><span data-stu-id="6d5fc-137">The workaround is to repair .NET Framework 3.5 after this via ARP, or use the [WorkFlow Service Registration Tool (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) with the `/c` switch.</span></span>  
  
 <span data-ttu-id="6d5fc-138">La [herramienta de registro del servicio de flujo de trabajo (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) se puede encontrar en%WINDIR%\Microsoft.NET\framework\v3.5\ o%WINDIR%\Microsoft.NET\framework64\v3.5</span><span class="sxs-lookup"><span data-stu-id="6d5fc-138">[WorkFlow Service Registration Tool (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) can be found at %windir%\Microsoft.NET\framework\v3.5\ or %windir%\Microsoft.NET\framework64\v3.5</span></span>\  
  
## <a name="configure-iis-properly-for-wcfwf-webhost-after-installing-net-framework-35"></a><span data-ttu-id="6d5fc-139">Configurar IIS correctamente para Webhost de WCF/WF después de instalar .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="6d5fc-139">Configure IIS Properly for WCF/WF Webhost after Installing .NET Framework 3.5</span></span>  

 <span data-ttu-id="6d5fc-140">Cuando .NET Framework instalación 3,5 no puede configurar otras opciones de configuración de IIS relacionadas con WCF, registra un error en el registro de instalación y continúa.</span><span class="sxs-lookup"><span data-stu-id="6d5fc-140">When .NET Framework 3.5 installation fails to configure additional WCF-related IIS configuration settings, it logs an error in the installation log and continues.</span></span> <span data-ttu-id="6d5fc-141">Cualquier intento de ejecutar las aplicaciones de WorkflowServices será en vano ya que faltan los valores de configuración necesarios.</span><span class="sxs-lookup"><span data-stu-id="6d5fc-141">Any attempt to run WorkflowServices applications will fail, since the required configuration settings are missing.</span></span> <span data-ttu-id="6d5fc-142">Por ejemplo, puede fallar la carga de los archivos .xoml o .rules.</span><span class="sxs-lookup"><span data-stu-id="6d5fc-142">For example, loading xoml or rules service can fail.</span></span>  
  
 <span data-ttu-id="6d5fc-143">Para solucionar este problema, use la [herramienta de registro del servicio de flujo de trabajo (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) con el `/c` modificador para configurar correctamente las asignaciones de script de IIS en la máquina.</span><span class="sxs-lookup"><span data-stu-id="6d5fc-143">To workaround this problem, use the [WorkFlow Service Registration Tool (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) with the `/c` switch to properly configure IIS script maps on the machine.</span></span> <span data-ttu-id="6d5fc-144">La [herramienta de registro del servicio de flujo de trabajo (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) se puede encontrar en%WINDIR%\Microsoft.NET\framework\v3.5\ o%WINDIR%\Microsoft.NET\framework64\v3.5</span><span class="sxs-lookup"><span data-stu-id="6d5fc-144">[WorkFlow Service Registration Tool (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) can be found at %windir%\Microsoft.NET\framework\v3.5\ or %windir%\Microsoft.NET\framework64\v3.5</span></span>\  
  
## <a name="could-not-load-type-systemservicemodelactivationhttpmodule"></a><span data-ttu-id="6d5fc-145">No se pudo cargar el tipo ' System. ServiceModel. Activation. HttpModule '</span><span class="sxs-lookup"><span data-stu-id="6d5fc-145">Could not load type 'System.ServiceModel.Activation.HttpModule'</span></span>

<span data-ttu-id="6d5fc-146">**No se pudo cargar el tipo ' System. ServiceModel. Activation. HttpModule ' del ensamblado ' System. ServiceModel, version 3.0.0.0, Culture = neutral, PublicKeyToken = b77a5c561934e089 '**</span><span class="sxs-lookup"><span data-stu-id="6d5fc-146">**Could not load type 'System.ServiceModel.Activation.HttpModule' from assembly 'System.ServiceModel, Version 3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'**</span></span>

 <span data-ttu-id="6d5fc-147">Este error se produce si .NET Framework 4 está instalado y, a continuación, se habilita la activación HTTP de WCF.</span><span class="sxs-lookup"><span data-stu-id="6d5fc-147">This error occurs if .NET Framework 4 is installed and then WCF HTTP Activation is enabled.</span></span> <span data-ttu-id="6d5fc-148">Para resolver el problema, ejecute el siguiente comando desde el Símbolo del sistema para desarrolladores para Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="6d5fc-148">To resolve the issue, run the following command from inside the Developer Command Prompt for Visual Studio:</span></span>  
  
```console
aspnet_regiis.exe -i -enable  
```  
  
## <a name="see-also"></a><span data-ttu-id="6d5fc-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d5fc-149">See also</span></span>

- [<span data-ttu-id="6d5fc-150">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="6d5fc-150">Set-Up Instructions</span></span>](./samples/set-up-instructions.md)
