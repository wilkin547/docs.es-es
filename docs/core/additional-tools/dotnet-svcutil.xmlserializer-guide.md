# <a name="using-dotnet-svcutilxmlserializer-on-net-core"></a>Uso de dotnet-svcutil.xmlserializer en .NET Core

## <a name="prerequisites"></a>Requisitos previos

Se necesita lo siguiente para que dotnet-svcutil.xmlserializer funcione. 

* [SDK de .NET Core 2.1 o versiones posteriores](https://www.microsoft.com/net/download/dotnet-core/sdk-2.1.300)
* [.NET Core Runtime 2.1 o posterior](https://www.microsoft.com/net/download/dotnet-core/runtime-2.1.0)

Puede usar el comando `dotnet --info` para comprobar qué versiones del SDK de .NET Core y del Runtime ya ha instalado.

Para usar dotnet svcutil.xmlserializer en una aplicación de consola de .NET Core:

1. Crea un servicio WCF denominado "MyWCFService" mediante la plantilla predeterminada "Aplicación del servicio WCF" en .NET Framework.  Agregue el atributo ```[XmlSerializerFormat]``` en el método de servicio similar a lo siguiente:
    ```c#
    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```
2. Cree una aplicación de consola de .NET Core como aplicación de cliente WCF que utiliza netcoreapp 2.1 como destino; por ejemplo, cree una aplicación denominada "MyWCFClient" con el comando:
    ```
    dotnet new console --name MyWCFClient
    ```
    Asegúrese de que csproj de tiene como destino netcoreapp 2.1. Esto se realiza mediante el siguiente elemento XML en el archivo .csproj:
    ```xml
    <TargetFramework>netcoreapp2.1</TargetFramework>
    ```
3. Agregue una referencia de paquete a System.ServiceModel.Http ejecutando el comando siguiente:
   
   ```dotnet add package System.ServiceModel.Http -v 4.5.0```

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
5. Edite el archivo .csproj y agregue una referencia al paquete de dotnet-svcutil.xmlserializer. Por ejemplo:

    i. Ejecute el comando: `dotnet add package dotnet-svcutil.xmlserializer -v 1.0.0`

    ii. Agregue las siguientes líneas en MyWCFClient.csproj:
    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil.xmlserializer" Version="1.0.0" />
    </ItemGroup>
    ```

6. Compile la aplicación ejecutando `dotnet build`. Si todo se realiza correctamente, se genera un ensamblado con el nombre MyWCFClient.XmlSerializers.dll en la carpeta de salida. Si la herramienta no pudo generar el ensamblado, verá advertencias en la salida de la compilación.

7. Inicie el servicio WCF, por ejemplo, mediante la ejecución de http://localhost:2561/Service1.svc en el explorador. Después, inicie la aplicación cliente, que se cargará automáticamente y utilizará los serializadores generados previamente en tiempo de ejecución.
