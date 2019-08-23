---
title: Procedimiento para registrar y configurar un moniker de servicio
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], configure service monikers
- COM [WCF], register service monikers
ms.assetid: e5e16c80-8a8e-4eef-af53-564933b651ef
ms.openlocfilehash: d14facf435d575b9db5129b732938658c921f97f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934320"
---
# <a name="how-to-register-and-configure-a-service-moniker"></a><span data-ttu-id="0f6f9-102">Procedimiento para registrar y configurar un moniker de servicio</span><span class="sxs-lookup"><span data-stu-id="0f6f9-102">How to: Register and Configure a Service Moniker</span></span>
<span data-ttu-id="0f6f9-103">Antes de utilizar el moniker del servicio Windows Communication Foundation (WCF) dentro de una aplicación COM con un contrato con tipo, debe registrar los tipos con atributos necesarios en COM y configurar la aplicación COM y el moniker con el enlace necesario configuraciones.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-103">Before using the Windows Communication Foundation (WCF) service moniker within a COM application with a typed contract, you must register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
### <a name="to-register-the-required-attributed-types-with-com"></a><span data-ttu-id="0f6f9-104">Para registrar los tipos con atributos necesarios en COM</span><span class="sxs-lookup"><span data-stu-id="0f6f9-104">To register the required attributed types with COM</span></span>  
  
1. <span data-ttu-id="0f6f9-105">Use la herramienta de utilidad de metadatos de [ServiceModel (SvcUtil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para recuperar el contrato de metadatos del servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-105">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool to retrieve the metadata contract from the WCF service.</span></span> <span data-ttu-id="0f6f9-106">Esto genera el código fuente para un ensamblado de cliente de WCF y un archivo de configuración de la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-106">This generates the source code for a WCF client assembly and a client application configuration file.</span></span>  
  
2. <span data-ttu-id="0f6f9-107">Asegúrese de que los tipos del ensamblado se marcan como `ComVisible`.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-107">Ensure that the types in the assembly are marked as `ComVisible`.</span></span> <span data-ttu-id="0f6f9-108">Para hacerlo, agregue el siguiente atributo al archivo AssemblyInfo.cs de su proyecto Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-108">To do so, add the following attribute to the AssemblyInfo.cs file in your Visual Studio project.</span></span>  
  
    ```  
    [assembly: ComVisible(true)]  
    ```  
  
3. <span data-ttu-id="0f6f9-109">Compile el cliente WCF administrado como un ensamblado con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-109">Compile the managed WCF client as a strong-named assembly.</span></span> <span data-ttu-id="0f6f9-110">Para ello se es necesario firmar con un par de claves criptográficas.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-110">This requires signing with a cryptographic key pair.</span></span> <span data-ttu-id="0f6f9-111">Para obtener más información, vea [firmar un ensamblado con un nombre seguro](https://go.microsoft.com/fwlink/?LinkId=94874) en la guía del desarrollador de .net.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-111">For more information, see [Signing an Assembly with a Strong Name](https://go.microsoft.com/fwlink/?LinkId=94874) in the .NET Developer's Guide.</span></span>  
  
4. <span data-ttu-id="0f6f9-112">Utilice la herramienta de registro de ensamblados (Regasm.exe) con la opción `/tlb` para registrar los tipos del ensamblado en COM.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-112">Use the Assembly Registration (Regasm.exe) tool with the `/tlb` option to register the types in the assembly with COM.</span></span>  
  
5. <span data-ttu-id="0f6f9-113">Use la herramienta de la caché global de ensamblados (Gacutil.exe) para agregar el ensamblado a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-113">Use the Global Assembly Cache (Gacutil.exe) tool to add the assembly to the global assembly cache.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0f6f9-114">Firmar y agregar el ensamblado a la caché global de ensamblados son pasos opcionales, pero permiten simplificar el proceso de carga del ensamblado desde la ubicación correcta en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-114">Signing the assembly and adding it to the Global Assembly Cache are optional steps, but they can simplify the process of loading the assembly from the correct location at runtime.</span></span>  
  
### <a name="to-configure-the-com-application-and-the-moniker-with-the-required-binding-configuration"></a><span data-ttu-id="0f6f9-115">Para configurar la aplicación COM y el moniker con la configuración de enlace necesaria</span><span class="sxs-lookup"><span data-stu-id="0f6f9-115">To configure the COM application and the moniker with the required binding configuration</span></span>  
  
- <span data-ttu-id="0f6f9-116">Coloque las definiciones de enlace (generadas por la herramienta de utilidad de metadatos de [ServiceModel (SvcUtil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) en el archivo de configuración de la aplicación cliente generada) en el archivo de configuración de la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-116">Place the binding definitions (generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) in the generated client application configuration file) in the client application's configuration file.</span></span> <span data-ttu-id="0f6f9-117">Por ejemplo, para un ejecutable de Visual Basic 6.0 denominado CallCenterClient.exe, la configuración debe encontrarse en un archivo denominado CallCenterConfig.exe.config en el mismo directorio que la aplicación ejecutable.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-117">For example, for a Visual Basic 6.0 executable named CallCenterClient.exe, the configuration should be placed in a file named CallCenterConfig.exe.config within the same directory as the executable.</span></span> <span data-ttu-id="0f6f9-118">De este modo la aplicación cliente puede utilizar el moniker.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-118">The client application can now use the moniker.</span></span> <span data-ttu-id="0f6f9-119">Tenga en cuenta que la configuración de enlace no es necesaria si se usa uno de los tipos de enlace estándar que proporciona WCF.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-119">Note that the binding configuration is not required if using one of the standard binding types provided by WCF.</span></span>  
  
     <span data-ttu-id="0f6f9-120">El siguiente tipo está registrado:</span><span class="sxs-lookup"><span data-stu-id="0f6f9-120">The following type is registered.</span></span>  
  
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
  
     <span data-ttu-id="0f6f9-121">La aplicación se expone mediante un enlace `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-121">The application is exposed using a `wsHttpBinding` binding.</span></span> <span data-ttu-id="0f6f9-122">Para el tipo y configuración de aplicación especificados, se utilizan las siguientes cadenas moniker de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-122">For the given type and application configuration, the following example moniker strings are used.</span></span>  
  
    ```  
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1  
    ```  
  
     `or`  
  
    ```  
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1, contract={36ADAD5A-A944-4d5c-9B7C-967E4F00A090}  
    ```  
  
     <span data-ttu-id="0f6f9-123">Puede utilizar cualquiera de estas cadenas moniker desde una aplicación de Visual Basic 6.0, siempre que agregue una referencia al ensamblado que contiene los tipos `IMathService`, como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-123">You can use either of these moniker strings from within a Visual Basic 6.0 application, after adding a reference to the assembly that contains the `IMathService` types, as shown in the following sample code.</span></span>  
  
    ```  
    Dim MathProxy As IMathService  
    Dim result As Integer  
  
    Set MathProxy = GetObject( _  
            "service4:address=http://localhost/MathService, _  
            binding=wsHttpBinding, _  
            bindingConfiguration=Binding1")  
  
    result = MathProxy.Add(3, 5)  
    ```  
  
     <span data-ttu-id="0f6f9-124">En este ejemplo, la definición de la configuración del enlace `Binding1` se almacena en un archivo de configuración con un nombre adecuado, por ejemplo vb6appname.exe.config.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-124">In this example, the definition for the binding configuration `Binding1` is stored in a suitably named configuration file for the client application, such as vb6appname.exe.config.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0f6f9-125">Puede utilizar un código similar en una aplicación C#, C++, o cualquier otra aplicación de lenguaje .NET.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-125">You can use similar code in a C#, a C++, or any other .NET Language application.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0f6f9-126">: Si el moniker tiene un formato incorrecto o si el servicio no está disponible, `GetObject` la llamada a devuelve un error de "sintaxis no válida".</span><span class="sxs-lookup"><span data-stu-id="0f6f9-126">: If the moniker is malformed or if the service is unavailable, the call to `GetObject` returns an error of "Invalid Syntax".</span></span> <span data-ttu-id="0f6f9-127">Si recibe este error, asegúrese de que el moniker que está utilizando es correcto y el servicio está disponible.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-127">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
     <span data-ttu-id="0f6f9-128">Aunque este tema se centra en la utilización del moniker de servicio del código de VB 6.0, puede utilizar un moniker de servicio de otros lenguajes.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-128">Although this topic focuses on using the service moniker from VB 6.0 code, you can use a service moniker from other languages.</span></span> <span data-ttu-id="0f6f9-129">Si utiliza un moniker del código de C++, deberá importar el ensamblado generado por Svcutil.exe con "no_namespace named_guids raw_interfaces_only", como se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-129">When using a moniker from C++ code the Svcutil.exe generated assembly should be imported with "no_namespace named_guids raw_interfaces_only" as shown in the following code.</span></span>  
  
    ```  
    #import "ComTestProxy.tlb" no_namespace named_guids  
    ```  
  
     <span data-ttu-id="0f6f9-130">De este modo se modifican las definiciones de la interfaz importada para que todos los métodos devuelvan `HResult`.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-130">This modifies the imported interface definitions so that all methods return an `HResult`.</span></span> <span data-ttu-id="0f6f9-131">Cualquier otro valor devuelto se convierte en parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-131">Any other return values are converted into out parameters.</span></span> <span data-ttu-id="0f6f9-132">La ejecución global de los métodos sigue siendo la misma.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-132">The overall execution of the methods remains the same.</span></span> <span data-ttu-id="0f6f9-133">Esto permite determinar la causa de una excepción al llamar a un método en el proxy.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-133">This allows you to determine the cause of an exception when calling a method on the proxy.</span></span> <span data-ttu-id="0f6f9-134">Esta funcionalidad sólo está disponible en el código de C++.</span><span class="sxs-lookup"><span data-stu-id="0f6f9-134">This functionality is only available from C++ code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f6f9-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f6f9-135">See also</span></span>

- [<span data-ttu-id="0f6f9-136">Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="0f6f9-136">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
