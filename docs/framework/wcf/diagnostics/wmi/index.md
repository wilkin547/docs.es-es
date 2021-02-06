---
description: Más información acerca de cómo usar Instrumental de administración de Windows para diagnósticos
title: Utilización del instrumental de administración de Windows (WMI) para diagnósticos
ms.date: 03/30/2017
ms.assetid: fe48738d-e31b-454d-b5ec-24c85c6bf79a
ms.openlocfilehash: 508422e8e060e608032d7ed22c5736c56c838f10
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99653880"
---
# <a name="using-windows-management-instrumentation-for-diagnostics"></a><span data-ttu-id="055f1-103">Utilización del instrumental de administración de Windows (WMI) para diagnósticos</span><span class="sxs-lookup"><span data-stu-id="055f1-103">Using Windows Management Instrumentation for Diagnostics</span></span>

<span data-ttu-id="055f1-104">Windows Communication Foundation (WCF) expone datos de inspección de un servicio en tiempo de ejecución a través de un proveedor de WCF Instrumental de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="055f1-104">Windows Communication Foundation (WCF) exposes inspection data of a service at runtime through a WCF Windows Management Instrumentation (WMI) provider.</span></span>  
  
## <a name="enabling-wmi"></a><span data-ttu-id="055f1-105">Habilitar WMI</span><span class="sxs-lookup"><span data-stu-id="055f1-105">Enabling WMI</span></span>  

 <span data-ttu-id="055f1-106">WMI es la implementación de Microsoft del estándar Web-Based Enterprise Management (WBEM).</span><span class="sxs-lookup"><span data-stu-id="055f1-106">WMI is Microsoft's implementation of the Web-Based Enterprise Management (WBEM) standard.</span></span> <span data-ttu-id="055f1-107">Para obtener más información sobre el SDK de WMI, vea [instrumental de administración de Windows](/windows/desktop/WmiSdk/wmi-start-page).</span><span class="sxs-lookup"><span data-stu-id="055f1-107">For more information about the WMI SDK, see [Windows Management Instrumentation](/windows/desktop/WmiSdk/wmi-start-page).</span></span> <span data-ttu-id="055f1-108">WBEM es un estándar de la industria para saber cómo exponen las aplicaciones la instrumentación de administración a las herramientas de administración externas.</span><span class="sxs-lookup"><span data-stu-id="055f1-108">WBEM is an industry standard for how applications expose management instrumentation to external management tools.</span></span>  
  
 <span data-ttu-id="055f1-109">Un proveedor de WMI es un componente que expone la instrumentación en el tiempo de ejecución a través de una interfaz compatible con WBEM.</span><span class="sxs-lookup"><span data-stu-id="055f1-109">A WMI provider is a component that exposes instrumentation at runtime through a WBEM-compatible interface.</span></span> <span data-ttu-id="055f1-110">Está compuesto de un conjunto de objetos WMI con pares atributo/valor.</span><span class="sxs-lookup"><span data-stu-id="055f1-110">It consists of a set of WMI objects that have attribute/value pairs.</span></span> <span data-ttu-id="055f1-111">Los pares pueden ser de varios tipos simples.</span><span class="sxs-lookup"><span data-stu-id="055f1-111">Pairs can be of a number of simple types.</span></span> <span data-ttu-id="055f1-112">Las herramientas de administración pueden conectarse a los servicios a través de la interfaz en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="055f1-112">Management tools can connect to the services through the interface at runtime.</span></span> <span data-ttu-id="055f1-113">WCF expone atributos de servicios como direcciones, enlaces, comportamientos y agentes de escucha.</span><span class="sxs-lookup"><span data-stu-id="055f1-113">WCF exposes attributes of services such as addresses, bindings, behaviors, and listeners.</span></span>  
  
 <span data-ttu-id="055f1-114">El proveedor de WMI integrado puede activarse en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="055f1-114">The built-in WMI provider can be activated in the configuration file of the application.</span></span> <span data-ttu-id="055f1-115">Esto se hace a través del `wmiProviderEnabled` atributo de [\<diagnostics>](../../../configure-apps/file-schema/wcf/diagnostics.md) en la [\<system.serviceModel>](../../../configure-apps/file-schema/wcf/system-servicemodel.md) sección, tal y como se muestra en la configuración del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="055f1-115">This is done through the `wmiProviderEnabled` attribute of the [\<diagnostics>](../../../configure-apps/file-schema/wcf/diagnostics.md) in the [\<system.serviceModel>](../../../configure-apps/file-schema/wcf/system-servicemodel.md) section, as shown in the following sample configuration.</span></span>  
  
```xml  
<system.serviceModel>  
    …  
    <diagnostics wmiProviderEnabled="true" />  
    …  
</system.serviceModel>  
```  
  
 <span data-ttu-id="055f1-116">Esta entrada de configuración expone una interfaz WMI.</span><span class="sxs-lookup"><span data-stu-id="055f1-116">This configuration entry exposes a WMI interface.</span></span> <span data-ttu-id="055f1-117">Ahora, las aplicaciones de administración pueden establecer la conexión a través de esta interfaz y obtener acceso a la instrumentación de administración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="055f1-117">Management applications can now connect through this interface and access the management instrumentation of the application.</span></span>  
  
## <a name="accessing-wmi-data"></a><span data-ttu-id="055f1-118">Obtener acceso a datos WMI</span><span class="sxs-lookup"><span data-stu-id="055f1-118">Accessing WMI Data</span></span>  

 <span data-ttu-id="055f1-119">Puede obtenerse acceso a los datos WMI de maneras muy distintas.</span><span class="sxs-lookup"><span data-stu-id="055f1-119">WMI data can be accessed in many different ways.</span></span> <span data-ttu-id="055f1-120">Microsoft proporciona API de WMI para scripts, aplicaciones Visual Basic, aplicaciones de C++ y el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="055f1-120">Microsoft provides WMI APIs for scripts, Visual Basic applications, C++ applications, and the .NET Framework.</span></span> <span data-ttu-id="055f1-121">Para obtener más información, vea [usar WMI](/windows/win32/wmisdk/using-wmi).</span><span class="sxs-lookup"><span data-stu-id="055f1-121">For more information, see [Using WMI](/windows/win32/wmisdk/using-wmi).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="055f1-122">Si utiliza los métodos proporcionados por .NET Framework para tener acceso mediante programación a los datos de WMI, debe tener en cuenta que tales métodos pueden iniciar excepciones una vez establecida la conexión.</span><span class="sxs-lookup"><span data-stu-id="055f1-122">If you use the .NET Framework provided methods to programmatically access WMI data, you should be aware that such methods may throw exceptions when the connection is established.</span></span> <span data-ttu-id="055f1-123">La conexión no se establece durante la construcción de la instancia <xref:System.Management.ManagementObject>, sino con la primera solicitud que implique el intercambio real de datos.</span><span class="sxs-lookup"><span data-stu-id="055f1-123">The connection is not established during the construction of the <xref:System.Management.ManagementObject> instance, but on the first request involving actual data exchange.</span></span> <span data-ttu-id="055f1-124">Por lo tanto, utilice un bloque `try..catch` para detectar las posibles excepciones.</span><span class="sxs-lookup"><span data-stu-id="055f1-124">Therefore, you should use a `try..catch` block to catch the possible exceptions.</span></span>  
  
 <span data-ttu-id="055f1-125">Puede cambiar la traza y el nivel de registro de mensajes, así como las opciones de registro de mensajes para el origen de traza de la traza `System.ServiceModel` en WMI.</span><span class="sxs-lookup"><span data-stu-id="055f1-125">You can change the trace and message logging level, as well as message logging options for the `System.ServiceModel` trace source in WMI.</span></span> <span data-ttu-id="055f1-126">Esto puede hacerse mediante el acceso a la instancia de [AppDomainInfo](appdomaininfo.md) , que expone estas propiedades booleanas: `LogMessagesAtServiceLevel` , `LogMessagesAtTransportLevel` , `LogMalformedMessages` y `TraceLevel` .</span><span class="sxs-lookup"><span data-stu-id="055f1-126">This can be done by accessing the [AppDomainInfo](appdomaininfo.md) instance, which exposes these Boolean properties: `LogMessagesAtServiceLevel`, `LogMessagesAtTransportLevel`, `LogMalformedMessages`, and `TraceLevel`.</span></span> <span data-ttu-id="055f1-127">Por consiguiente, si configura un agente de escucha de traza para el registro de mensajes, pero define estas opciones en `false`, en la configuración, puede cambiarlas después a `true`, una vez se esté ejecutando la aplicación.</span><span class="sxs-lookup"><span data-stu-id="055f1-127">Therefore, if you configure a trace listener for message logging, but set these options to `false` in configuration, you can later change them to `true` when the application is running.</span></span> <span data-ttu-id="055f1-128">Esto habilitará de manera efectiva el registro de mensajes en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="055f1-128">This will effectively enable message logging at runtime.</span></span> <span data-ttu-id="055f1-129">De igual forma, si habilita el registro de mensajes en su archivo de configuración, puede deshabilitarlo en el tiempo de ejecución mediante WMI.</span><span class="sxs-lookup"><span data-stu-id="055f1-129">Similarly, if you enable message logging in your configuration file, you can disable it at runtime using WMI.</span></span>  
  
 <span data-ttu-id="055f1-130">Debe tener en cuenta que si en el archivo de configuración no se especifica ningún agente de escucha de traza de registro de mensajes para el registro de mensajes, o no se especifica ningún agente de escucha de traza de `System.ServiceModel`, no se aplica ninguno de sus cambios, aunque WMI los acepte.</span><span class="sxs-lookup"><span data-stu-id="055f1-130">You should be aware that if no message logging trace listeners for message logging, or no `System.ServiceModel` trace listeners for tracing are specified in the configuration file, none of your changes are taken into effect, even though the changes are accepted by WMI.</span></span> <span data-ttu-id="055f1-131">Para obtener más información sobre cómo configurar correctamente los agentes de escucha respectivos, vea [configurar el registro de mensajes](../configuring-message-logging.md) y configurar el [seguimiento](../tracing/configuring-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="055f1-131">For more information on properly setting up the respective listeners, see [Configuring Message Logging](../configuring-message-logging.md) and [Configuring Tracing](../tracing/configuring-tracing.md).</span></span> <span data-ttu-id="055f1-132">El nivel de seguimiento de traza, del resto de los orígenes de traza de traza, especificado por la configuración es efectivo cuando se inicia la aplicación, y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="055f1-132">The trace level of all other trace sources specified by configuration is effective when the application starts, and cannot be changed.</span></span>  
  
 <span data-ttu-id="055f1-133">WCF expone un `GetOperationCounterInstanceName` método para el scripting.</span><span class="sxs-lookup"><span data-stu-id="055f1-133">WCF exposes a `GetOperationCounterInstanceName` method for scripting.</span></span> <span data-ttu-id="055f1-134">Este método devuelve un nombre de instancia del contador de rendimiento si le proporciona un nombre de operación.</span><span class="sxs-lookup"><span data-stu-id="055f1-134">This method returns a performance counter instance name if you provide it with an operation name.</span></span> <span data-ttu-id="055f1-135">Sin embargo, no valida la entrada.</span><span class="sxs-lookup"><span data-stu-id="055f1-135">However, it does not validate your input.</span></span> <span data-ttu-id="055f1-136">Por lo tanto, si proporciona un nombre de operación incorrecto, se devuelve un nombre de contador incorrecto.</span><span class="sxs-lookup"><span data-stu-id="055f1-136">Therefore, if you provide an incorrect operation name, an incorrect counter name is returned.</span></span>  
  
 <span data-ttu-id="055f1-137">La `OutgoingChannel` propiedad de la `Service` instancia no cuenta los canales abiertos por un servicio para conectarse a otro servicio, si el cliente de WCF al servicio de destino no se crea dentro del `Service` método.</span><span class="sxs-lookup"><span data-stu-id="055f1-137">The `OutgoingChannel` property of the `Service` instance does not count channels opened by a service to connect to another service, if the WCF client to the destination service is not created within the `Service` method.</span></span>  
  
 <span data-ttu-id="055f1-138">**PRECAUCIÓN** WMI solo admite un <xref:System.TimeSpan> valor de hasta 3 separadores decimales.</span><span class="sxs-lookup"><span data-stu-id="055f1-138">**Caution** WMI only supports a <xref:System.TimeSpan> value up to 3 decimal points.</span></span> <span data-ttu-id="055f1-139">Por ejemplo, si su servicio establece una de sus propiedades en <xref:System.TimeSpan.MaxValue>, su valor se trunca pasados los 3 separadores decimales cuando se ve mediante WMI.</span><span class="sxs-lookup"><span data-stu-id="055f1-139">For example, if your service sets one of its properties to <xref:System.TimeSpan.MaxValue>, its value is truncated after 3 decimal points when viewed through WMI.</span></span>  
  
## <a name="security"></a><span data-ttu-id="055f1-140">Seguridad</span><span class="sxs-lookup"><span data-stu-id="055f1-140">Security</span></span>  

 <span data-ttu-id="055f1-141">Dado que el proveedor de WCF WMI permite la detección de servicios en un entorno, debe extremar las precauciones para concederle acceso.</span><span class="sxs-lookup"><span data-stu-id="055f1-141">Because the WCF WMI provider allows the discovery of services in an environment, you should exercise extreme caution for granting access to it.</span></span> <span data-ttu-id="055f1-142">Si suaviza el acceso predeterminado exclusivo a los administradores, puede permitir el acceso de partes menos fiables a los datos confidenciales de su entorno.</span><span class="sxs-lookup"><span data-stu-id="055f1-142">If you relax the default administrator-only access, you may allow less-trusted parties access to sensitive data in your environment.</span></span> <span data-ttu-id="055f1-143">En concreto, si suaviza los permisos de acceso remoto a WMI, pueden producirse ataques por inundación.</span><span class="sxs-lookup"><span data-stu-id="055f1-143">Specifically, if you loosen permissions on remote WMI access, flooding attacks can occur.</span></span> <span data-ttu-id="055f1-144">Si un proceso se inunda por un exceso de solicitudes de WMI, su rendimiento puede degradarse.</span><span class="sxs-lookup"><span data-stu-id="055f1-144">If a process is flooded by excessive WMI requests, its performance can be degraded.</span></span>  
  
 <span data-ttu-id="055f1-145">Además, si suaviza los permisos de acceso para el archivo MOF, partes menos fiables pueden manipular el comportamiento de WMI y modificar los objetos que se cargan en el esquema de WMI.</span><span class="sxs-lookup"><span data-stu-id="055f1-145">In addition, if you relax access permissions for the MOF file, less-trusted parties can manipulate the behavior of WMI and alter the objects that are loaded in the WMI schema.</span></span> <span data-ttu-id="055f1-146">Por ejemplo, pueden quitarse campos de modo que se oculten datos críticos al administrador, que no se puedan rellenar campos, o provocar que se agreguen excepciones al archivo.</span><span class="sxs-lookup"><span data-stu-id="055f1-146">For example, fields can be removed such that critical data is concealed from the administrator or that fields that do not populate or cause exceptions are added to the file.</span></span>  
  
 <span data-ttu-id="055f1-147">De forma predeterminada, el proveedor de WMI de WCF concede el permiso "ejecutar método", "escritura de proveedor" y "habilitar cuenta" para el administrador y el permiso "habilitar cuenta" para ASP.NET, servicio local y servicio de red.</span><span class="sxs-lookup"><span data-stu-id="055f1-147">By default, the WCF WMI provider grants "execute method", "provider write", and "enable account" permission for Administrator, and "enable account" permission for ASP.NET, Local Service and Network Service.</span></span> <span data-ttu-id="055f1-148">En concreto, en plataformas que no son de Windows Vista, la cuenta ASP.NET tiene acceso de lectura al espacio de nombres de ServiceModel de WMI.</span><span class="sxs-lookup"><span data-stu-id="055f1-148">In particular, on non-Windows Vista platforms, the ASP.NET account has read access to the WMI ServiceModel namespace.</span></span> <span data-ttu-id="055f1-149">Si no desea conceder estos privilegios a un grupo de usuarios determinado, debe desactivar el proveedor de WMI (deshabilitado de manera predeterminada), o deshabilitar el acceso para el grupo de usuarios concreto.</span><span class="sxs-lookup"><span data-stu-id="055f1-149">If you do not want to grant these privileges to a particular user group, you should either deactivate the WMI provider (it is disabled by default), or disable access for the specific user group.</span></span>  
  
 <span data-ttu-id="055f1-150">Además, al intentar habilitar WMI a través de la configuración, WMI puede no estar habilitada debido a un privilegio de usuario insuficiente.</span><span class="sxs-lookup"><span data-stu-id="055f1-150">In addition, when you attempt to enable WMI through configuration, WMI may not be enabled due to insufficient user privilege.</span></span> <span data-ttu-id="055f1-151">No obstante, no se escribe ningún evento en el registro de eventos que registre este error.</span><span class="sxs-lookup"><span data-stu-id="055f1-151">However, no event is written to the event log to record this failure.</span></span>  
  
 <span data-ttu-id="055f1-152">Para modificar los niveles de privilegio del usuario, siga los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="055f1-152">To modify user privilege levels, use the following steps.</span></span>  
  
1. <span data-ttu-id="055f1-153">Haga clic en Inicio y, a continuación, en ejecutar y escriba **compmgmt. msc**.</span><span class="sxs-lookup"><span data-stu-id="055f1-153">Click Start and then Run and type **compmgmt.msc**.</span></span>  
  
2. <span data-ttu-id="055f1-154">Haga clic con el botón secundario en **servicios y controles de aplicación/WMI** para seleccionar **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="055f1-154">Right-click **Services and Application/WMI Controls** to select **Properties**.</span></span>  
  
3. <span data-ttu-id="055f1-155">Seleccione la pestaña **seguridad** y navegue hasta el espacio de nombres **root/ServiceModel** .</span><span class="sxs-lookup"><span data-stu-id="055f1-155">Select the **Security** Tab, and navigate to the **Root/ServiceModel** namespace.</span></span> <span data-ttu-id="055f1-156">Haga clic en el botón **seguridad** .</span><span class="sxs-lookup"><span data-stu-id="055f1-156">Click the **Security** button.</span></span>  
  
4. <span data-ttu-id="055f1-157">Seleccione el grupo o usuario específico al que desea controlar el acceso y use la casilla **permitir** o **denegar** para configurar los permisos.</span><span class="sxs-lookup"><span data-stu-id="055f1-157">Select the specific group or user that you want to control access and use the **Allow** or **Deny** checkbox to configure permissions.</span></span>  
  
## <a name="granting-wcf-wmi-registration-permissions-to-additional-users"></a><span data-ttu-id="055f1-158">Conceder permisos de registro de WCF WMI a usuarios adicionales</span><span class="sxs-lookup"><span data-stu-id="055f1-158">Granting WCF WMI Registration Permissions to Additional Users</span></span>  

 <span data-ttu-id="055f1-159">WCF expone datos de administración a WMI.</span><span class="sxs-lookup"><span data-stu-id="055f1-159">WCF exposes management data to WMI.</span></span> <span data-ttu-id="055f1-160">Para ello, hospeda un proveedor WMI en proceso, que a veces se denomina "proveedor desacoplado".</span><span class="sxs-lookup"><span data-stu-id="055f1-160">It does so by hosting an in-process WMI provider, sometimes called a "decoupled provider".</span></span> <span data-ttu-id="055f1-161">La cuenta que registra este proveedor debe tener los permisos apropiados para poder exponer los datos de administración.</span><span class="sxs-lookup"><span data-stu-id="055f1-161">For the management data to be exposed, the account that registers this provider must have the appropriate permissions.</span></span> <span data-ttu-id="055f1-162">En Windows, solo un pequeño conjunto de cuentas privilegiadas pueden registrar proveedores desacoplados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="055f1-162">In Windows, only a small set of privileged accounts can register decoupled providers by default.</span></span> <span data-ttu-id="055f1-163">Esto supone un problema, ya que los usuarios normalmente desean exponer los datos WMI de un servicio WCF que se está ejecutando bajo una cuenta que no se encuentra en el conjunto predeterminado.</span><span class="sxs-lookup"><span data-stu-id="055f1-163">This is a problem because users commonly want to expose WMI data from a WCF service running under an account that is not in the default set.</span></span>  
  
 <span data-ttu-id="055f1-164">Para proporcionar este acceso, el administrador debe conceder los permisos siguientes a la cuenta adicional en el orden siguiente:</span><span class="sxs-lookup"><span data-stu-id="055f1-164">To provide this access, an administrator must grant the following permissions to the additional account in the following order:</span></span>  
  
1. <span data-ttu-id="055f1-165">Permiso para tener acceso al espacio de nombres de WMI de WCF.</span><span class="sxs-lookup"><span data-stu-id="055f1-165">Permission to access to the WCF WMI Namespace.</span></span>  
  
2. <span data-ttu-id="055f1-166">Permiso para registrar el proveedor desacoplado WMI de WCF.</span><span class="sxs-lookup"><span data-stu-id="055f1-166">Permission to register the WCF Decoupled WMI Provider.</span></span>  
  
#### <a name="to-grant-wmi-namespace-access-permission"></a><span data-ttu-id="055f1-167">Para conceder permiso de acceso al espacio de nombres WMI</span><span class="sxs-lookup"><span data-stu-id="055f1-167">To grant WMI namespace access permission</span></span>  
  
1. <span data-ttu-id="055f1-168">Ejecute el siguiente script de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="055f1-168">Run the following PowerShell script.</span></span>  
  
    ```powershell  
    write-host ""  
    write-host "Granting Access to root/servicemodel WMI namespace to built in users group"  
    write-host ""  
  
    # Create the binary representation of the permissions to grant in SDDL  
    $newPermissions = "O:BAG:BAD:P(A;CI;CCDCLCSWRPWPRCWD;;;BA)(A;CI;CC;;;NS)(A;CI;CC;;;LS)(A;CI;CC;;;BU)"  
    $converter = new-object system.management.ManagementClass Win32_SecurityDescriptorHelper  
    $binarySD = $converter.SDDLToBinarySD($newPermissions)  
    $convertedPermissions = ,$binarySD.BinarySD  
  
    # Get the object used to set the permissions  
    $security = gwmi -namespace root/servicemodel -class __SystemSecurity  
  
    # Get and output the current settings  
    $binarySD = @($null)  
    $result = $security.PsBase.InvokeMethod("GetSD",$binarySD)  
  
    $outsddl = $converter.BinarySDToSDDL($binarySD[0])  
    write-host "Previous ACL: "$outsddl.SDDL  
  
    # Change the Access Control List (ACL) using SDDL  
    $result = $security.PsBase.InvokeMethod("SetSD",$convertedPermissions)
  
    # Get and output the current settings  
    $binarySD = @($null)  
    $result = $security.PsBase.InvokeMethod("GetSD",$binarySD)  
  
    $outsddl = $converter.BinarySDToSDDL($binarySD[0])  
    write-host "New ACL:      "$outsddl.SDDL  
    write-host ""  
    ```  
  
     <span data-ttu-id="055f1-169">Este script de PowerShell usa el lenguaje de definición de descriptores de seguridad (SDDL) para conceder al Built-In el grupo de usuarios acceso al espacio de nombres WMI "root/ServiceModel".</span><span class="sxs-lookup"><span data-stu-id="055f1-169">This PowerShell script uses Security Descriptor Definition Language (SDDL) to grant the Built-In Users group access to the "root/servicemodel" WMI namespace.</span></span> <span data-ttu-id="055f1-170">Especifica las ACL siguientes:</span><span class="sxs-lookup"><span data-stu-id="055f1-170">It specifies the following ACLs:</span></span>  
  
    - <span data-ttu-id="055f1-171">Cuenta predefinida Administrador (BA) - Ya tenía acceso.</span><span class="sxs-lookup"><span data-stu-id="055f1-171">Built-In Administrator (BA) - Already Had Access.</span></span>  
  
    - <span data-ttu-id="055f1-172">Servicio de red (NS) - Ya tenía acceso.</span><span class="sxs-lookup"><span data-stu-id="055f1-172">Network Service (NS) - Already Had Access.</span></span>  
  
    - <span data-ttu-id="055f1-173">Sistema local (LS) - Ya tenía acceso.</span><span class="sxs-lookup"><span data-stu-id="055f1-173">Local System (LS) - Already Had Access.</span></span>  
  
    - <span data-ttu-id="055f1-174">Usuarios integrado - El grupo al que se va a conceder acceso.</span><span class="sxs-lookup"><span data-stu-id="055f1-174">Built-In Users - The group to grant access to.</span></span>  
  
#### <a name="to-grant-provider-registration-access"></a><span data-ttu-id="055f1-175">Para conceder acceso de registro de proveedores</span><span class="sxs-lookup"><span data-stu-id="055f1-175">To grant provider registration access</span></span>  
  
1. <span data-ttu-id="055f1-176">Ejecute el siguiente script de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="055f1-176">Run the following PowerShell script.</span></span>  
  
    ```powershell  
    write-host ""  
    write-host "Granting WCF provider registration access to built in users group"  
    write-host ""  
    # Set security on ServiceModel provider  
    $provider = get-WmiObject -namespace "root\servicemodel" __Win32Provider  
  
    write-host "Previous ACL: "$provider.SecurityDescriptor  
    $result = $provider.SecurityDescriptor = "O:BUG:BUD:(A;;0x1;;;BA)(A;;0x1;;;NS)(A;;0x1;;;LS)(A;;0x1;;;BU)"  
  
    # Commit the changes and display it to the console  
    $result = $provider.Put()  
    write-host "New ACL:      "$provider.SecurityDescriptor  
    write-host ""  
    ```  
  
### <a name="granting-access-to-arbitrary-users-or-groups"></a><span data-ttu-id="055f1-177">Conceder acceso a usuarios o grupos arbitrarios</span><span class="sxs-lookup"><span data-stu-id="055f1-177">Granting Access to Arbitrary Users or Groups</span></span>  

 <span data-ttu-id="055f1-178">En el ejemplo de esta sección se conceden privilegios de registro de proveedores WMI a todos los usuarios locales.</span><span class="sxs-lookup"><span data-stu-id="055f1-178">The example in this section grants WMI Provider registration privileges to all local users.</span></span> <span data-ttu-id="055f1-179">Si desea conceder acceso a un usuario o grupo que no está integrado, debe obtener el identificador de seguridad (SID) del usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="055f1-179">If you want to grant access to a user or group that is not built in, then you must obtain that user or group's Security Identifier (SID).</span></span> <span data-ttu-id="055f1-180">No hay ninguna forma sencilla de obtener el SID de un usuario arbitrario.</span><span class="sxs-lookup"><span data-stu-id="055f1-180">There is no simple way to get the SID for an arbitrary user.</span></span> <span data-ttu-id="055f1-181">Un método consiste en iniciar sesión como el usuario deseado y, a continuación, usar el comando shell siguiente.</span><span class="sxs-lookup"><span data-stu-id="055f1-181">One method is to log on as the desired user and then issue the following shell command.</span></span>  
  
```console
Whoami /user  
```  
  
 <span data-ttu-id="055f1-182">Esto proporciona el SID del usuario actual, pero este método no se puede usar para obtener el SID de un usuario arbitrario.</span><span class="sxs-lookup"><span data-stu-id="055f1-182">This provides the SID of the current user, but this method cannot be used to get the SID on any arbitrary user.</span></span> <span data-ttu-id="055f1-183">Otro método para obtener el SID es usar la herramienta de [getsid.exe](/windows/win32/wmisdk/using-wmi) de las herramientas del kit de recursos de Windows 2000 para las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="055f1-183">Another method to get the SID is to use the [getsid.exe](/windows/win32/wmisdk/using-wmi) tool from the Windows 2000 Resource Kit Tools for administrative tasks.</span></span> <span data-ttu-id="055f1-184">Esta herramienta compara el SID de dos usuarios (locales o del dominio), y como efecto secundario imprime ambos SID en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="055f1-184">This tool compares the SID of two users (local or domain), and as a side effect prints the two SIDs to the command line.</span></span> <span data-ttu-id="055f1-185">Para obtener más información, consulte [SID conocidos](https://support.microsoft.com/help/243330/well-known-security-identifiers-in-windows-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="055f1-185">For more information, see [Well Known SIDs](https://support.microsoft.com/help/243330/well-known-security-identifiers-in-windows-operating-systems).</span></span>  
  
## <a name="accessing-remote-wmi-object-instances"></a><span data-ttu-id="055f1-186">Acceso a las instancias de objeto de WMI remotas</span><span class="sxs-lookup"><span data-stu-id="055f1-186">Accessing Remote WMI Object Instances</span></span>  

 <span data-ttu-id="055f1-187">Si necesita tener acceso a instancias de WCF WMI en un equipo remoto, debe habilitar la privacidad de paquetes en las herramientas que usa para el acceso.</span><span class="sxs-lookup"><span data-stu-id="055f1-187">If you need to access WCF WMI instances on a remote machine, you must enable packet privacy on the tools that you use for access.</span></span> <span data-ttu-id="055f1-188">La siguiente sección describe cómo conseguirlo mediante CIM Studio de WMI, la Herramienta de comprobación del instrumental de administración de Windows, y .NET SDK 2.0.</span><span class="sxs-lookup"><span data-stu-id="055f1-188">The following section describes how to achieve these using the WMI CIM Studio, Windows Management Instrumentation Tester, as well as .NET SDK 2.0.</span></span>  
  
### <a name="wmi-cim-studio"></a><span data-ttu-id="055f1-189">CIM Studio de WMI</span><span class="sxs-lookup"><span data-stu-id="055f1-189">WMI CIM Studio</span></span>

<span data-ttu-id="055f1-190">Si ha instalado las herramientas administrativas de WMI, puede utilizar WMI CIM Studio para tener acceso a las instancias de WMI.</span><span class="sxs-lookup"><span data-stu-id="055f1-190">If you've installed WMI Administrative Tools, you can use the WMI CIM Studio to access WMI instances.</span></span> <span data-ttu-id="055f1-191">Las herramientas se encuentran en la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="055f1-191">The tools are in the following folder:</span></span>
  
<span data-ttu-id="055f1-192">*%windir%\Program Files\WMI Tools\\*</span><span class="sxs-lookup"><span data-stu-id="055f1-192">*%windir%\Program Files\WMI Tools\\*</span></span>
  
1. <span data-ttu-id="055f1-193">En la ventana **conectar con espacio de nombres:** , escriba **root\ServiceModel** y haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="055f1-193">In the **Connect to namespace:** window, type **root\ServiceModel** and click **OK.**</span></span>  
  
2. <span data-ttu-id="055f1-194">En la ventana de **Inicio de sesión de WMI CIM Studio** , haga clic en el botón **Opciones >>** para expandir la ventana.</span><span class="sxs-lookup"><span data-stu-id="055f1-194">In the **WMI CIM Studio Login** window, click the **Options >>** button to expand the window.</span></span> <span data-ttu-id="055f1-195">Seleccione **privacidad de paquete** para el **nivel de autenticación** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="055f1-195">Select **Packet privacy** for **Authentication level**, and click **OK**.</span></span>  
  
### <a name="windows-management-instrumentation-tester"></a><span data-ttu-id="055f1-196">Herramienta de comprobación del instrumental de administración de Windows</span><span class="sxs-lookup"><span data-stu-id="055f1-196">Windows Management Instrumentation Tester</span></span>  

 <span data-ttu-id="055f1-197">Windows instala esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="055f1-197">This tool is installed by Windows.</span></span> <span data-ttu-id="055f1-198">Para ejecutarlo, inicie una consola de comandos escribiendo **cmd.exe** en el cuadro de diálogo **iniciar/ejecutar** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="055f1-198">To run it, launch a command console by typing **cmd.exe** in the **Start/Run** dialog box and click **OK**.</span></span> <span data-ttu-id="055f1-199">A continuación, escriba **wbemtest.exe** en la ventana de comandos.</span><span class="sxs-lookup"><span data-stu-id="055f1-199">Then, type **wbemtest.exe** in the command window.</span></span> <span data-ttu-id="055f1-200">Se inicia la Herramienta de comprobación del instrumental de administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="055f1-200">The Windows Management Instrumentation Tester tool is then launched.</span></span>  
  
1. <span data-ttu-id="055f1-201">Haga clic en el botón **conectar** situado en la esquina superior derecha de la ventana.</span><span class="sxs-lookup"><span data-stu-id="055f1-201">Click the **Connect** button on the top right corner of the window.</span></span>  
  
2. <span data-ttu-id="055f1-202">En la nueva ventana, escriba **root\ServiceModel** en el campo **espacio de nombres** y seleccione privacidad de **paquete** para el nivel de **autenticación**.</span><span class="sxs-lookup"><span data-stu-id="055f1-202">In the new window, enter **root\ServiceModel** for the **Namespace** field, and select **Packet privacy** for **Authentication level**.</span></span> <span data-ttu-id="055f1-203">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="055f1-203">Click **Connect**.</span></span>  
  
### <a name="using-managed-code"></a><span data-ttu-id="055f1-204">Utilización del código administrado</span><span class="sxs-lookup"><span data-stu-id="055f1-204">Using Managed Code</span></span>  

 <span data-ttu-id="055f1-205">También puede obtener acceso a instancias WMI remotas mediante programación utilizando las clases proporcionadas por el espacio de nombres <xref:System.Management>.</span><span class="sxs-lookup"><span data-stu-id="055f1-205">You can also access remote WMI instances programmatically by using classes provided by the <xref:System.Management> namespace.</span></span> <span data-ttu-id="055f1-206">En el ejemplo de código siguiente se muestra cómo utilizar este recurso.</span><span class="sxs-lookup"><span data-stu-id="055f1-206">The following code sample demonstrates how to do this.</span></span>  
  
```csharp
String wcfNamespace = $@"\\{this.serviceMachineName}\Root\ServiceModel");
  
ConnectionOptions connection = new ConnectionOptions();  
connection.Authentication = AuthenticationLevel.PacketPrivacy;  
ManagementScope scope = new ManagementScope(this.wcfNamespace, connection);  
```
