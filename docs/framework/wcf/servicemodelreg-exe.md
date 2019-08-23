---
title: Herramienta de registro de ServiceModel (ServiceModelReg.exe)
ms.date: 03/30/2017
ms.assetid: 396ec5ae-e34f-4c64-a164-fcf50e86b6ac
ms.openlocfilehash: 519f303507ed873266cc05a7556073887b66ba6f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923029"
---
# <a name="servicemodel-registration-tool-servicemodelregexe"></a><span data-ttu-id="72bcc-102">Herramienta de registro de ServiceModel (ServiceModelReg.exe)</span><span class="sxs-lookup"><span data-stu-id="72bcc-102">ServiceModel Registration Tool (ServiceModelReg.exe)</span></span>
<span data-ttu-id="72bcc-103">Esta herramienta de la línea de comandos proporciona la capacidad de administrar el registro de componentes de WCF y de WF en un único equipo.</span><span class="sxs-lookup"><span data-stu-id="72bcc-103">This command-line tool provides the ability to manage the registration of WCF and WF components on a single machine.</span></span> <span data-ttu-id="72bcc-104">En circunstancias normales no debería ser necesario usar esta herramienta mientras se configuran e instalan los componentes de WCF y de WF.</span><span class="sxs-lookup"><span data-stu-id="72bcc-104">Under normal circumstances you should not need to use this tool as WCF and WF components are configured when installed.</span></span> <span data-ttu-id="72bcc-105">Pero si experimenta problemas con la activación del servicio, puede intentar registrar los componentes mediante esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="72bcc-105">But if you are experiencing problems with service activation, you can try to register the components using this tool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72bcc-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72bcc-106">Syntax</span></span>  
  
```  
ServiceModelReg.exe[(-ia|-ua|-r)|((-i|-u) -c:<command>)] [-v|-q] [-nologo] [-?]  
```  
  
## <a name="remarks"></a><span data-ttu-id="72bcc-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="72bcc-107">Remarks</span></span>  
 <span data-ttu-id="72bcc-108">La herramienta se puede encontrar en la ubicación siguiente:</span><span class="sxs-lookup"><span data-stu-id="72bcc-108">The tool can be found in the following location:</span></span>  
  
 <span data-ttu-id="72bcc-109">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="72bcc-109">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation</span></span>\  
  
> [!NOTE]
> <span data-ttu-id="72bcc-110">Cuando se ejecuta la herramienta de registro de [!INCLUDE[wv](../../../includes/wv-md.md)]ServiceModel, es posible que el cuadro de diálogo **características de Windows** no refleje que está activada la opción de **activación http Windows Communication Foundation** en **Microsoft .NET Framework 3,0** .</span><span class="sxs-lookup"><span data-stu-id="72bcc-110">When the ServiceModel Registration Tool is run on [!INCLUDE[wv](../../../includes/wv-md.md)], the **Windows Features** dialog may not reflect that the **Windows Communication Foundation HTTP Activation** option under **Microsoft .NET Framework 3.0** is turned on.</span></span> <span data-ttu-id="72bcc-111">Para obtener acceso al cuadro de diálogo **características de Windows** , haga clic en **Inicio**, luego en **Ejecutar** y, a continuación, escriba **OptionalFeatures**.</span><span class="sxs-lookup"><span data-stu-id="72bcc-111">The **Windows Features** dialog can be accessed by clicking **Start**, then click **Run** and then typing **OptionalFeatures**.</span></span>  
  
 <span data-ttu-id="72bcc-112">Las tablas siguientes describen las opciones que se pueden utilizar con ServiceModelReg.exe.</span><span class="sxs-lookup"><span data-stu-id="72bcc-112">The following tables describe the options that can be used with ServiceModelReg.exe.</span></span>  
  
|<span data-ttu-id="72bcc-113">Opción</span><span class="sxs-lookup"><span data-stu-id="72bcc-113">Option</span></span>|<span data-ttu-id="72bcc-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="72bcc-114">Description</span></span>|  
|------------|-----------------|  
|`-ia`|<span data-ttu-id="72bcc-115">Instala todos los componentes de WCF y de WF.</span><span class="sxs-lookup"><span data-stu-id="72bcc-115">Installs all WCF and WF components.</span></span>|  
|`-ua`|<span data-ttu-id="72bcc-116">Desinstala todos los componentes de WCF y de WF.</span><span class="sxs-lookup"><span data-stu-id="72bcc-116">Uninstalls all WCF and WF components.</span></span>|  
|`-r`|<span data-ttu-id="72bcc-117">Repara todos los componentes de WCF y de WF.</span><span class="sxs-lookup"><span data-stu-id="72bcc-117">Repairs all WCF and WF components.</span></span>|  
|`-i`|<span data-ttu-id="72bcc-118">Instala los componentes de WCF y de WF especificados con –c.</span><span class="sxs-lookup"><span data-stu-id="72bcc-118">Installs WCF and WF components specified with –c.</span></span>|  
|`-u`|<span data-ttu-id="72bcc-119">Desinstala los componentes de WCF y de WF especificados con –c.</span><span class="sxs-lookup"><span data-stu-id="72bcc-119">Uninstalls WCF and WF components specified with –c.</span></span>|  
|`-c`|<span data-ttu-id="72bcc-120">Instala o desinstala un componente:</span><span class="sxs-lookup"><span data-stu-id="72bcc-120">Installs or uninstalls a component:</span></span><br /><br /> <span data-ttu-id="72bcc-121">-httpnamespace: Reserva de espacio de nombres HTTP</span><span class="sxs-lookup"><span data-stu-id="72bcc-121">-   httpnamespace – HTTP Namespace Reservation</span></span><br /><span data-ttu-id="72bcc-122">-tcpportsharing: servicio de uso compartido de puertos TCP</span><span class="sxs-lookup"><span data-stu-id="72bcc-122">-   tcpportsharing – TCP port sharing service</span></span><br /><span data-ttu-id="72bcc-123">-tcpactivation: servicio de activación TCP (no compatible con .NET 4 Client Profile)</span><span class="sxs-lookup"><span data-stu-id="72bcc-123">-   tcpactivation – TCP activation service (unsupported on .NET 4 Client Profile)</span></span><br /><span data-ttu-id="72bcc-124">-namedpipeactivation: servicio de activación de canalizaciones con nombre (no compatible con .NET 4 Client Profile</span><span class="sxs-lookup"><span data-stu-id="72bcc-124">-   namedpipeactivation – Named pipe activation service (unsupported on .NET 4 Client Profile</span></span><br /><span data-ttu-id="72bcc-125">-msmqactivation: servicio de activación de MSMQ (no compatible con .NET 4 Client Profile</span><span class="sxs-lookup"><span data-stu-id="72bcc-125">-   msmqactivation – MSMQ activation service (unsupported on .NET 4 Client Profile</span></span><br /><span data-ttu-id="72bcc-126">-ETW: manifiestos de seguimiento de eventos ETW (Windows Vista o posterior)</span><span class="sxs-lookup"><span data-stu-id="72bcc-126">-   etw – ETW event tracing manifests (Windows Vista or later)</span></span>|  
|`-q`|<span data-ttu-id="72bcc-127">Modo silencioso (solo se muestra el registro de errores)</span><span class="sxs-lookup"><span data-stu-id="72bcc-127">Quiet mode (only display error logging)</span></span>|  
|`-v`|<span data-ttu-id="72bcc-128">Modo detallado.</span><span class="sxs-lookup"><span data-stu-id="72bcc-128">Verbose mode.</span></span>|  
|`-nologo`|<span data-ttu-id="72bcc-129">Suprime el mensaje del banner y el copyright.</span><span class="sxs-lookup"><span data-stu-id="72bcc-129">Suppresses the copyright and banner message.</span></span>|  
|`-?`|<span data-ttu-id="72bcc-130">Muestra texto de ayuda.</span><span class="sxs-lookup"><span data-stu-id="72bcc-130">Displays help text</span></span>|  
  
## <a name="fixing-the-fileloadexception-error"></a><span data-ttu-id="72bcc-131">Corregir el error FileLoadException</span><span class="sxs-lookup"><span data-stu-id="72bcc-131">Fixing the FileLoadException Error</span></span>  
 <span data-ttu-id="72bcc-132">Si instaló versiones anteriores de WCF en el equipo, es posible que reciba un `FileLoadFoundException` error al ejecutar la herramienta ServiceModelReg para registrar una nueva instalación.</span><span class="sxs-lookup"><span data-stu-id="72bcc-132">If you installed previous versions of WCF on your machine, you may get a `FileLoadFoundException` error when you run the ServiceModelReg tool to register a new installation.</span></span> <span data-ttu-id="72bcc-133">Esto puede pasar aun cuando ha quitado manualmente los archivos de la instalación anterior, pero ha dejado intactos los valores machine.config.</span><span class="sxs-lookup"><span data-stu-id="72bcc-133">This can happen even if you have manually removed files from the previous install, but left the machine.config settings intact.</span></span>  
  
 <span data-ttu-id="72bcc-134">El mensaje de error es similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="72bcc-134">The error message is similar to the following.</span></span>  
  
```  
Error: System.IO.FileLoadException: Could not load file or assembly 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040)  
File name: 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'  
```  
  
 <span data-ttu-id="72bcc-135">Debería observar en el mensaje de error que el ensamblado de la versión 2.0.0.0 de System.ServiceModel fue instalado por un lanzamiento anterior de Customer Technology Preview (CTP).</span><span class="sxs-lookup"><span data-stu-id="72bcc-135">You should note from the error message that the System.ServiceModel Version 2.0.0.0 assembly was installed by an early Customer Technology Preview (CTP) release.</span></span> <span data-ttu-id="72bcc-136">La versión actual del ensamblado System.ServiceModel que se ha lanzado es 3.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="72bcc-136">The current version of the System.ServiceModel assembly released is 3.0.0.0 instead.</span></span> <span data-ttu-id="72bcc-137">Por lo tanto, este problema se produce cuando se desea instalar la versión oficial de WCF en un equipo en el que se ha instalado una versión de CTP temprana, pero no se ha desinstalado por completo.</span><span class="sxs-lookup"><span data-stu-id="72bcc-137">Therefore, this issue is encountered when you want to install the official WCF release on a machine where an early CTP release of WCF was installed, but not completely uninstalled.</span></span>  
  
 <span data-ttu-id="72bcc-138">ServiceModelReg.exe no puede limpiar las entradas de versión anteriores, ni puede registrar las entradas de la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="72bcc-138">ServiceModelReg.exe cannot clean up prior version entries, nor can it register the new version's entries.</span></span> <span data-ttu-id="72bcc-139">La única solución alternativa es modificar manualmente machine.config. Encontrará este archivo en la ubicación siguiente.</span><span class="sxs-lookup"><span data-stu-id="72bcc-139">The only workaround is to manually edit machine.config. You can locate this file at the following location.</span></span>  
  
```  
%windir%\Microsoft.NET\Framework\v2.0.50727\config\machine.config   
```  
  
 <span data-ttu-id="72bcc-140">Si está ejecutando WCF en un equipo de 64 bits, también debe editar el mismo archivo en esta ubicación.</span><span class="sxs-lookup"><span data-stu-id="72bcc-140">If you are running WCF on a 64-bit machine, you should also edit the same file at this location.</span></span>  
  
```  
%windir%\Microsoft.NET\Framework64\v2.0.50727\config\machine.config   
```  
  
 <span data-ttu-id="72bcc-141">Busque los nodos XML de este archivo que hagan referencia a "System. ServiceModel, version = 2.0.0.0", elimínelos y los nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="72bcc-141">Locate any XML nodes in this file that refer to "System.ServiceModel, Version=2.0.0.0", delete them and any child nodes.</span></span> <span data-ttu-id="72bcc-142">Guarde el archivo y el problema se resolverá volviendo a ejecutar ServiceModelReg.exe.</span><span class="sxs-lookup"><span data-stu-id="72bcc-142">Save the file and re-run ServiceModelReg.exe resolves this problem.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="72bcc-143">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="72bcc-143">Examples</span></span>  
 <span data-ttu-id="72bcc-144">Los ejemplos siguientes muestran cómo usar las opciones más comunes de la herramienta ServiceModelReg.exe.</span><span class="sxs-lookup"><span data-stu-id="72bcc-144">The following examples show how to use the most common options of the ServiceModelReg.exe tool.</span></span>  
  
```  
ServiceModelReg.exe -ia  
  Installs all components  
ServiceModelReg.exe -i -c:httpnamespace -c:etw  
  Installs HTTP namespace reservation and ETW manifests  
ServiceModelReg.exe -u -c:etw  
  Uninstalls ETW manifests  
ServiceModelReg.exe -r  
  Repairs an extended install  
```
