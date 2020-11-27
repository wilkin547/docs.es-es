---
title: Herramienta de registro de servicio de flujo de trabajo (WFServicesReg.exe)
ms.date: 03/30/2017
ms.assetid: 9e92c87b-99c5-4e8d-9d53-7944cc2b47d3
ms.openlocfilehash: 763b617a99c98383b5b873e4fb8646884f9b5253
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261883"
---
# <a name="workflow-service-registration-tool-wfservicesregexe"></a><span data-ttu-id="47a1d-102">Herramienta de registro de servicio de flujo de trabajo (WFServicesReg.exe)</span><span class="sxs-lookup"><span data-stu-id="47a1d-102">WorkFlow Service Registration Tool (WFServicesReg.exe)</span></span>

<span data-ttu-id="47a1d-103">El registro de servicio de flujo de trabajo (WFServicesReg.exe) es una herramienta independiente que puede utilizarse para agregar, quitar o reparar los elementos de configuración de los servicios de Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="47a1d-103">Workflow Services Registration tool (WFServicesReg.exe) is a stand-alone tool that can be used to add, remove, or repair the configuration elements for Windows Workflow Foundation (WF) services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47a1d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47a1d-104">Syntax</span></span>  
  
```console  
WFServicesReg.exe [-c | -r | -v | -m | -i]  
```  
  
## <a name="remarks"></a><span data-ttu-id="47a1d-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="47a1d-105">Remarks</span></span>  

 <span data-ttu-id="47a1d-106">La herramienta se puede encontrar en la ubicación de instalación de .NET Framework 3,5, específicamente,%windir%\Microsoft.NET\Framework\v3.5 o en%windir%\Microsoft.NET\Framework64\v3.5 en máquinas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="47a1d-106">The tool can be found at the .NET Framework 3.5 installation location, specifically, %windir%\Microsoft.NET\Framework\v3.5, or at %windir%\Microsoft.NET\Framework64\v3.5 in 64-bit machines.</span></span>  
  
 <span data-ttu-id="47a1d-107">Las tablas siguientes describen las opciones que pueden utilizarse con la herramienta de registro de servicio de flujo de trabajo (WFServicesReg.exe).</span><span class="sxs-lookup"><span data-stu-id="47a1d-107">The following tables describe the options that can be used with the Workflow Services Registration tool (WFServicesReg.exe).</span></span>  
  
|<span data-ttu-id="47a1d-108">Opción</span><span class="sxs-lookup"><span data-stu-id="47a1d-108">Option</span></span>|<span data-ttu-id="47a1d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="47a1d-109">Description</span></span>|  
|------------|-----------------|  
|`/c`|<span data-ttu-id="47a1d-110">Configura los servicios de flujo de trabajo de Windows.</span><span class="sxs-lookup"><span data-stu-id="47a1d-110">Configures Windows Workflow Services.</span></span> <span data-ttu-id="47a1d-111">Se utiliza en escenarios de instalación y reparación.</span><span class="sxs-lookup"><span data-stu-id="47a1d-111">Used in install and repair scenarios.</span></span>|  
|`/r`|<span data-ttu-id="47a1d-112">Quita la configuración de los servicios de flujo de trabajo de Windows.</span><span class="sxs-lookup"><span data-stu-id="47a1d-112">Removes Windows Workflow Services Configuration.</span></span>|  
|`/v`|<span data-ttu-id="47a1d-113">Imprime información detallada (para configuración o eliminación).</span><span class="sxs-lookup"><span data-stu-id="47a1d-113">Print verbose information (for either configuration or removal).</span></span>|  
|`/m`|<span data-ttu-id="47a1d-114">Habilita el formato de registro de MSI.</span><span class="sxs-lookup"><span data-stu-id="47a1d-114">Enables MSI logging format.</span></span>|  
|`/i`|<span data-ttu-id="47a1d-115">Minimiza la ventana cuando se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="47a1d-115">Minimizes the window when the application runs.</span></span>|  
  
## <a name="registration"></a><span data-ttu-id="47a1d-116">Registro</span><span class="sxs-lookup"><span data-stu-id="47a1d-116">Registration</span></span>  

 <span data-ttu-id="47a1d-117">La herramienta inspecciona el archivo Web.config y registra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="47a1d-117">The tool inspects the Web.config file and registers the following:</span></span>  
  
- <span data-ttu-id="47a1d-118">Ensamblados de referencia de .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="47a1d-118">.NET Framework 3.5 reference assemblies.</span></span>  
  
- <span data-ttu-id="47a1d-119">Proveedor de compilación para archivos .xoml.</span><span class="sxs-lookup"><span data-stu-id="47a1d-119">A build provider for .xoml files.</span></span>  
  
- <span data-ttu-id="47a1d-120">Controladores HTTP para archivos .xoml y .rules.</span><span class="sxs-lookup"><span data-stu-id="47a1d-120">HTTP handlers for .xoml and .rules files.</span></span>  
  
 <span data-ttu-id="47a1d-121">La herramienta inspecciona el archivo Machine.config y registra las siguientes extensiones:</span><span class="sxs-lookup"><span data-stu-id="47a1d-121">The tool inspects the Machine.config file and registers the following extensions:</span></span>  
  
- <span data-ttu-id="47a1d-122">behaviorExtensions</span><span class="sxs-lookup"><span data-stu-id="47a1d-122">behaviorExtensions</span></span>  
  
- <span data-ttu-id="47a1d-123">bindingElementExtensions</span><span class="sxs-lookup"><span data-stu-id="47a1d-123">bindingElementExtensions</span></span>  
  
- <span data-ttu-id="47a1d-124">bindingExtensions</span><span class="sxs-lookup"><span data-stu-id="47a1d-124">bindingExtensions</span></span>  
  
 <span data-ttu-id="47a1d-125">La herramienta también registra los siguientes importadores de metadatos de cliente:</span><span class="sxs-lookup"><span data-stu-id="47a1d-125">The tool also registers the following client metadata importers:</span></span>  
  
- <span data-ttu-id="47a1d-126">policyImporters</span><span class="sxs-lookup"><span data-stu-id="47a1d-126">policyImporters</span></span>  
  
- <span data-ttu-id="47a1d-127">wsdlImporters</span><span class="sxs-lookup"><span data-stu-id="47a1d-127">wsdlImporters</span></span>  
  
 <span data-ttu-id="47a1d-128">La herramienta también registra los controladores y las asignaciones de secuencias de comandos de .xoml y .rules en la metabase de IIS.</span><span class="sxs-lookup"><span data-stu-id="47a1d-128">The tool also registers .xoml and .rules scriptmaps and handlers in the IIS metabase.</span></span>  
  
 <span data-ttu-id="47a1d-129">En Windows Server 2003 y equipos con Windows XP (IIS 5,1 e IIS 6,0), se registra un conjunto de asignaciones de scripts. xoml y. rules.</span><span class="sxs-lookup"><span data-stu-id="47a1d-129">On Windows Server 2003 and Windows XP machines (IIS 5.1 and IIS 6.0), one set of .xoml and .rules scriptmaps are registered.</span></span>  
  
 <span data-ttu-id="47a1d-130">En equipos de 64 bits, la herramienta registra asignaciones de secuencias de comandos en el modo WOW si el modificador `Enable32BitAppOnWin64` está habilitado, o asignaciones de secuencias de comandos nativas de 64 bits si el modificador `Enable32BitAppOnWin64` está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="47a1d-130">On 64-bit machines, the tool registers WOW mode scriptmaps if the `Enable32BitAppOnWin64` switch is enabled, or native 64-bit scriptmaps if the `Enable32BitAppOnWin64` switch is disabled.</span></span>  
  
 <span data-ttu-id="47a1d-131">En las máquinas con Windows Vista y Windows Server 2008 (IIS 7,0 y versiones posteriores), se registran dos conjuntos de controladores. xoml y. rules: uno para el modo integrado y otro para el modo clásico.</span><span class="sxs-lookup"><span data-stu-id="47a1d-131">On Windows Vista and Windows Server 2008 (IIS 7.0 and above) machines, two sets of .xoml and .rules handlers are registered: one for Integrated mode and one for Classic mode.</span></span>  
  
 <span data-ttu-id="47a1d-132">En equipos de 64 bits, se registran tres conjuntos de controladores (independientemente del estado del modificador `Enable32BitAppOnWin64`): uno para el modo integrado, otro para el modo clásico de WOW y el tercero para el modo clásico de 64 bits nativo.</span><span class="sxs-lookup"><span data-stu-id="47a1d-132">On 64-bit machines, three sets of handlers are registered (regardless of the state of the `Enable32BitAppOnWin64` switch): one for Integrated mode, one for WOW Classic mode and one for native 64-bit Classic mode.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="47a1d-133">A diferencia de ServiceModelReg.exe, WFServicesReg.exe no permite agregar, quitar o reparar asignaciones de secuencias de comandos o controladores de un sitio web determinado.</span><span class="sxs-lookup"><span data-stu-id="47a1d-133">Unlike ServiceModelreg.exe, WFServicesReg.exe does not allow adding, removing, or repairing scriptmaps or handlers for a particular Web site.</span></span> <span data-ttu-id="47a1d-134">Para encontrar una solución a este problema, vea la sección "Reparar asignaciones de secuencias de comandos".</span><span class="sxs-lookup"><span data-stu-id="47a1d-134">For a workaround to this issue, see the "Repairing the Scriptmaps" section.</span></span>  
  
## <a name="usage-scenarios"></a><span data-ttu-id="47a1d-135">Escenarios de uso</span><span class="sxs-lookup"><span data-stu-id="47a1d-135">Usage Scenarios</span></span>  
  
### <a name="installing-iis-after-net-framework-35-is-installed"></a><span data-ttu-id="47a1d-136">Instalar IIS una vez instalado .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="47a1d-136">Installing IIS after .NET Framework 3.5 is installed</span></span>  

 <span data-ttu-id="47a1d-137">En un equipo con Windows Server 2003, .NET Framework 3,5 se instala antes de la instalación de IIS.</span><span class="sxs-lookup"><span data-stu-id="47a1d-137">On a Windows Server 2003 machine, .NET Framework 3.5 is installed prior to IIS installation.</span></span> <span data-ttu-id="47a1d-138">Debido a la falta de disponibilidad de la metabase de IIS, la instalación de .NET Framework 3,5 se realiza correctamente sin instalar las asignaciones de scripts. xoml y. rules.</span><span class="sxs-lookup"><span data-stu-id="47a1d-138">Due to the unavailability of the IIS metabase, installation of .NET Framework 3.5 succeeds without installing .xoml and .rules scriptmaps.</span></span>  
  
 <span data-ttu-id="47a1d-139">Una vez instalado IIS, puede utilizar la herramienta WFServicesReg.exe con el modificador `/c` para instalar estas asignaciones de secuencias de comandos concretas.</span><span class="sxs-lookup"><span data-stu-id="47a1d-139">After IIS is installed, you can use the WFServicesReg.exe tool with the `/c` switch to install these specific scriptmaps.</span></span>  
  
### <a name="repairing-the-scriptmaps"></a><span data-ttu-id="47a1d-140">Reparar asignaciones de secuencias de comandos</span><span class="sxs-lookup"><span data-stu-id="47a1d-140">Repairing the Scriptmaps</span></span>  
  
#### <a name="scriptmap-deleted-under-web-sites-node"></a><span data-ttu-id="47a1d-141">Asignación de secuencias de comandos eliminada en el nodo de sitios web</span><span class="sxs-lookup"><span data-stu-id="47a1d-141">Scriptmap deleted under Web Sites node</span></span>  

 <span data-ttu-id="47a1d-142">En un equipo con Windows Server 2003,. xoml o. rules se eliminan accidentalmente del nodo sitios Web.</span><span class="sxs-lookup"><span data-stu-id="47a1d-142">On a Windows Server 2003 machine, .xoml or .rules is accidentally deleted from the Web Sites node.</span></span> <span data-ttu-id="47a1d-143">Esto puede repararse ejecutando la herramienta WFServicesReg.exe con el modificador `/c`.</span><span class="sxs-lookup"><span data-stu-id="47a1d-143">This can be repaired by running the WFServicesReg.exe tool with the `/c` switch.</span></span>  
  
#### <a name="scriptmap-deleted-under-a-particular-web-site"></a><span data-ttu-id="47a1d-144">Asignación de secuencias de comandos eliminada en un sitio web determinado</span><span class="sxs-lookup"><span data-stu-id="47a1d-144">Scriptmap deleted under a particular Web site</span></span>  

 <span data-ttu-id="47a1d-145">En un equipo con Windows Server 2003,. xoml o. rules se eliminan accidentalmente de un sitio Web determinado (por ejemplo, el sitio web predeterminado) en lugar de hacerlo del nodo sitios Web.</span><span class="sxs-lookup"><span data-stu-id="47a1d-145">On a Windows Server 2003 machine, .xoml or .rules is accidentally deleted from a particular Web site (for example, the Default Web Site) rather than from the Web Sites node.</span></span>  
  
 <span data-ttu-id="47a1d-146">Para reparar los controladores eliminados de un sitio Web determinado, debe ejecutar "WFServicesReg.exe/r" para quitar los controladores de todos los sitios web y, a continuación, ejecutar "WFServicesReg.exe/c" para crear los controladores adecuados para todos los sitios Web.</span><span class="sxs-lookup"><span data-stu-id="47a1d-146">To repair deleted handlers for a particular Web site, you should run "WFServicesReg.exe /r" to remove handlers from all Web sites, then run "WFServicesReg.exe /c" to create the appropriate handlers for all Web sites.</span></span>  
  
### <a name="configuring-handlers-after-switching-iis-mode"></a><span data-ttu-id="47a1d-147">Configurar los controladores después de cambiar al modo de IIS</span><span class="sxs-lookup"><span data-stu-id="47a1d-147">Configuring handlers after switching IIS mode</span></span>  

 <span data-ttu-id="47a1d-148">Cuando IIS está en modo de configuración compartida y .NET Framework está instalado 3,5, la metabase de IIS se configura en una ubicación compartida.</span><span class="sxs-lookup"><span data-stu-id="47a1d-148">When IIS is in shared configuration mode and .NET Framework 3.5 is installed, the IIS metabase is configured under a shared location.</span></span> <span data-ttu-id="47a1d-149">Si pasa IIS al modo de configuración no compartido, la metabase local no contendrá los controladores necesarios.</span><span class="sxs-lookup"><span data-stu-id="47a1d-149">If you switch IIS to non-shared configuration mode, the local metabase will not contain the required handlers.</span></span> <span data-ttu-id="47a1d-150">Para configurar la metabase local correctamente, puede importar la metabase compartida a local o ejecutar "WFServicesReg.exe/c", que configura la metabase local.</span><span class="sxs-lookup"><span data-stu-id="47a1d-150">To configure the local metabase properly, you can either import the shared metabase to local, or run "WFServicesReg.exe /c", which configures the local metabase.</span></span>
