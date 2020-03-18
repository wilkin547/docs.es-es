---
title: Uso de dotnet-svcutil.xmlserializer
description: Obtenga información sobre cómo puede usar el paquete NuGet `dotnet-svcutil.xmlserializer` para generar previamente un ensamblado de serialización para los proyectos de .NET Core.
author: huanwu
ms.date: 11/27/2018
ms.openlocfilehash: 4811647c294118cb160d25805e7d3ada97f071f9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75344897"
---
# <a name="using-dotnet-svcutilxmlserializer-on-net-core"></a><span data-ttu-id="788bc-103">Uso de dotnet-svcutil.xmlserializer en .NET Core</span><span class="sxs-lookup"><span data-stu-id="788bc-103">Using dotnet-svcutil.xmlserializer on .NET Core</span></span>

<span data-ttu-id="788bc-104">El paquete NuGet `dotnet-svcutil.xmlserializer` puede generar previamente un ensamblado de serialización para los proyectos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="788bc-104">The `dotnet-svcutil.xmlserializer` NuGet package can pre-generate a serialization assembly for .NET Core projects.</span></span> <span data-ttu-id="788bc-105">Genera previamente código de serialización de C# para los tipos de la aplicación cliente que usa el contrato de servicio de WCF y que puede serializar XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="788bc-105">It pre-generates C# serialization code for the types in the client application that are used by the WCF Service Contract and that can be serialized by the XmlSerializer.</span></span> <span data-ttu-id="788bc-106">Esto mejora el rendimiento de inicio de la serialización de XML al serializar o deserializar objetos de esos tipos.</span><span class="sxs-lookup"><span data-stu-id="788bc-106">This improves the startup performance of XML serialization when serializing or deserializing objects of those types.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="788bc-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="788bc-107">Prerequisites</span></span>

* <span data-ttu-id="788bc-108">[SDK de .NET Core 2.1](https://dotnet.microsoft.com/download) o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="788bc-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later</span></span>
* <span data-ttu-id="788bc-109">Su editor de código favorito</span><span class="sxs-lookup"><span data-stu-id="788bc-109">Your favorite code editor</span></span>

<span data-ttu-id="788bc-110">Puede usar el comando `dotnet --info` para comprobar qué versiones del SDK de .NET Core y del Runtime ya ha instalado.</span><span class="sxs-lookup"><span data-stu-id="788bc-110">You can use the command `dotnet --info` to check which versions of .NET Core SDK and runtime you already have installed.</span></span>

## <a name="getting-started"></a><span data-ttu-id="788bc-111">Introducción</span><span class="sxs-lookup"><span data-stu-id="788bc-111">Getting started</span></span>

<span data-ttu-id="788bc-112">Para usar `dotnet-svcutil.xmlserializer` en una aplicación de consola de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="788bc-112">To use `dotnet-svcutil.xmlserializer` in a .NET Core console application:</span></span>

1. <span data-ttu-id="788bc-113">Crea un servicio WCF denominado "MyWCFService" mediante la plantilla predeterminada "Aplicación del servicio WCF" en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="788bc-113">Create a WCF Service named 'MyWCFService' using the default template 'WCF Service Application' in .NET Framework.</span></span> <span data-ttu-id="788bc-114">Agregue el atributo `[XmlSerializerFormat]` al método de servicio similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="788bc-114">Add `[XmlSerializerFormat]` attribute on the service method like the following:</span></span>

   ```csharp
    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```

2. <span data-ttu-id="788bc-115">Cree una aplicación de consola de .NET Core como aplicación cliente de WCF que tenga como destino .NET Core 2.1 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="788bc-115">Create a .NET Core console application as WCF client application that targets at .NET Core 2.1 or later versions.</span></span> <span data-ttu-id="788bc-116">Por ejemplo, cree una aplicación denominada "MyWCFClient" con el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="788bc-116">For example, create an app named 'MyWCFClient' with the following command:</span></span>

    ```dotnetcli
    dotnet new console --name MyWCFClient
    ```

    <span data-ttu-id="788bc-117">Para asegurarse de que el proyecto está destinado a .NET Core 2.1 o una versión posterior, inspeccione el elemento XML `TargetFramework` del archivo de proyecto:</span><span class="sxs-lookup"><span data-stu-id="788bc-117">To ensure your project is targeting .NET Core 2.1 or later, inspect the `TargetFramework` XML element in your project file:</span></span>

    ```xml
    <TargetFramework>netcoreapp2.1</TargetFramework>
    ```

3. <span data-ttu-id="788bc-118">Ejecute el comando siguiente para agregar una referencia de paquete a `System.ServiceModel.Http`:</span><span class="sxs-lookup"><span data-stu-id="788bc-118">Add a package reference to `System.ServiceModel.Http` by running the following command:</span></span>

    ```dotnetcli
    dotnet add package System.ServiceModel.Http
    ```

4. <span data-ttu-id="788bc-119">Agregue el código del cliente WCF:</span><span class="sxs-lookup"><span data-stu-id="788bc-119">Add the WCF Client code:</span></span>

    ```csharp
    using System.ServiceModel;

        class Program
        {
            static void Main(string[] args)
            {
                var myBinding = new BasicHttpBinding();
                var myEndpoint = new EndpointAddress("http://localhost:2561/Service1.svc"); //Fill your service url here
                var myChannelFactory = new ChannelFactory<IService1>(myBinding, myEndpoint);
                IService1 client = myChannelFactory.CreateChannel();
                string s = client.GetData(1);
                ((ICommunicationObject)client).Close();
            }
        }

    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```

5. <span data-ttu-id="788bc-120">Agregue una referencia al paquete `dotnet-svcutil.xmlserializer` mediante la ejecución del comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="788bc-120">Add a reference to the `dotnet-svcutil.xmlserializer` package by running the following command:</span></span>
  
    ```dotnetcli
    dotnet add package dotnet-svcutil.xmlserializer
    ```

    <span data-ttu-id="788bc-121">Al ejecutar el comando se debería agregar una entrada al archivo de proyecto similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="788bc-121">Running the command should add an entry to your project file similar to this:</span></span>
  
    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil.xmlserializer" Version="1.0.0" />
    </ItemGroup>
    ```

6. <span data-ttu-id="788bc-122">Compile la aplicación ejecutando `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="788bc-122">Build the application by running `dotnet build`.</span></span> <span data-ttu-id="788bc-123">Si todo se realiza correctamente, se genera un ensamblado denominado *MyWCFClient.XmlSerializers.dll* en la carpeta de salida.</span><span class="sxs-lookup"><span data-stu-id="788bc-123">If everything succeeds, an assembly named *MyWCFClient.XmlSerializers.dll* is generated in the output folder.</span></span> <span data-ttu-id="788bc-124">Si la herramienta no pudo generar el ensamblado, verá advertencias en la salida de la compilación.</span><span class="sxs-lookup"><span data-stu-id="788bc-124">If the tool failed to generate the assembly, you'll see warnings in the build output.</span></span>

7. <span data-ttu-id="788bc-125">Inicie el servicio WCF, por ejemplo, mediante la ejecución de `http://localhost:2561/Service1.svc` en el explorador.</span><span class="sxs-lookup"><span data-stu-id="788bc-125">Start the WCF service by, for example, running `http://localhost:2561/Service1.svc` in the browser.</span></span> <span data-ttu-id="788bc-126">Después, inicie la aplicación cliente, que se cargará automáticamente y utilizará los serializadores generados previamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="788bc-126">Then start the client application, and it will automatically load and use the pre-generated serializers at runtime.</span></span>
