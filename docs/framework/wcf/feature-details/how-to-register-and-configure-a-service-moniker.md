---
title: Procedimiento para registrar y configurar un moniker de servicio
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], configure service monikers
- COM [WCF], register service monikers
ms.assetid: e5e16c80-8a8e-4eef-af53-564933b651ef
ms.openlocfilehash: dfac833cc7517af00d0264fc5d11fc83ae543569
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000810"
---
# <a name="how-to-register-and-configure-a-service-moniker"></a><span data-ttu-id="fe9e5-102">Procedimiento para registrar y configurar un moniker de servicio</span><span class="sxs-lookup"><span data-stu-id="fe9e5-102">How to: Register and Configure a Service Moniker</span></span>
<span data-ttu-id="fe9e5-103">Antes de utilizar el moniker de servicio de Windows Communication Foundation (WCF) dentro de una aplicación de COM con un contrato con tipo, debe registrar los tipos con atributos necesarios con COM y configurar la aplicación COM y el moniker con el enlace necesaria configuración.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-103">Before using the Windows Communication Foundation (WCF) service moniker within a COM application with a typed contract, you must register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
### <a name="to-register-the-required-attributed-types-with-com"></a><span data-ttu-id="fe9e5-104">Para registrar los tipos con atributos necesarios en COM</span><span class="sxs-lookup"><span data-stu-id="fe9e5-104">To register the required attributed types with COM</span></span>  
  
1. <span data-ttu-id="fe9e5-105">Use la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) herramienta para recuperar el contrato de metadatos del servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-105">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool to retrieve the metadata contract from the WCF service.</span></span> <span data-ttu-id="fe9e5-106">Esto genera el código fuente para un ensamblado de cliente WCF y un archivo de configuración de la aplicación de cliente.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-106">This generates the source code for a WCF client assembly and a client application configuration file.</span></span>  
  
2. <span data-ttu-id="fe9e5-107">Asegúrese de que los tipos del ensamblado se marcan como `ComVisible`.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-107">Ensure that the types in the assembly are marked as `ComVisible`.</span></span> <span data-ttu-id="fe9e5-108">Para hacerlo, agregue el siguiente atributo al archivo AssemblyInfo.cs de su proyecto Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-108">To do so, add the following attribute to the AssemblyInfo.cs file in your Visual Studio project.</span></span>  
  
    ```  
    [assembly: ComVisible(true)]  
    ```  
  
3. <span data-ttu-id="fe9e5-109">Compile el cliente WCF administrado como un ensamblado con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-109">Compile the managed WCF client as a strong-named assembly.</span></span> <span data-ttu-id="fe9e5-110">Para ello se es necesario firmar con un par de claves criptográficas.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-110">This requires signing with a cryptographic key pair.</span></span> <span data-ttu-id="fe9e5-111">Para obtener más información, consulte [firmar un ensamblado con un nombre seguro](https://go.microsoft.com/fwlink/?LinkId=94874) en la Guía del desarrollador. NET.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-111">For more information, see [Signing an Assembly with a Strong Name](https://go.microsoft.com/fwlink/?LinkId=94874) in the .NET Developer's Guide.</span></span>  
  
4. <span data-ttu-id="fe9e5-112">Utilice la herramienta de registro de ensamblados (Regasm.exe) con la opción `/tlb` para registrar los tipos del ensamblado en COM.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-112">Use the Assembly Registration (Regasm.exe) tool with the `/tlb` option to register the types in the assembly with COM.</span></span>  
  
5. <span data-ttu-id="fe9e5-113">Use la herramienta de la caché global de ensamblados (Gacutil.exe) para agregar el ensamblado a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-113">Use the Global Assembly Cache (Gacutil.exe) tool to add the assembly to the global assembly cache.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fe9e5-114">Firmar y agregar el ensamblado a la caché global de ensamblados son pasos opcionales, pero permiten simplificar el proceso de carga del ensamblado desde la ubicación correcta en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-114">Signing the assembly and adding it to the Global Assembly Cache are optional steps, but they can simplify the process of loading the assembly from the correct location at runtime.</span></span>  
  
### <a name="to-configure-the-com-application-and-the-moniker-with-the-required-binding-configuration"></a><span data-ttu-id="fe9e5-115">Para configurar la aplicación COM y el moniker con la configuración de enlace necesaria</span><span class="sxs-lookup"><span data-stu-id="fe9e5-115">To configure the COM application and the moniker with the required binding configuration</span></span>  
  
- <span data-ttu-id="fe9e5-116">Coloque las definiciones de enlace (generadas por el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) en el archivo de configuración de la aplicación de cliente generado) en el archivo de configuración de la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-116">Place the binding definitions (generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) in the generated client application configuration file) in the client application's configuration file.</span></span> <span data-ttu-id="fe9e5-117">Por ejemplo, para un ejecutable de Visual Basic 6.0 denominado CallCenterClient.exe, la configuración debe encontrarse en un archivo denominado CallCenterConfig.exe.config en el mismo directorio que la aplicación ejecutable.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-117">For example, for a Visual Basic 6.0 executable named CallCenterClient.exe, the configuration should be placed in a file named CallCenterConfig.exe.config within the same directory as the executable.</span></span> <span data-ttu-id="fe9e5-118">De este modo la aplicación cliente puede utilizar el moniker.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-118">The client application can now use the moniker.</span></span> <span data-ttu-id="fe9e5-119">Tenga en cuenta que la configuración de enlace no es necesaria si usa uno de lo tipos proporcionados por WCF de enlace estándar.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-119">Note that the binding configuration is not required if using one of the standard binding types provided by WCF.</span></span>  
  
     <span data-ttu-id="fe9e5-120">El siguiente tipo está registrado:</span><span class="sxs-lookup"><span data-stu-id="fe9e5-120">The following type is registered.</span></span>  
  
    ```  
    using System.ServiceModel;  
  
    ...  
  
    [ServiceContract]   
    public interface IMathService   
    {  
    [OperationContract]  
    public int Add(int x, int y);  
    [OperationContract]  
    public int Subtract(int x, int y);  
    }  
    ```  
  
     <span data-ttu-id="fe9e5-121">La aplicación se expone mediante un enlace `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-121">The application is exposed using a `wsHttpBinding` binding.</span></span> <span data-ttu-id="fe9e5-122">Para el tipo y configuración de aplicación especificados, se utilizan las siguientes cadenas moniker de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-122">For the given type and application configuration, the following example moniker strings are used.</span></span>  
  
    ```  
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1  
    ```  
  
     `or`  
  
    ```  
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1, contract={36ADAD5A-A944-4d5c-9B7C-967E4F00A090}  
    ```  
  
     <span data-ttu-id="fe9e5-123">Puede utilizar cualquiera de estas cadenas moniker desde una aplicación de Visual Basic 6.0, siempre que agregue una referencia al ensamblado que contiene los tipos `IMathService`, como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-123">You can use either of these moniker strings from within a Visual Basic 6.0 application, after adding a reference to the assembly that contains the `IMathService` types, as shown in the following sample code.</span></span>  
  
    ```  
    Dim MathProxy As IMathService  
    Dim result As Integer  
  
    Set MathProxy = GetObject( _  
            "service4:address=http://localhost/MathService, _  
            binding=wsHttpBinding, _  
            bindingConfiguration=Binding1")  
  
    result = MathProxy.Add(3, 5)  
    ```  
  
     <span data-ttu-id="fe9e5-124">En este ejemplo, la definición de la configuración del enlace `Binding1` se almacena en un archivo de configuración con un nombre adecuado, por ejemplo vb6appname.exe.config.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-124">In this example, the definition for the binding configuration `Binding1` is stored in a suitably named configuration file for the client application, such as vb6appname.exe.config.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fe9e5-125">Puede utilizar un código similar en una aplicación C#, C++, o cualquier otra aplicación de lenguaje .NET.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-125">You can use similar code in a C#, a C++, or any other .NET Language application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fe9e5-126">: Si el moniker es incorrecto o si el servicio no está disponible, la llamada a `GetObject` devuelve un error "Sintaxis no válida".</span><span class="sxs-lookup"><span data-stu-id="fe9e5-126">: If the moniker is malformed or if the service is unavailable, the call to `GetObject` returns an error of "Invalid Syntax".</span></span> <span data-ttu-id="fe9e5-127">Si recibe este error, asegúrese de que el moniker que está utilizando es correcto y el servicio está disponible.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-127">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
     <span data-ttu-id="fe9e5-128">Aunque este tema se centra en la utilización del moniker de servicio del código de VB 6.0, puede utilizar un moniker de servicio de otros lenguajes.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-128">Although this topic focuses on using the service moniker from VB 6.0 code, you can use a service moniker from other languages.</span></span> <span data-ttu-id="fe9e5-129">Si utiliza un moniker del código de C++, deberá importar el ensamblado generado por Svcutil.exe con "no_namespace named_guids raw_interfaces_only", como se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-129">When using a moniker from C++ code the Svcutil.exe generated assembly should be imported with "no_namespace named_guids raw_interfaces_only" as shown in the following code.</span></span>  
  
    ```  
    #import "ComTestProxy.tlb" no_namespace named_guids  
    ```  
  
     <span data-ttu-id="fe9e5-130">De este modo se modifican las definiciones de la interfaz importada para que todos los métodos devuelvan `HResult`.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-130">This modifies the imported interface definitions so that all methods return an `HResult`.</span></span> <span data-ttu-id="fe9e5-131">Cualquier otro valor devuelto se convierte en parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-131">Any other return values are converted into out parameters.</span></span> <span data-ttu-id="fe9e5-132">La ejecución global de los métodos sigue siendo la misma.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-132">The overall execution of the methods remains the same.</span></span> <span data-ttu-id="fe9e5-133">Esto permite determinar la causa de una excepción al llamar a un método en el proxy.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-133">This allows you to determine the cause of an exception when calling a method on the proxy.</span></span> <span data-ttu-id="fe9e5-134">Esta funcionalidad sólo está disponible en el código de C++.</span><span class="sxs-lookup"><span data-stu-id="fe9e5-134">This functionality is only available from C++ code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe9e5-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe9e5-135">See also</span></span>

- [<span data-ttu-id="fe9e5-136">Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="fe9e5-136">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
