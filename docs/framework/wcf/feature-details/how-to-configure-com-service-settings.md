---
description: Más información acerca de cómo configurar el servicio COM+.
title: Procedimiento para configurar los parámetros de los servicios COM+
ms.date: 03/30/2017
helpviewer_keywords:
- COM+ [WCF], configuring service settings
ms.assetid: f42a55a8-3af8-4394-9fdd-bf12a93780eb
ms.openlocfilehash: 95d58c9db5fa4d3c5e1830401b1ab0651a56d265
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734950"
---
# <a name="how-to-configure-com-service-settings"></a><span data-ttu-id="139d3-103">Procedimiento para configurar los parámetros de los servicios COM+</span><span class="sxs-lookup"><span data-stu-id="139d3-103">How to: Configure COM+ Service Settings</span></span>

<span data-ttu-id="139d3-104">Cuando se agrega o quita una interfaz de aplicaciones mediante la herramienta de configuración de servicio de COM+, la configuración del servicio web se actualiza en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="139d3-104">When an application interface is added or removed by using the COM+ Service Configuration tool, the Web service configuration is updated within the application's configuration file.</span></span> <span data-ttu-id="139d3-105">En el modo hospedado de COM+, el archivo de Application.config se coloca en el directorio raíz de la aplicación (%ProgramFiles%\ComPlus Applications Applications \\ {AppID} es el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="139d3-105">In the COM+ hosted mode, the Application.config file is placed in the Application Root Directory (%PROGRAMFILES%\ComPlus Applications\\{appid} is the default).</span></span> <span data-ttu-id="139d3-106">En cualquiera de los modos hospedados en la web, el archivo Web.config se encuentra en el directorio vroot especificado.</span><span class="sxs-lookup"><span data-stu-id="139d3-106">In either of the Web-hosted modes, the Web.config file is placed in the specified vroot directory.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="139d3-107">La utilización de la firma de los mensajes protege de la alteración de los mensajes entre el cliente y un servidor.</span><span class="sxs-lookup"><span data-stu-id="139d3-107">Message signing should be used to protect against tampering of messages between a client and a server.</span></span> <span data-ttu-id="139d3-108">Además, la utilización del cifrado en el nivel del mensaje o del transporte protege contra la divulgación de información de los mensajes entre un cliente y un servidor.</span><span class="sxs-lookup"><span data-stu-id="139d3-108">Also, message or transport layer encryption should be used to protect against information disclosure from messages between a client and a server.</span></span> <span data-ttu-id="139d3-109">Al igual que con los servicios de Windows Communication Foundation (WCF), debe usar la limitación para limitar el número de llamadas simultáneas, conexiones, instancias y operaciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="139d3-109">As with Windows Communication Foundation (WCF) services, you should use throttling to limit the number of concurrent calls, connections, instances, and pending operations.</span></span> <span data-ttu-id="139d3-110">Así se contribuye a evitar el consumo excesivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="139d3-110">This helps prevent over-consumption of resources.</span></span> <span data-ttu-id="139d3-111">El comportamiento del límite de peticiones se especifica mediante los valores del archivo de configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="139d3-111">Throttling behavior is specified through service configuration file settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="139d3-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="139d3-112">Example</span></span>  

 <span data-ttu-id="139d3-113">Considere un componente que implementa la siguiente interfaz:</span><span class="sxs-lookup"><span data-stu-id="139d3-113">Consider a component that implements the following interface:</span></span>  
  
```csharp
[Guid("C551FBA9-E3AA-4272-8C2A-84BD8D290AC7")]  
public interface IFinances  
{  
    string Debit(string accountNo, double amount);  
    string Credit(string accountNo, double amount);  
}  
```  
  
 <span data-ttu-id="139d3-114">Si el componente se expone como un servicio web, el contrato de servicios correspondiente que se expone, y con el que los clientes deberán ser compatibles, es como sigue:</span><span class="sxs-lookup"><span data-stu-id="139d3-114">If the component is exposed as a Web service, the corresponding service contract that is exposed, and that clients would need to conform to, is as follows:</span></span>  
  
```csharp
[ServiceContract(Session = true,  
Namespace = "http://tempuri.org/C551FBA9-E3AA-4272-8C2A-84BD8D290AC7",  
Name = "IFinances")]  
public interface IFinancesContract : IDisposable  
{  
    [OperationContract]  
    string Debit(string accountNo, double amount);  
    [OperationContract]  
    string Credit(string accountNo, double amount);  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="139d3-115">El IID forma parte del espacio de nombres inicial del contrato.</span><span class="sxs-lookup"><span data-stu-id="139d3-115">IID forms part of the initial namespace for the contract.</span></span>  
  
 <span data-ttu-id="139d3-116">Las aplicaciones cliente que utilizan este servicio deberán ser conformes a este contrato, así como utilizar un enlace compatible con el que se especificó en la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="139d3-116">Client applications that use this service would need to conform to this contract, along with using a binding that is compatible with the one specified in the application configuration.</span></span>  
  
 <span data-ttu-id="139d3-117">El siguiente ejemplo de código muestra un archivo de configuración predeterminado.</span><span class="sxs-lookup"><span data-stu-id="139d3-117">The following code example shows a default configuration file.</span></span> <span data-ttu-id="139d3-118">Al ser un servicio Web de Windows Communication Foundation (WCF), se ajusta al esquema de configuración del modelo de servicio estándar y se puede editar de la misma manera que otros archivos de configuración de servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="139d3-118">Being a Windows Communication Foundation (WCF) Web service, this conforms to the standard service model configuration schema and can be edited in the same way as other WCF services configuration files.</span></span>  
  
 <span data-ttu-id="139d3-119">En las modificaciones típicas se incluye:</span><span class="sxs-lookup"><span data-stu-id="139d3-119">Typical modifications would include:</span></span>  
  
- <span data-ttu-id="139d3-120">Cambiar la dirección del punto de conexión del formulario predeterminado ApplicationName/ComponentName/InterfaceName a un formulario más útil.</span><span class="sxs-lookup"><span data-stu-id="139d3-120">Changing the endpoint address from the default ApplicationName/ComponentName/InterfaceName form to a more usable form.</span></span>  
  
- <span data-ttu-id="139d3-121">Modificar el espacio de nombres del servicio del formulario predeterminado `http://tempuri.org/InterfaceID` a un formulario más relevante.</span><span class="sxs-lookup"><span data-stu-id="139d3-121">Modifying the namespace of the service from the default `http://tempuri.org/InterfaceID` form to a more relevant form.</span></span>  
  
- <span data-ttu-id="139d3-122">Cambiar el punto de conexión para utilizar un enlace de transporte diferente.</span><span class="sxs-lookup"><span data-stu-id="139d3-122">Changing the endpoint to use a different transport binding.</span></span>  
  
     <span data-ttu-id="139d3-123">En el caso de hospedaje en COM+, se utiliza el transporte de las canalizaciones con nombre de manera predeterminada, aunque en su lugar puede utilizarse un transporte fuera de equipo, tipo TCP.</span><span class="sxs-lookup"><span data-stu-id="139d3-123">In the COM+-hosted case, the named pipes transport is used by default, but an off-machine transport like TCP can be used instead.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <bindings>  
            <netNamedPipeBinding>  
                <binding name="comNonTransactionalBinding" />  
                <binding name="comTransactionalBinding" transactionFlow="true" />  
            </netNamedPipeBinding>  
        </bindings>  
        <comContracts>  
            <comContract contract="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"  
                name="IFinances" namespace="http://tempuri.org/C551FBA9-E3AA-4272-8C2A-84BD8D290AC7"  
                requiresSession="true">  
                <exposedMethods>  
                    <add exposedMethod="Debit" />  
                    <add exposedMethod="Credit" />  
                </exposedMethods>  
            </comContract>  
        </comContracts>  
        <services>  
            <service name="{DCDB24CC-0B19-4534-95CD-FBBFF4D67DD9},{C942B840-AD54-4A44-B5F7-928130980AB9}">  
                <endpoint address="IFinances" binding="netNamedPipeBinding" bindingConfiguration="comNonTransactionalBinding"  
                    contract="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}" />  
                <host>  
                    <baseAddresses>  
                        <add baseAddress="net.pipe://localhost/ServiceModelDocSampleApp/ServiceModelDocSample.esFinance" />  
                    </baseAddresses>  
                </host>  
            </service>  
        </services>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="139d3-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="139d3-124">See also</span></span>

- [<span data-ttu-id="139d3-125">Integración con aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="139d3-125">Integrating with COM+ Applications</span></span>](integrating-with-com-plus-applications.md)
