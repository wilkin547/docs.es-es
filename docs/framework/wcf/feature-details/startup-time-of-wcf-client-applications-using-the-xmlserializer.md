---
title: Procedimiento para mejorar el tiempo de inicio de las aplicaciones cliente WCF mediante XmlSerializer
ms.date: 03/30/2017
ms.assetid: 21093451-0bc3-4b1a-9a9d-05f7f71fa7d0
ms.openlocfilehash: ac54a766161db146331a3e072b97822b609344c0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96246386"
---
# <a name="how-to-improve-the-startup-time-of-wcf-client-applications-using-the-xmlserializer"></a><span data-ttu-id="f23fd-102">Procedimiento para mejorar el tiempo de inicio de las aplicaciones cliente WCF mediante XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="f23fd-102">How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer</span></span>

<span data-ttu-id="f23fd-103">Los servicios y las aplicaciones cliente que utilizan tipos de datos que son serializables utilizando <xref:System.Xml.Serialization.XmlSerializer> generan y compilan el código de la serialización para esos tipos de datos en el tiempo de ejecución, lo que se puede traducir en un rendimiento de inicio lento.</span><span class="sxs-lookup"><span data-stu-id="f23fd-103">Services and client applications that use data types that are serializable using the <xref:System.Xml.Serialization.XmlSerializer> generate and compile serialization code for those data types at runtime, which can result in slow start-up performance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f23fd-104">El código de serialización generado previamente solo puede usarse en aplicaciones cliente y no en servicios.</span><span class="sxs-lookup"><span data-stu-id="f23fd-104">Pre-generated serialization code can only be used in client applications and not in services.</span></span>  
  
 <span data-ttu-id="f23fd-105">La [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) puede mejorar el rendimiento de inicio de estas aplicaciones mediante la generación del código de serialización necesario a partir de los ensamblados compilados para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f23fd-105">The [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) can improve start-up performance for these applications by generating the necessary serialization code from the compiled assemblies for the application.</span></span> <span data-ttu-id="f23fd-106">Svcutil.exe genera el código de serialización para todos los tipos de datos utilizados en contratos de servicios en el ensamblado de aplicación de compilación que se puede serializar utilizando <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="f23fd-106">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="f23fd-107">Los contratos de operación y servicio que utiliza el <xref:System.Xml.Serialization.XmlSerializer> se marcan con <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f23fd-107">Service and operation contracts that use the <xref:System.Xml.Serialization.XmlSerializer> are marked with the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code"></a><span data-ttu-id="f23fd-108">Para generar el código de serialización de XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="f23fd-108">To generate XmlSerializer serialization code</span></span>  
  
1. <span data-ttu-id="f23fd-109">Compile su servicio o código de cliente en uno o más ensamblados.</span><span class="sxs-lookup"><span data-stu-id="f23fd-109">Compile your service or client code into one or more assemblies.</span></span>  
  
2. <span data-ttu-id="f23fd-110">Abra un símbolo del sistema de SDK.</span><span class="sxs-lookup"><span data-stu-id="f23fd-110">Open an SDK command prompt.</span></span>  
  
3. <span data-ttu-id="f23fd-111">En el símbolo del sistema, inicie la herramienta Svcutil.exe mediante el formato siguiente.</span><span class="sxs-lookup"><span data-stu-id="f23fd-111">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span>  
  
    ```console  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="f23fd-112">El argumento `assemblyPath` especifica la ruta de acceso a un ensamblado que contiene tipos de contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="f23fd-112">The `assemblyPath` argument specifies the path to an assembly that contains service contract types.</span></span> <span data-ttu-id="f23fd-113">Svcutil.exe genera el código de serialización para todos los tipos de datos utilizados en contratos de servicios en el ensamblado de aplicación de compilación que se puede serializar utilizando <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="f23fd-113">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
     <span data-ttu-id="f23fd-114">Svcutil.exe solo puede generar código de serialización de C#.</span><span class="sxs-lookup"><span data-stu-id="f23fd-114">Svcutil.exe can only generate C# serialization code.</span></span> <span data-ttu-id="f23fd-115">Un archivo de código fuente se genera para cada ensamblado de entrada.</span><span class="sxs-lookup"><span data-stu-id="f23fd-115">One source code file is generated for each input assembly.</span></span> <span data-ttu-id="f23fd-116">No se puede usar el modificador **/Language** para cambiar el lenguaje del código generado.</span><span class="sxs-lookup"><span data-stu-id="f23fd-116">You cannot use the **/language** switch to change the language of the generated code.</span></span>  
  
     <span data-ttu-id="f23fd-117">Para especificar la ruta de acceso a los ensamblados dependientes, use la opción **/Reference** .</span><span class="sxs-lookup"><span data-stu-id="f23fd-117">To specify the path to dependent assemblies, use the **/reference** option.</span></span>  
  
4. <span data-ttu-id="f23fd-118">Haga que el código de serialización generado esté disponible para su aplicación utilizando una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f23fd-118">Make the generated serialization code available to your application by using one of the following options:</span></span>  
  
    1. <span data-ttu-id="f23fd-119">Compile el código de serialización generado en un ensamblado independiente con el nombre [*ensamblado original*] .XmlSerializers.dll (por ejemplo, MyApp.XmlSerializers.dll).</span><span class="sxs-lookup"><span data-stu-id="f23fd-119">Compile the generated serialization code into a separate assembly with the name [*original assembly*].XmlSerializers.dll (for example, MyApp.XmlSerializers.dll).</span></span> <span data-ttu-id="f23fd-120">Su aplicación debe poder cargar el ensamblado, que se debe firmar con la misma clave como el ensamblado original.</span><span class="sxs-lookup"><span data-stu-id="f23fd-120">Your application must be able to load the assembly, which must be signed with the same key as the original assembly.</span></span> <span data-ttu-id="f23fd-121">Si vuelve a compilar el ensamblado original, debe volver a generar el ensamblado de serialización.</span><span class="sxs-lookup"><span data-stu-id="f23fd-121">If you recompile the original assembly, you must regenerate the serialization assembly.</span></span>  
  
    2. <span data-ttu-id="f23fd-122">Compile el código de serialización generado en un ensamblado independiente y utilice <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> en el contrato de servicios que utiliza <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f23fd-122">Compile the generated serialization code into a separate assembly and use the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> on the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="f23fd-123">Establezca las propiedades <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> o <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> para señalar al ensamblado de serialización compilado.</span><span class="sxs-lookup"><span data-stu-id="f23fd-123">Set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties to point to the compiled serialization assembly.</span></span>  
  
    3. <span data-ttu-id="f23fd-124">Compile el código de serialización generado en su ensamblado de aplicación y agregue el <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> al contrato de servicios que utiliza el <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f23fd-124">Compile the generated serialization code into your application assembly and add the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> to the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="f23fd-125">No establezca las propiedades <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> ni <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A>.</span><span class="sxs-lookup"><span data-stu-id="f23fd-125">Do not set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties.</span></span> <span data-ttu-id="f23fd-126">Se supone que el ensamblado de serialización predeterminado es el ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="f23fd-126">The default serialization assembly is assumed to be the current assembly.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code-in-visual-studio"></a><span data-ttu-id="f23fd-127">Para generar código de serialización XmlSerializer en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f23fd-127">To generate XmlSerializer serialization code in Visual Studio</span></span>  
  
1. <span data-ttu-id="f23fd-128">Cree los proyectos de servicio y cliente de WCF en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f23fd-128">Create the WCF service and client projects in Visual Studio.</span></span> <span data-ttu-id="f23fd-129">A continuación, agregue una referencia de servicio al proyecto de cliente.</span><span class="sxs-lookup"><span data-stu-id="f23fd-129">Then, add a service reference to the client project.</span></span>  
  
2. <span data-ttu-id="f23fd-130">Agregue un <xref:System.ServiceModel.XmlSerializerFormatAttribute> al contrato de servicio en el archivo *Reference.CS* en el proyecto de la aplicación cliente en **serviceReference**  ->  **Reference. svcmap**.</span><span class="sxs-lookup"><span data-stu-id="f23fd-130">Add an <xref:System.ServiceModel.XmlSerializerFormatAttribute> to the service contract in the *reference.cs* file in the client app project under **serviceReference** -> **reference.svcmap**.</span></span> <span data-ttu-id="f23fd-131">Tenga en cuenta que tiene que Mostrar todos los archivos de **Explorador de soluciones** para ver estos archivos.</span><span class="sxs-lookup"><span data-stu-id="f23fd-131">Note that you need to show all files in **Solution Explorer** to see these files.</span></span>  
  
3. <span data-ttu-id="f23fd-132">Compile la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="f23fd-132">Build the client app.</span></span>  
  
4. <span data-ttu-id="f23fd-133">Use la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para crear un archivo *. CS* de serializador generado previamente mediante el comando:</span><span class="sxs-lookup"><span data-stu-id="f23fd-133">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to create a pre-generated serializer *.cs* file by using the command:</span></span>  
  
    ```console  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="f23fd-134">El argumento assemblyPath especifica la ruta de acceso al ensamblado de cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="f23fd-134">The assemblyPath argument specifies the path to the WCF client assembly.</span></span>  
  
     <span data-ttu-id="f23fd-135">Como:</span><span class="sxs-lookup"><span data-stu-id="f23fd-135">Such as:</span></span>  
  
    ```console  
    svcutil.exe /t:xmlSerializer wcfclient.exe  
    ```  
  
     <span data-ttu-id="f23fd-136">Se generará el archivo *WCFClient.XmlSerializers.dll. CS* .</span><span class="sxs-lookup"><span data-stu-id="f23fd-136">The *WCFClient.XmlSerializers.dll.cs* file will be generated.</span></span>  
  
5. <span data-ttu-id="f23fd-137">Compile el ensamblado de serialización generado previamente.</span><span class="sxs-lookup"><span data-stu-id="f23fd-137">Compile the pre-generated serialization assembly.</span></span>  
  
     <span data-ttu-id="f23fd-138">Según el ejemplo del paso anterior, el comando de compilación sería el siguiente:</span><span class="sxs-lookup"><span data-stu-id="f23fd-138">Based on the example in the previous step, the compile command would be the following:</span></span>  
  
    ```console  
    csc /r:wcfclient.exe /out:WCFClient.XmlSerializers.dll /t:library WCFClient.XmlSerializers.dll.cs  
    ```  
  
     <span data-ttu-id="f23fd-139">Asegúrese de que el *WCFClient.XmlSerializers.dll* generado se encuentra en el mismo directorio que la aplicación cliente, que se *WCFClient.exe* en este caso.</span><span class="sxs-lookup"><span data-stu-id="f23fd-139">Make sure the generated *WCFClient.XmlSerializers.dll* is in the same directory as the client app, which is *WCFClient.exe* in this case.</span></span>  
  
6. <span data-ttu-id="f23fd-140">Ejecute la aplicación cliente como de costumbre.</span><span class="sxs-lookup"><span data-stu-id="f23fd-140">Run the client app as usual.</span></span> <span data-ttu-id="f23fd-141">Se utilizará el ensamblado de serialización generado previamente.</span><span class="sxs-lookup"><span data-stu-id="f23fd-141">The pre-generated serialization assembly will be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f23fd-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f23fd-142">Example</span></span>  

 <span data-ttu-id="f23fd-143">El siguiente comando genera los tipos de serialización para los tipos de `XmlSerializer` utilizados por cualquier contrato de servicios en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f23fd-143">The following command generates serialization types for `XmlSerializer` types that any service contracts in the assembly use.</span></span>  
  
```console  
svcutil /t:xmlserializer myContractLibrary.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="f23fd-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="f23fd-144">See also</span></span>

- [<span data-ttu-id="f23fd-145">Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="f23fd-145">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../servicemodel-metadata-utility-tool-svcutil-exe.md)
