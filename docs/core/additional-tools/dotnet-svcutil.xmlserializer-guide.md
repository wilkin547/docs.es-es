---
title: Uso de dotnet-svcutil.xmlserializer
description: Obtenga información sobre cómo puede usar el paquete NuGet `dotnet-svcutil.xmlserializer` para generar previamente un ensamblado de serialización para los proyectos de .NET Core.
author: huanwu
ms.date: 11/27/2018
ms.openlocfilehash: 4811647c294118cb160d25805e7d3ada97f071f9
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344897"
---
# <a name="using-dotnet-svcutilxmlserializer-on-net-core"></a>Uso de dotnet-svcutil.xmlserializer en .NET Core

El paquete NuGet `dotnet-svcutil.xmlserializer` puede generar previamente un ensamblado de serialización para los proyectos de .NET Core. Genera previamente código de serialización de C# para los tipos de la aplicación cliente que usa el contrato de servicio de WCF y que puede serializar XmlSerializer. Esto mejora el rendimiento de inicio de la serialización de XML al serializar o deserializar objetos de esos tipos.

## <a name="prerequisites"></a>Requisitos previos

* [SDK de .NET Core 2.1](https://dotnet.microsoft.com/download) o versiones posteriores
* Su editor de código favorito

Puede usar el comando `dotnet --info` para comprobar qué versiones del SDK de .NET Core y del Runtime ya ha instalado.

## <a name="getting-started"></a>Introducción

Para usar `dotnet-svcutil.xmlserializer` en una aplicación de consola de .NET Core:

1. Crea un servicio WCF denominado "MyWCFService" mediante la plantilla predeterminada "Aplicación del servicio WCF" en .NET Framework. Agregue el atributo `[XmlSerializerFormat]` al método de servicio similar al siguiente:

   ```csharp
    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```

2. Cree una aplicación de consola de .NET Core como aplicación cliente de WCF que tenga como destino .NET Core 2.1 o versiones posteriores. Por ejemplo, cree una aplicación denominada "MyWCFClient" con el comando siguiente:

    ```dotnetcli
    dotnet new console --name MyWCFClient
    ```

    Para asegurarse de que el proyecto está destinado a .NET Core 2.1 o una versión posterior, inspeccione el elemento XML `TargetFramework` del archivo de proyecto:

    ```xml
    <TargetFramework>netcoreapp2.1</TargetFramework>
    ```

3. Ejecute el comando siguiente para agregar una referencia de paquete a `System.ServiceModel.Http`:

    ```dotnetcli
    dotnet add package System.ServiceModel.Http
    ```

4. Agregue el código del cliente WCF:

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

5. Agregue una referencia al paquete `dotnet-svcutil.xmlserializer` mediante la ejecución del comando siguiente:
  
    ```dotnetcli
    dotnet add package dotnet-svcutil.xmlserializer
    ```

    Al ejecutar el comando se debería agregar una entrada al archivo de proyecto similar a la siguiente:
  
    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil.xmlserializer" Version="1.0.0" />
    </ItemGroup>
    ```

6. Compile la aplicación ejecutando `dotnet build`. Si todo se realiza correctamente, se genera un ensamblado denominado *MyWCFClient.XmlSerializers.dll* en la carpeta de salida. Si la herramienta no pudo generar el ensamblado, verá advertencias en la salida de la compilación.

7. Inicie el servicio WCF, por ejemplo, mediante la ejecución de `http://localhost:2561/Service1.svc` en el explorador. Después, inicie la aplicación cliente, que se cargará automáticamente y utilizará los serializadores generados previamente en tiempo de ejecución.
