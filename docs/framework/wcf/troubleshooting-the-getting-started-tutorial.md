---
title: Solución de problemas con el tutorial de introducción
ms.date: 03/30/2017
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 5b8cd04ef4d98e522e255e1b7529e848351b2e0c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54695665"
---
# <a name="troubleshooting-the-getting-started-tutorial"></a><span data-ttu-id="27d42-102">Solución de problemas con el tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="27d42-102">Troubleshooting the Getting Started Tutorial</span></span>
<span data-ttu-id="27d42-103">En este tema se enumeran los problemas más comunes que se producen al desarrollar el Tutorial de introducción y se explica cómo resolverlos.</span><span class="sxs-lookup"><span data-stu-id="27d42-103">This topic lists the most common problems encountered when working through the Getting Started Tutorial and how to resolve them.</span></span>  
  
<span data-ttu-id="27d42-104">**No puedo encontrar los archivos de proyecto en el disco duro.**</span><span class="sxs-lookup"><span data-stu-id="27d42-104">**I am unable to find the project files on my hard drive.**</span></span>

 <span data-ttu-id="27d42-105">Visual Studio guarda los archivos de proyecto en c:\users\\<user name>\Documents\\< versión de Visual Studio\>\Projects.</span><span class="sxs-lookup"><span data-stu-id="27d42-105">Visual Studio saves project files in c:\users\\<user name>\Documents\\<Visual Studio version\>\Projects.</span></span>  
  
<span data-ttu-id="27d42-106">**Intentar ejecutar la aplicación de servicio: HTTP no pudo registrar la dirección URL `http://+:8000/ServiceModelSamples/Service/`.** 
 **Su proceso no tiene derechos de acceso a este espacio de nombres.**</span><span class="sxs-lookup"><span data-stu-id="27d42-106">**Attempting to run the service application: HTTP could not register URL `http://+:8000/ServiceModelSamples/Service/`.**
**Your process does not have access rights to this namespace.**</span></span> 

 <span data-ttu-id="27d42-107">El proceso que hospeda un servicio WCF se debe ejecutar con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="27d42-107">The process that hosts a WCF service must be run with Administrative privileges.</span></span> <span data-ttu-id="27d42-108">Si está ejecutando el servicio desde dentro de Visual Studio, debe ejecutar Visual Studio como administrador.</span><span class="sxs-lookup"><span data-stu-id="27d42-108">If you are running the service from inside Visual Studio, you must run Visual Studio as an Administrator.</span></span> <span data-ttu-id="27d42-109">Para ello, haga clic **iniciar**, haga clic en **Visual Studio \< *versión* >**  y seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="27d42-109">To do so click **Start**, right-click **Visual Studio \<*version*>** and select **Run As Administrator**.</span></span> <span data-ttu-id="27d42-110">Si está ejecutando el servicio desde un símbolo del sistema de línea de comandos en una ventana de consola, debe iniciar la ventana de consola como un administrador de una manera similar.</span><span class="sxs-lookup"><span data-stu-id="27d42-110">If you are running the service from a command-line prompt in a console window, you must start the console window as an Administrator in a similar way.</span></span> <span data-ttu-id="27d42-111">Haga clic en **iniciar**, haga clic en **símbolo** y seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="27d42-111">Click **Start**, right-click **Command Prompt** and select **Run As Administrator**.</span></span>  
  
<span data-ttu-id="27d42-112">**Al intentar utilizar la herramienta Svcutil.exe: 'svcutil' no se reconoce como un comando interno o externo, programa operable o archivo por lotes.**</span><span class="sxs-lookup"><span data-stu-id="27d42-112">**Attempting to use the Svcutil.exe tool: 'svcutil' is not recognized as an internal or external command, operable program or batch file.**</span></span>

 <span data-ttu-id="27d42-113">Svcutil.exe debe estar en la ruta de acceso del sistema.</span><span class="sxs-lookup"><span data-stu-id="27d42-113">Svcutil.exe must be in the system path.</span></span> <span data-ttu-id="27d42-114">La solución más fácil es usar el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="27d42-114">The easiest solution is to use the Command Prompt.</span></span> <span data-ttu-id="27d42-115">Haga clic en **iniciar**, seleccione **todos los programas**, **Visual Studio \< *versión*>**,  **Herramientas de Visual Studio**, y **símbolo del sistema para desarrolladores de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="27d42-115">Click **Start**, select **All Programs**, **Visual Studio \<*version*>**, **Visual Studio Tools**, and **Developer Command Prompt for Visual Studio**.</span></span> <span data-ttu-id="27d42-116">Este símbolo se establece la ruta de acceso del sistema en las ubicaciones correctas para todas las herramientas que se incluye como parte de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="27d42-116">This command prompt sets the system path to the correct locations for all tools shipped as part of Visual Studio.</span></span>  

<span data-ttu-id="27d42-117">**No se encuentra el archivo App.config generado por Svcutil.exe.**</span><span class="sxs-lookup"><span data-stu-id="27d42-117">**Unable to find the App.config file generated by Svcutil.exe.**</span></span>

 <span data-ttu-id="27d42-118">El **Agregar elemento existente** cuadro de diálogo solo muestra los archivos con las siguientes extensiones de forma predeterminada:. cs, .resx, .settings, .xsd,. WSDL.</span><span class="sxs-lookup"><span data-stu-id="27d42-118">The **Add Existing Item** dialog only displays files with the following extensions by default: .cs, .resx, .settings, .xsd, .wsdl.</span></span> <span data-ttu-id="27d42-119">Puede especificar que desea ver todos los tipos de archivo seleccionando **todos los archivos (\*.\*)**  en el cuadro de lista desplegable situada en la esquina inferior derecha de la **Agregar elemento existente** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="27d42-119">You can specify that you want to see all file types by selecting **All Files (\*.\*)** in the drop-down list box in the lower right corner of the **Add Existing Item** dialog box.</span></span>  


<span data-ttu-id="27d42-120">**Compilar la aplicación cliente: 'CalculatorClient' no contiene una definición para '\<nombre del método >' y no hay ningún método de extensión '\<nombre del método >' acepte un primer argumento de tipo 'CalculatorClient' se encontró (¿falta un uso de la directiva o un referencia de ensamblado?)**</span><span class="sxs-lookup"><span data-stu-id="27d42-120">**Compiling the client application: 'CalculatorClient' does not contain a definition for '\<method name>' and no extension method '\<method name>' accepting a first argument of type 'CalculatorClient' could be found (are you missing a using directive or an assembly reference?)**</span></span>  

<span data-ttu-id="27d42-121">Sólo los métodos que se marcan con `ServiceOperationAttribute` se exponen al exterior.</span><span class="sxs-lookup"><span data-stu-id="27d42-121">Only those methods that are marked with the `ServiceOperationAttribute` are exposed to the outside world.</span></span> <span data-ttu-id="27d42-122">Si omite el `ServiceOperationAttribute` atributo desde uno de los métodos de la `ICalculator` interfaz, obtendrá este mensaje de error al compilar una aplicación cliente que realiza una llamada a la operación no tiene el atributo.</span><span class="sxs-lookup"><span data-stu-id="27d42-122">If you omitted the `ServiceOperationAttribute` attribute from one of the methods in the `ICalculator` interface, you get this error message when compiling a client application that makes a call to the operation missing the attribute.</span></span>  

<span data-ttu-id="27d42-123">**Compilar la aplicación cliente: El nombre de tipo o espacio de nombres 'CalculatorClient' no se encontró (¿falta un uso de la directiva o una referencia de ensamblado?)**</span><span class="sxs-lookup"><span data-stu-id="27d42-123">**Compiling the client application: The type or namespace name 'CalculatorClient' could not be found (are you missing a using directive or an assembly reference?)**</span></span>

 <span data-ttu-id="27d42-124">Este error se produce si no se agrega el archivo Proxy.cs o Proxy.vb a su proyecto de cliente.</span><span class="sxs-lookup"><span data-stu-id="27d42-124">You get this error if you do not add the Proxy.cs or Proxy.vb file to your client project.</span></span>  

<span data-ttu-id="27d42-125">**Ejecuta al cliente: Excepción no controlada: System.ServiceModel.EndpointNotFoundException: No se pudo conectar a `http://localhost:8000/ServiceModelSamples/Service/CalculatorService`. Código de error TCP 10061: Se realizará ninguna conexión porque el equipo de destino rechazó.**</span><span class="sxs-lookup"><span data-stu-id="27d42-125">**Running the client: Unhandled Exception: System.ServiceModel.EndpointNotFoundException: Could not connect to `http://localhost:8000/ServiceModelSamples/Service/CalculatorService`. TCP error code 10061: No connection could be made because the target machine actively refused it.**</span></span>

<span data-ttu-id="27d42-126">Este error se produce si se ejecuta la aplicación cliente sin ejecutar el servicio.</span><span class="sxs-lookup"><span data-stu-id="27d42-126">This error occurs if you run the client application without running the service.</span></span>  
  
<span data-ttu-id="27d42-127">**Excepción no controlada: System.ServiceModel.Security.SecurityNegotiationException: Negociación de seguridad SOAP con `http://localhost:8000/ServiceModelSamples/Service/CalculatorService` para destino `http://localhost:8000/ServiceModelSamples/Service/CalculatorService` error**</span><span class="sxs-lookup"><span data-stu-id="27d42-127">**Unhandled Exception: System.ServiceModel.Security.SecurityNegotiationException: SOAP security negotiation with `http://localhost:8000/ServiceModelSamples/Service/CalculatorService` for target `http://localhost:8000/ServiceModelSamples/Service/CalculatorService` failed**</span></span>  

<span data-ttu-id="27d42-128">Este error se produce en un equipo unido a un dominio que no dispone de conectividad de red.</span><span class="sxs-lookup"><span data-stu-id="27d42-128">This error occurs on a domain-joined computer that does not have network connectivity.</span></span> <span data-ttu-id="27d42-129">Conecte el equipo a la red o desactive la seguridad para el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="27d42-129">Either connect your computer to the network or turn off security for both the client and the service.</span></span> <span data-ttu-id="27d42-130">En el servicio, modifique el código que crea el WSHttpBinding de la manera siguiente.</span><span class="sxs-lookup"><span data-stu-id="27d42-130">For the service, modify the code that creates the WSHttpBinding to the following.</span></span>  
  
```csharp
// Step 3 of the hosting procedure: Add a service endpoint  
selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
```

<span data-ttu-id="27d42-131">Para el cliente, cambie el  **\<seguridad >** elemento bajo el  **\<enlace >** elemento a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="27d42-131">For the client, change the **\<security>** element under the **\<binding>** element to the following:</span></span>  
  
```xml
<security mode="Node" />  
```  

## <a name="see-also"></a><span data-ttu-id="27d42-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="27d42-132">See also</span></span>
- [<span data-ttu-id="27d42-133">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="27d42-133">Getting Started Tutorial</span></span>](../../../docs/framework/wcf/getting-started-tutorial.md)
- [<span data-ttu-id="27d42-134">Inicio rápido de solución de problemas de WCF</span><span class="sxs-lookup"><span data-stu-id="27d42-134">WCF Troubleshooting Quickstart</span></span>](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)
- [<span data-ttu-id="27d42-135">Solución de problemas de instalación</span><span class="sxs-lookup"><span data-stu-id="27d42-135">Troubleshooting Setup Issues</span></span>](../../../docs/framework/wcf/troubleshooting-setup-issues.md)
