---
description: 'Más información sobre: comportamiento de depuración de servicio'
title: Comportamiento de depuración de servicio
ms.date: 03/30/2017
ms.assetid: 9d8fd3fb-dc39-427a-8235-336a7e7162ba
ms.openlocfilehash: 3aae4a4cca53fce50bff8ec02896e748f430166f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793108"
---
# <a name="service-debug-behavior"></a><span data-ttu-id="5c47e-103">Comportamiento de depuración de servicio</span><span class="sxs-lookup"><span data-stu-id="5c47e-103">Service Debug Behavior</span></span>

<span data-ttu-id="5c47e-104">Este ejemplo muestra cómo se pueden configurar los valores del comportamiento de servicio de depuración.</span><span class="sxs-lookup"><span data-stu-id="5c47e-104">This sample demonstrates how service debug behavior settings can be configured.</span></span> <span data-ttu-id="5c47e-105">El ejemplo se basa en el [Introducción](getting-started-sample.md), que implementa el `ICalculator` contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="5c47e-105">The sample is based on the [Getting Started](getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="5c47e-106">Este ejemplo define explícitamente el comportamiento de depuración de servicio en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5c47e-106">This sample explicitly defines service debug behavior in the configuration file.</span></span> <span data-ttu-id="5c47e-107">También se puede hacer de forma imperiosa en el código.</span><span class="sxs-lookup"><span data-stu-id="5c47e-107">It can also be done imperatively in code.</span></span>

<span data-ttu-id="5c47e-108">En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.</span><span class="sxs-lookup"><span data-stu-id="5c47e-108">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>

> [!NOTE]
> <span data-ttu-id="5c47e-109">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="5c47e-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="5c47e-110">El archivo Web.config para el servidor define el comportamiento de depuración del servicio para habilitar como se muestra la página de ayuda y control de excepciones en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5c47e-110">The Web.config file for the server defines the service debug behavior to enable the help page and exception handling as shown in the following sample.</span></span>

```xml
<behaviors>
     <serviceBehaviors>
         <behavior name="CalculatorServiceBehavior">
         <!-- WARNING: Setting includeExceptionDetailInFaults = "True" could result in leaking secured server information to the client.-->
         <!-- Please set this to false when deploying -->
             <serviceDebug includeExceptionDetailInFaults="True" httpHelpPageEnabled="True"/>
         </behavior>
     </serviceBehaviors>
</behaviors>
```

<span data-ttu-id="5c47e-111">[\<serviceDebug>](../../configure-apps/file-schema/wcf/servicedebug.md) es el elemento de configuración que permite cambiar las propiedades de comportamiento de depuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="5c47e-111">[\<serviceDebug>](../../configure-apps/file-schema/wcf/servicedebug.md) is the configuration element that allows changing the service debug behavior properties.</span></span> <span data-ttu-id="5c47e-112">El usuario puede modificar este comportamiento para lograr lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c47e-112">The user can modify this behavior to achieve the following:</span></span>

- <span data-ttu-id="5c47e-113">Permite al servicio devolver cualquier excepción producida por el código de aplicación aun cuando la excepción no se declare mediante <xref:System.ServiceModel.FaultContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5c47e-113">This allows the service to return any exception that is thrown by the application code even if the exception is not declared using the <xref:System.ServiceModel.FaultContractAttribute>.</span></span> <span data-ttu-id="5c47e-114">Se ha hecho configurando `includeExceptionDetailInFaults` como `true`.</span><span class="sxs-lookup"><span data-stu-id="5c47e-114">It is done by setting `includeExceptionDetailInFaults` to `true`.</span></span> <span data-ttu-id="5c47e-115">Este valor es útil al depurar los casos donde el servidor produce una excepción inesperada.</span><span class="sxs-lookup"><span data-stu-id="5c47e-115">This setting is useful when debugging cases where the server is throwing an unexpected exception.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="5c47e-116">No es seguro para activar este valor en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="5c47e-116">It is not secure to turn this setting on in a production environment.</span></span> <span data-ttu-id="5c47e-117">Una excepción de servidor inesperada puede tener alguna información que no se piensa para el cliente y establecer así `includeExceptionDetailsInFaults` como `true` podría producir pérdida de la información.</span><span class="sxs-lookup"><span data-stu-id="5c47e-117">An unexpected server exception may have some information that is not intended for the client and so setting `includeExceptionDetailsInFaults` to `true` might result in an information leak.</span></span>

- <span data-ttu-id="5c47e-118">[\<serviceDebug>](../../configure-apps/file-schema/wcf/servicedebug.md)También permite al usuario habilitar o deshabilitar la página de ayuda.</span><span class="sxs-lookup"><span data-stu-id="5c47e-118">The [\<serviceDebug>](../../configure-apps/file-schema/wcf/servicedebug.md) also allows a user to enable or disable the help page.</span></span> <span data-ttu-id="5c47e-119">Cada servicio puede exponer opcionalmente una página de ayuda que contiene información sobre el servicio que incluye el extremo para obtener WSDL para el servicio.</span><span class="sxs-lookup"><span data-stu-id="5c47e-119">Each service can optionally expose a help page that contains information about the service including the endpoint to get WSDL for the service.</span></span> <span data-ttu-id="5c47e-120">Esto puede estar habilitado estableciendo `httpHelpPageEnabled` como `true`.</span><span class="sxs-lookup"><span data-stu-id="5c47e-120">This can be enabled by setting `httpHelpPageEnabled` to `true`.</span></span> <span data-ttu-id="5c47e-121">Esto permite devolver la página de ayuda a una solicitud GET en la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="5c47e-121">This enables the help page to be returned to a GET request to the base address of the service.</span></span> <span data-ttu-id="5c47e-122">Puede cambiar esta dirección estableciendo otro atributo `httpHelpPageUrl`.</span><span class="sxs-lookup"><span data-stu-id="5c47e-122">You can change this address by setting another attribute `httpHelpPageUrl`.</span></span> <span data-ttu-id="5c47e-123">Puede realizarlo de manera segura utilizando HTTPS en lugar de HTTP.</span><span class="sxs-lookup"><span data-stu-id="5c47e-123">You can make this secure by using HTTPS instead of HTTP.</span></span> <span data-ttu-id="5c47e-124">Esto se puede hacer estableciendo `httpsHelpPageEnabled` y `httpsHelpPageUrl`.</span><span class="sxs-lookup"><span data-stu-id="5c47e-124">This can be done by setting `httpsHelpPageEnabled` and `httpsHelpPageUrl`.</span></span>

<span data-ttu-id="5c47e-125">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="5c47e-125">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="5c47e-126">Las primeras tres operaciones (Sumar, Restar y Multiplicar) deben ejecutarse exitosamente.</span><span class="sxs-lookup"><span data-stu-id="5c47e-126">The first three operations (Add, Subtract and Multiply) must succeed.</span></span> <span data-ttu-id="5c47e-127">Los últimos errores de la operación ("dividir") con una excepción de división entre cero.</span><span class="sxs-lookup"><span data-stu-id="5c47e-127">The last operation ("divide") fails with a division by zero exception.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5c47e-128">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="5c47e-128">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="5c47e-129">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5c47e-129">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="5c47e-130">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5c47e-130">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="5c47e-131">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5c47e-131">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c47e-132">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="5c47e-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5c47e-133">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="5c47e-133">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="5c47e-134">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="5c47e-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5c47e-135">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="5c47e-135">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\ServiceDebug`
