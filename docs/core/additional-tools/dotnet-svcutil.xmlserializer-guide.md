# <a name="using-dotnet-svcutilxmlserializer-on-net-core"></a><span data-ttu-id="affa8-101">Uso de dotnet-svcutil.xmlserializer en .NET Core</span><span class="sxs-lookup"><span data-stu-id="affa8-101">Using dotnet-svcutil.xmlserializer on .NET Core</span></span>

## <a name="prerequisites"></a><span data-ttu-id="affa8-102">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="affa8-102">Prerequisites</span></span>

<span data-ttu-id="affa8-103">Se necesita lo siguiente para que dotnet-svcutil.xmlserializer funcione.</span><span class="sxs-lookup"><span data-stu-id="affa8-103">The following is required for dotnet-svcutil.xmlserializer to work.</span></span> 

* [<span data-ttu-id="affa8-104">SDK de .NET Core 2.1 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="affa8-104">.NET Core 2.1 SDK or later</span></span>](https://www.microsoft.com/net/download/dotnet-core/sdk-2.1.300)
* [<span data-ttu-id="affa8-105">.NET Core Runtime 2.1 o posterior</span><span class="sxs-lookup"><span data-stu-id="affa8-105">.NET Core Runtime 2.1 or later</span></span>](https://www.microsoft.com/net/download/dotnet-core/runtime-2.1.0)

<span data-ttu-id="affa8-106">Puede usar el comando `dotnet --info` para comprobar qué versiones del SDK de .NET Core y del Runtime ya ha instalado.</span><span class="sxs-lookup"><span data-stu-id="affa8-106">You can use the command `dotnet --info` to check which versions of .NET Core SDK and runtime you already have installed.</span></span>

<span data-ttu-id="affa8-107">Para usar dotnet svcutil.xmlserializer en una aplicación de consola de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="affa8-107">To use dotnet-svcutil.xmlserializer in a .NET Core console application:</span></span>

1. <span data-ttu-id="affa8-108">Crea un servicio WCF denominado "MyWCFService" mediante la plantilla predeterminada "Aplicación del servicio WCF" en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="affa8-108">Create a WCF Service named 'MyWCFService' using the default template 'WCF Service Application' in .NET Framework.</span></span>  <span data-ttu-id="affa8-109">Agregue el atributo ```[XmlSerializerFormat]``` en el método de servicio similar a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="affa8-109">Add ```[XmlSerializerFormat]``` attribute on the service method like the following</span></span>
    ```c#
    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```
2. <span data-ttu-id="affa8-110">Cree una aplicación de consola de .NET Core como aplicación de cliente WCF que utiliza netcoreapp 2.1 como destino; por ejemplo, cree una aplicación denominada "MyWCFClient" con el comando:</span><span class="sxs-lookup"><span data-stu-id="affa8-110">Create a .NET Core console application as WCF client application that targets at netcoreapp 2.1, e.g. create an app named 'MyWCFClient' with the command,</span></span>
    ```
    dotnet new console --name MyWCFClient
    ```
    <span data-ttu-id="affa8-111">Asegúrese de que csproj de tiene como destino netcoreapp 2.1.</span><span class="sxs-lookup"><span data-stu-id="affa8-111">Make sure your csproj targets a netcoreapp 2.1.</span></span> <span data-ttu-id="affa8-112">Esto se realiza mediante el siguiente elemento XML en el archivo .csproj:</span><span class="sxs-lookup"><span data-stu-id="affa8-112">This is done using the following XML element in your .csproj file</span></span>
    ```xml
    <TargetFramework>netcoreapp2.1</TargetFramework>
    ```
3. <span data-ttu-id="affa8-113">Agregue una referencia de paquete a System.ServiceModel.Http ejecutando el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="affa8-113">Add a package reference to System.ServiceModel.Http by running the following command:</span></span>
   
   ```dotnet add package System.ServiceModel.Http -v 4.5.0```

4. <span data-ttu-id="affa8-114">Agregue el código del cliente WCF:</span><span class="sxs-lookup"><span data-stu-id="affa8-114">Add the WCF Client code:</span></span>
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
5. <span data-ttu-id="affa8-115">Edite el archivo .csproj y agregue una referencia al paquete de dotnet-svcutil.xmlserializer.</span><span class="sxs-lookup"><span data-stu-id="affa8-115">Edit the .csproj file and add a reference to the dotnet-svcutil.xmlserializer package.</span></span> <span data-ttu-id="affa8-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="affa8-116">For example:</span></span>

    <span data-ttu-id="affa8-117">i.</span><span class="sxs-lookup"><span data-stu-id="affa8-117">i.</span></span> <span data-ttu-id="affa8-118">Ejecute el comando: `dotnet add package dotnet-svcutil.xmlserializer -v 1.0.0`</span><span class="sxs-lookup"><span data-stu-id="affa8-118">Run command: `dotnet add package dotnet-svcutil.xmlserializer -v 1.0.0`</span></span>

    <span data-ttu-id="affa8-119">ii.</span><span class="sxs-lookup"><span data-stu-id="affa8-119">ii.</span></span> <span data-ttu-id="affa8-120">Agregue las siguientes líneas en MyWCFClient.csproj:</span><span class="sxs-lookup"><span data-stu-id="affa8-120">Add the following lines in MyWCFClient.csproj,</span></span>
    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil.xmlserializer" Version="1.0.0" />
    </ItemGroup>
    ```

6. <span data-ttu-id="affa8-121">Compile la aplicación ejecutando `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="affa8-121">Build the application by running `dotnet build`.</span></span> <span data-ttu-id="affa8-122">Si todo se realiza correctamente, se genera un ensamblado con el nombre MyWCFClient.XmlSerializers.dll en la carpeta de salida.</span><span class="sxs-lookup"><span data-stu-id="affa8-122">If everything succeeds, an assembly named MyWCFClient.XmlSerializers.dll will be generated in the output folder.</span></span> <span data-ttu-id="affa8-123">Si la herramienta no pudo generar el ensamblado, verá advertencias en la salida de la compilación.</span><span class="sxs-lookup"><span data-stu-id="affa8-123">You will see warnings in the build output if the tool failed to generate the assembly.</span></span>

7. <span data-ttu-id="affa8-124">Inicie el servicio WCF, por ejemplo, mediante la ejecución de http://localhost:2561/Service1.svc en el explorador.</span><span class="sxs-lookup"><span data-stu-id="affa8-124">Start the WCF service e.g. by running http://localhost:2561/Service1.svc in the browser.</span></span> <span data-ttu-id="affa8-125">Después, inicie la aplicación cliente, que se cargará automáticamente y utilizará los serializadores generados previamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="affa8-125">Then start the client application, and it will automatically load and use the pre-generated serializers at runtime.</span></span>
