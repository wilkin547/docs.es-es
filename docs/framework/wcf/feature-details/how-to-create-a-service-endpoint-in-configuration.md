---
title: Procedimiento para crear un punto de conexión de servicio en la configuración
ms.date: 06/16/2016
ms.assetid: f474e25d-2a27-4f31-84c5-395c442b8e70
ms.openlocfilehash: 56b29da0c147eb9e73a08e2875e33e384da729ed
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598923"
---
# <a name="how-to-create-a-service-endpoint-in-configuration"></a><span data-ttu-id="3a56c-102">Procedimiento para crear un punto de conexión de servicio en la configuración</span><span class="sxs-lookup"><span data-stu-id="3a56c-102">How to: Create a Service Endpoint in Configuration</span></span>
<span data-ttu-id="3a56c-103">Los extremos proporcionan a los clientes acceso a la funcionalidad que ofrece un servicio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3a56c-103">Endpoints provide clients with access to the functionality a Windows Communication Foundation (WCF) service offers.</span></span> <span data-ttu-id="3a56c-104">Puede definir uno o más extremos para un servicio usando una combinación de direcciones de extremo relativas y absolutas; si no se define ninguno, el tiempo de ejecución proporciona varios de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3a56c-104">You can define one or more endpoints for a service by using a combination of relative and absolute endpoint addresses, or if you do not define any service endpoints, the runtime provides some by default for you.</span></span> <span data-ttu-id="3a56c-105">En este tema se muestra cómo agregar extremos mediante un archivo de configuración que contiene tanto direcciones absolutas como relativas.</span><span class="sxs-lookup"><span data-stu-id="3a56c-105">This topic shows how to add endpoints using a configuration file that contain both relative and absolute addresses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a56c-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a56c-106">Example</span></span>  
 <span data-ttu-id="3a56c-107">La siguiente configuración de servicio especifica una dirección base y cinco extremos.</span><span class="sxs-lookup"><span data-stu-id="3a56c-107">The following service configuration specifies a base address and five endpoints.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="3a56c-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a56c-108">Example</span></span>  
 <span data-ttu-id="3a56c-109">La dirección base se especifica utilizando el elemento `add`, bajo service/host/baseAddresses, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3a56c-109">The base address is specified using the `add` element, under service/host/baseAddresses, as shown in the following sample.</span></span>  
  
```xml  
<service
    name="Microsoft.ServiceModel.Samples.CalculatorService">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
    </baseAddresses>  
  </host>  
```  
  
## <a name="example"></a><span data-ttu-id="3a56c-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a56c-110">Example</span></span>  
 <span data-ttu-id="3a56c-111">La primera definición de extremo mostrada en el siguiente ejemplo especifica una dirección relativa, que significa que la dirección del extremo es una combinación de la dirección base y la dirección relativa siguiendo las reglas de composición de identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="3a56c-111">The first endpoint definition shown in the following sample specifies a relative address, which means the endpoint address is a combination of the base address and the relative address following the rules of Uniform Resource Identifier (URI) composition.</span></span> <span data-ttu-id="3a56c-112">La dirección relativa está vacía (""), por lo que la dirección del extremo es igual a la dirección base.</span><span class="sxs-lookup"><span data-stu-id="3a56c-112">The relative address is empty (""), so the endpoint address is the same as the base address.</span></span> <span data-ttu-id="3a56c-113">La dirección del punto de conexión real es `http://localhost:8000/servicemodelsamples/service` .</span><span class="sxs-lookup"><span data-stu-id="3a56c-113">The actual endpoint address is `http://localhost:8000/servicemodelsamples/service`.</span></span>  
  
```xml  
<endpoint address=""
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="3a56c-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a56c-114">Example</span></span>  
 <span data-ttu-id="3a56c-115">La segunda definición de extremo también especifica una dirección relativa, como se muestra en el siguiente ejemplo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3a56c-115">The second endpoint definition also specifies a relative address, as shown in the following sample configuration.</span></span> <span data-ttu-id="3a56c-116">La dirección relativa, "test", se anexa a la dirección base.</span><span class="sxs-lookup"><span data-stu-id="3a56c-116">The relative address, "test", is appended to the base address.</span></span> <span data-ttu-id="3a56c-117">La dirección del punto de conexión real es `http://localhost:8000/servicemodelsamples/service/test` .</span><span class="sxs-lookup"><span data-stu-id="3a56c-117">The actual endpoint address is `http://localhost:8000/servicemodelsamples/service/test`.</span></span>  
  
```xml  
<endpoint address="/test"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="3a56c-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a56c-118">Example</span></span>  
 <span data-ttu-id="3a56c-119">La tercera definición de extremo especifica una dirección absoluta, como se muestra en el siguiente ejemplo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3a56c-119">The third endpoint definition specifies an absolute address, as shown in the following sample configuration.</span></span> <span data-ttu-id="3a56c-120">La dirección base no desempeña ningún papel en la dirección.</span><span class="sxs-lookup"><span data-stu-id="3a56c-120">The base address plays no role in the address.</span></span> <span data-ttu-id="3a56c-121">La dirección del punto de conexión real es `http://localhost:8001/hello/servicemodelsamples` .</span><span class="sxs-lookup"><span data-stu-id="3a56c-121">The actual endpoint address is `http://localhost:8001/hello/servicemodelsamples`.</span></span>  
  
```xml  
<endpoint address="http://localhost:8001/hello/servicemodelsamples"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="3a56c-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a56c-122">Example</span></span>  
 <span data-ttu-id="3a56c-123">La cuarta dirección del extremo especifica una dirección absoluta y un TCP de transporte diferente.</span><span class="sxs-lookup"><span data-stu-id="3a56c-123">The fourth endpoint address specifies an absolute address and a different transport—TCP.</span></span> <span data-ttu-id="3a56c-124">La dirección base no desempeña ningún papel en la dirección.</span><span class="sxs-lookup"><span data-stu-id="3a56c-124">The base address plays no role in the address.</span></span> <span data-ttu-id="3a56c-125">La dirección del punto de conexión real es net.tcp://localhost:9000/servicemodelsamples/service.</span><span class="sxs-lookup"><span data-stu-id="3a56c-125">The actual endpoint address is net.tcp://localhost:9000/servicemodelsamples/service.</span></span>  
  
```xml  
<endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
    binding="netTcpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="3a56c-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a56c-126">Example</span></span>  
 <span data-ttu-id="3a56c-127">Para usar los puntos de conexión predeterminados proporcionados por el tiempo de ejecución, no especifique ningún punto de conexión de servicio en el código ni en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3a56c-127">To use the default endpoints provided by the runtime, do not specify any service endpoints in either the code or the configuration file.</span></span> <span data-ttu-id="3a56c-128">En este ejemplo, el tiempo de ejecución crea los puntos de conexión predeterminados al abrir el servicio.</span><span class="sxs-lookup"><span data-stu-id="3a56c-128">In this example, the runtime creates the default endpoints when the service is opened.</span></span> <span data-ttu-id="3a56c-129">Para obtener más información sobre los puntos de conexión, enlaces y comportamientos predeterminados, vea [Configuración simplificada](../simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](../samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="3a56c-129">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../simplified-configuration.md) and [Simplified Configuration for WCF Services](../samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
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
