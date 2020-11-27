---
title: Procedimiento para crear un punto de conexión de servicio en la configuración
description: Obtenga información sobre cómo agregar extremos para un servicio WCF mediante un archivo de configuración que contenga direcciones absolutas y relativas.
ms.date: 06/16/2016
ms.assetid: f474e25d-2a27-4f31-84c5-395c442b8e70
ms.openlocfilehash: aa8dce18a39b44c2c56d072a81699d1bc1e7d7da
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286427"
---
# <a name="how-to-create-a-service-endpoint-in-configuration"></a><span data-ttu-id="15540-103">Procedimiento para crear un punto de conexión de servicio en la configuración</span><span class="sxs-lookup"><span data-stu-id="15540-103">How to: Create a Service Endpoint in Configuration</span></span>

<span data-ttu-id="15540-104">Los extremos proporcionan a los clientes acceso a la funcionalidad que ofrece un servicio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="15540-104">Endpoints provide clients with access to the functionality a Windows Communication Foundation (WCF) service offers.</span></span> <span data-ttu-id="15540-105">Puede definir uno o más extremos para un servicio usando una combinación de direcciones de extremo relativas y absolutas; si no se define ninguno, el tiempo de ejecución proporciona varios de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="15540-105">You can define one or more endpoints for a service by using a combination of relative and absolute endpoint addresses, or if you do not define any service endpoints, the runtime provides some by default for you.</span></span> <span data-ttu-id="15540-106">En este tema se muestra cómo agregar extremos mediante un archivo de configuración que contiene tanto direcciones absolutas como relativas.</span><span class="sxs-lookup"><span data-stu-id="15540-106">This topic shows how to add endpoints using a configuration file that contain both relative and absolute addresses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15540-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15540-107">Example</span></span>  

 <span data-ttu-id="15540-108">La siguiente configuración de servicio especifica una dirección base y cinco extremos.</span><span class="sxs-lookup"><span data-stu-id="15540-108">The following service configuration specifies a base address and five endpoints.</span></span>  
  
```xml  
<configuration>  
  
  <appSettings>  
    <!-- use appSetting to configure base address provided by host -->  
    <add key="baseAddress" value="http://localhost:8000/servicemodelsamples/service" />  
  </appSettings>  
  
  <system.serviceModel>  
    <services>  
    <!-- This section is optional with the default configuration introduced in .NET Framework 4. -->  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
          </baseAddresses>  
        </host>  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="/test"  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="http://localhost:8001/hello/servicemodelsamples"  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
                  binding="netTcpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is another relative address exposed at   
             http://localhost:8000/ServiceModelSamples/service/mex -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="15540-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15540-109">Example</span></span>  

 <span data-ttu-id="15540-110">La dirección base se especifica utilizando el elemento `add`, bajo service/host/baseAddresses, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="15540-110">The base address is specified using the `add` element, under service/host/baseAddresses, as shown in the following sample.</span></span>  
  
```xml  
<service
    name="Microsoft.ServiceModel.Samples.CalculatorService">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
    </baseAddresses>  
  </host>  
```  
  
## <a name="example"></a><span data-ttu-id="15540-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15540-111">Example</span></span>  

 <span data-ttu-id="15540-112">La primera definición de extremo mostrada en el siguiente ejemplo especifica una dirección relativa, que significa que la dirección del extremo es una combinación de la dirección base y la dirección relativa siguiendo las reglas de composición de identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="15540-112">The first endpoint definition shown in the following sample specifies a relative address, which means the endpoint address is a combination of the base address and the relative address following the rules of Uniform Resource Identifier (URI) composition.</span></span> <span data-ttu-id="15540-113">La dirección relativa está vacía (""), por lo que la dirección del extremo es igual a la dirección base.</span><span class="sxs-lookup"><span data-stu-id="15540-113">The relative address is empty (""), so the endpoint address is the same as the base address.</span></span> <span data-ttu-id="15540-114">La dirección del punto de conexión real es `http://localhost:8000/servicemodelsamples/service` .</span><span class="sxs-lookup"><span data-stu-id="15540-114">The actual endpoint address is `http://localhost:8000/servicemodelsamples/service`.</span></span>  
  
```xml  
<endpoint address=""
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="15540-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15540-115">Example</span></span>  

 <span data-ttu-id="15540-116">La segunda definición de extremo también especifica una dirección relativa, como se muestra en el siguiente ejemplo de configuración.</span><span class="sxs-lookup"><span data-stu-id="15540-116">The second endpoint definition also specifies a relative address, as shown in the following sample configuration.</span></span> <span data-ttu-id="15540-117">La dirección relativa, "test", se anexa a la dirección base.</span><span class="sxs-lookup"><span data-stu-id="15540-117">The relative address, "test", is appended to the base address.</span></span> <span data-ttu-id="15540-118">La dirección del punto de conexión real es `http://localhost:8000/servicemodelsamples/service/test` .</span><span class="sxs-lookup"><span data-stu-id="15540-118">The actual endpoint address is `http://localhost:8000/servicemodelsamples/service/test`.</span></span>  
  
```xml  
<endpoint address="/test"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="15540-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15540-119">Example</span></span>  

 <span data-ttu-id="15540-120">La tercera definición de extremo especifica una dirección absoluta, como se muestra en el siguiente ejemplo de configuración.</span><span class="sxs-lookup"><span data-stu-id="15540-120">The third endpoint definition specifies an absolute address, as shown in the following sample configuration.</span></span> <span data-ttu-id="15540-121">La dirección base no desempeña ningún papel en la dirección.</span><span class="sxs-lookup"><span data-stu-id="15540-121">The base address plays no role in the address.</span></span> <span data-ttu-id="15540-122">La dirección del punto de conexión real es `http://localhost:8001/hello/servicemodelsamples` .</span><span class="sxs-lookup"><span data-stu-id="15540-122">The actual endpoint address is `http://localhost:8001/hello/servicemodelsamples`.</span></span>  
  
```xml  
<endpoint address="http://localhost:8001/hello/servicemodelsamples"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="15540-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15540-123">Example</span></span>  

 <span data-ttu-id="15540-124">La cuarta dirección del extremo especifica una dirección absoluta y un TCP de transporte diferente.</span><span class="sxs-lookup"><span data-stu-id="15540-124">The fourth endpoint address specifies an absolute address and a different transport—TCP.</span></span> <span data-ttu-id="15540-125">La dirección base no desempeña ningún papel en la dirección.</span><span class="sxs-lookup"><span data-stu-id="15540-125">The base address plays no role in the address.</span></span> <span data-ttu-id="15540-126">La dirección del punto de conexión real es net.tcp://localhost:9000/servicemodelsamples/service.</span><span class="sxs-lookup"><span data-stu-id="15540-126">The actual endpoint address is net.tcp://localhost:9000/servicemodelsamples/service.</span></span>  
  
```xml  
<endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
    binding="netTcpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="15540-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15540-127">Example</span></span>  

 <span data-ttu-id="15540-128">Para usar los puntos de conexión predeterminados proporcionados por el tiempo de ejecución, no especifique ningún punto de conexión de servicio en el código ni en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="15540-128">To use the default endpoints provided by the runtime, do not specify any service endpoints in either the code or the configuration file.</span></span> <span data-ttu-id="15540-129">En este ejemplo, el tiempo de ejecución crea los puntos de conexión predeterminados al abrir el servicio.</span><span class="sxs-lookup"><span data-stu-id="15540-129">In this example, the runtime creates the default endpoints when the service is opened.</span></span> <span data-ttu-id="15540-130">Para obtener más información sobre los puntos de conexión, enlaces y comportamientos predeterminados, vea [Configuración simplificada](../simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](../samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="15540-130">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../simplified-configuration.md) and [Simplified Configuration for WCF Services](../samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
```xml  
<configuration>  
  
  <appSettings>  
    <!-- use appSetting to configure base address provided by host -->  
    <add key="baseAddress" value="http://localhost:8000/servicemodelsamples/service" />  
  </appSettings>  
  
  <system.serviceModel>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```
