---
title: "Cómo migrar el código del servicio web ASP.NET a Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e528c64f-c027-4f2e-ada6-d8f3994cf8d6
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1d6ed443d2b645687d59a3d795c706f303616cfb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-migrate-aspnet-web-service-code-to-the-windows-communication-foundation"></a><span data-ttu-id="ffeab-102">Cómo migrar el código del servicio web ASP.NET a Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="ffeab-102">How to: Migrate ASP.NET Web Service Code to the Windows Communication Foundation</span></span>
<span data-ttu-id="ffeab-103">El procedimiento siguiente describe cómo migrar un servicio web ASP.NET a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ffeab-103">The following procedure describes how to migrate an ASP.NET Web Service to [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="ffeab-104">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="ffeab-104">Procedure</span></span>  
  
#### <a name="to-migrate-aspnet-web-service-code-to-wcf"></a><span data-ttu-id="ffeab-105">Para migrar un servicio web ASP.NET a WCF</span><span class="sxs-lookup"><span data-stu-id="ffeab-105">To migrate ASP.NET Web service code to WCF</span></span>  
  
1.  <span data-ttu-id="ffeab-106">Asegúrese de que existe un conjunto completo de pruebas para el servicio.</span><span class="sxs-lookup"><span data-stu-id="ffeab-106">Ensure that a comprehensive set of tests exist for the service.</span></span>  
  
2.  <span data-ttu-id="ffeab-107">Genere el WSDL del servicio y guarde una copia en la misma carpeta que el archivo .asmx del servicio.</span><span class="sxs-lookup"><span data-stu-id="ffeab-107">Generate the WSDL for the service and save a copy in the same folder as the service’s .asmx file.</span></span>  
  
3.  <span data-ttu-id="ffeab-108">Actualice el servicio Web ASP.NET para que pueda usar .NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="ffeab-108">Upgrade the ASP.NET Web service to use .NET 2.0.</span></span> <span data-ttu-id="ffeab-109">Implementar primero la versión 2.0 de .NET Framework a la aplicación en IIS y, a continuación, usar Visual Studio 2005 para automatizar el proceso de conversión de código, como se documenta en [guía paso a paso para convertir proyectos Web de Visual Studio .NET 2002/2003 a Visual Studio 2005](http://go.microsoft.com/fwlink/?LinkId=96492).</span><span class="sxs-lookup"><span data-stu-id="ffeab-109">First deploy the .NET Framework 2.0 to the application in IIS, and then use Visual Studio 2005 to automate the code conversion process, as documented in [Step-By-Step Guide to Converting Web Projects from Visual Studio .NET 2002/2003 to Visual Studio 2005](http://go.microsoft.com/fwlink/?LinkId=96492).</span></span> <span data-ttu-id="ffeab-110">Ejecute el conjunto de pruebas.</span><span class="sxs-lookup"><span data-stu-id="ffeab-110">Run the set of tests.</span></span>  
  
4.  <span data-ttu-id="ffeab-111">Proporcione los valores explícitos para `Namespace` y los parámetros `Name` de los atributos <xref:System.Web.Services.WebService>, si aún no se han proporcionado.</span><span class="sxs-lookup"><span data-stu-id="ffeab-111">Provide explicit values for the `Namespace` and `Name` parameters of the <xref:System.Web.Services.WebService> attributes if they are not provided already.</span></span> <span data-ttu-id="ffeab-112">Repita la acción para el parámetro `MessageName` de <xref:System.Web.Services.WebMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ffeab-112">Do the same for the `MessageName` parameter of the <xref:System.Web.Services.WebMethodAttribute>.</span></span> <span data-ttu-id="ffeab-113">Si aún no se han proporcionado los valores explícitos de los encabezados HTTP de SOAPAction mediante los cuales se enrutan las solicitudes a los métodos, especifique explícitamente el valor predeterminado del parámetro `Action` con <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ffeab-113">If explicit values are not already provided for the SOAPAction HTTP headers by which requests are routed to methods, then explicitly specify the default value of the `Action` parameter with a <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span></span>  
  
    ```  
    [WebService(Namespace = "http://tempuri.org/", Name = "Adder")]  
    public class Adder  
    {  
         [WebMethod(MessageName = "Add")]  
         [SoapDocumentMethod(Action = "http://tempuri.org/Add")]  
         public double Add(SumInput input)  
         {  
              double sum = 0.00;  
              foreach (double inputValue in input.Input)  
              {  
                  sum += inputValue;  
              }  
          return sum;  
         }  
    }  
    ```  
  
5.  <span data-ttu-id="ffeab-114">Pruebe el cambio.</span><span class="sxs-lookup"><span data-stu-id="ffeab-114">Test the change.</span></span>  
  
6.  <span data-ttu-id="ffeab-115">Mueva cualquier código sustantivo de los cuerpos de los métodos de la clase, a una clase distinta a la que utiliza la clase original.</span><span class="sxs-lookup"><span data-stu-id="ffeab-115">Move any substantive code in the bodies of the methods of the class to a separate class that the original class is made to use.</span></span>  
  
    ```  
    [WebService(Namespace = "http://tempuri.org/", Name = "Adder")]  
    public class Adder  
    {  
         [WebMethod(MessageName = "Add")]  
         [SoapDocumentMethod(Action = "http://tempuri.org/Add")]  
         public double Add(SumInput input)  
         {  
              return new ActualAdder().Add(input);  
         }  
    }  
  
    internal class ActualAdder  
    {  
         internal double Add(SumInput input)  
         {  
              double sum = 0.00;  
              foreach (double inputValue in input.Input)  
              {  
                  sum += inputValue;  
              }  
          return sum;  
         }  
    }  
    ```  
  
7.  <span data-ttu-id="ffeab-116">Pruebe el cambio.</span><span class="sxs-lookup"><span data-stu-id="ffeab-116">Test the change.</span></span>  
  
8.  <span data-ttu-id="ffeab-117">Agregue las referencias de los ensamblados System.ServiceModel y System.Runtime.Serialization [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] al proyecto de servicio web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ffeab-117">Add references to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] assemblies System.ServiceModel and System.Runtime.Serialization to the ASP.NET Web service project.</span></span>  
  
9. <span data-ttu-id="ffeab-118">Ejecutar [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para generar un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clase de cliente desde el archivo WSDL.</span><span class="sxs-lookup"><span data-stu-id="ffeab-118">Run [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client class from the WSDL.</span></span> <span data-ttu-id="ffeab-119">Agregue el módulo de clase generado a la solución.</span><span class="sxs-lookup"><span data-stu-id="ffeab-119">Add the generated class module to the solution.</span></span>  
  
10. <span data-ttu-id="ffeab-120">El módulo de clase generado en el paso anterior contiene la definición de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="ffeab-120">The class module generated in the preceding step contains the definition of an interface.</span></span>  
  
    ```  
    [System.ServiceModel.ServiceContractAttribute()]  
    public interface AdderSoap  
    {  
         [System.ServiceModel.OperationContractAttribute(  
          Action="http://tempuri.org/Add",   
          ReplyAction="http://tempuri.org/Add")]  
         AddResponse Add(AddRequest request);  
    }  
    ```  
  
     <span data-ttu-id="ffeab-121">Modifique la definición de la clase de servicio web ASP.NET para definir la clase como implementación de esa interfaz, como muestra el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="ffeab-121">Modify the definition of the ASP.NET Web service class so that the class is defined as implementing that interface, as shown in the following sample code.</span></span>  
  
    ```  
    [WebService(Namespace = "http://tempuri.org/", Name = "Adder")]  
    public class Adder: AdderSoap  
    {  
         [WebMethod(MessageName = "Add")]  
         [SoapDocumentMethod(Action = "http://tempuri.org/Add")]  
         public double Add(SumInput input)  
         {  
              return new ActualAdder().Add(input);  
         }  
  
         public AddResponse Add(AddRequest request)  
         {  
            return new AddResponse(  
            new AddResponseBody(  
            this.Add(request.Body.input)));  
         }  
    }  
    ```  
  
11. <span data-ttu-id="ffeab-122">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ffeab-122">Compile the project.</span></span> <span data-ttu-id="ffeab-123">Pueden producirse errores debido a que el código generado en el paso nueve duplicó algunas definiciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="ffeab-123">There may be some errors due to the code generated in step nine that duplicated some type definitions.</span></span> <span data-ttu-id="ffeab-124">Repare esos errores, normalmente eliminando las definiciones de los tipos existentes anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ffeab-124">Repair those errors, usually by deleting the pre-existing definitions of the types.</span></span> <span data-ttu-id="ffeab-125">Pruebe el cambio.</span><span class="sxs-lookup"><span data-stu-id="ffeab-125">Test the change.</span></span>  
  
12. <span data-ttu-id="ffeab-126">Quite los atributos específicos de ASP.NET, como <xref:System.Web.Services.WebService>, <xref:System.Web.Services.WebMethodAttribute> y <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ffeab-126">Remove the ASP.NET-specific attributes, such as the <xref:System.Web.Services.WebService>, <xref:System.Web.Services.WebMethodAttribute> and <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span></span>  
  
    ```  
    public class Adder: AdderSoap  
    {  
         public double Add(SumInput input)  
         {  
              return new ActualAdder().Add(input);  
         }  
  
         public AddResponse Add(AddRequest request)  
         {  
              return new AddResponse(  
             new AddResponseBody(  
            this.Add(request.Body.input)));  
         }  
    }  
    ```  
  
13. <span data-ttu-id="ffeab-127">Configure la clase, que ahora es un tipo de servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], para exigir el modo de compatibilidad de ASP.NET [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] si el servicio web ASP.NET se basa en alguno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="ffeab-127">Configure the class, which is now a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service type, to require [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET compatibility mode if the ASP.NET Web service relied on any of the following:</span></span>  
  
    -   <span data-ttu-id="ffeab-128">La clase <xref:System.Web.HttpContext>.</span><span class="sxs-lookup"><span data-stu-id="ffeab-128">The <xref:System.Web.HttpContext> class.</span></span>  
  
    -   <span data-ttu-id="ffeab-129">Los perfiles ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ffeab-129">The ASP.NET Profiles.</span></span>  
  
    -   <span data-ttu-id="ffeab-130">Las listas ACL en archivos .asmx.</span><span class="sxs-lookup"><span data-stu-id="ffeab-130">ACLs on .asmx files.</span></span>  
  
    -   <span data-ttu-id="ffeab-131">Las opciones de autenticación de IIS.</span><span class="sxs-lookup"><span data-stu-id="ffeab-131">IIS authentication options.</span></span>  
  
    -   <span data-ttu-id="ffeab-132">Las opciones de suplantación de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ffeab-132">ASP.NET impersonation options.</span></span>  
  
    -   <span data-ttu-id="ffeab-133">La globalización de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ffeab-133">ASP.NET globalization.</span></span>  
  
    ```  
    [System.ServiceModel.AspNetCompatibilityRequirements(  
      RequirementsMode=AspNetCompatbilityRequirementsMode.Required)]  
    public class Adder: AdderSoap  
    ```  
  
14. <span data-ttu-id="ffeab-134">Cambie el nombre del archivo .asmx original a .asmx .old.</span><span class="sxs-lookup"><span data-stu-id="ffeab-134">Rename the original .asmx file to .asmx.old.</span></span>  
  
15. <span data-ttu-id="ffeab-135">Cree un archivo de servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con la extensión .asmx y guárdelo en la raíz de la aplicación en IIS.</span><span class="sxs-lookup"><span data-stu-id="ffeab-135">Create a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service file for the service, give it the extension, .asmx, and save it into the application root in IIS.</span></span>  
  
    ```xml  
    <%@Service Class="MyOrganization.Adder" %>  
    <%@Assembly Name="MyServiceAssembly" %>   
    ```  
  
16. <span data-ttu-id="ffeab-136">Agregue una configuración [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para el servicio a su archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="ffeab-136">Add a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configuration for the service to its Web.config file.</span></span> <span data-ttu-id="ffeab-137">Configurar el servicio para utilizar la [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), para usar el archivo de servicio con la extensión .asmx creada en los pasos anteriores y no generar WSDL para sí mismo, pero usar el WSDL del paso dos.</span><span class="sxs-lookup"><span data-stu-id="ffeab-137">Configure the service to use the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), to use the service file with the .asmx extension created in the preceding steps, and to not generate WSDL for itself, but to use the WSDL from step two.</span></span> <span data-ttu-id="ffeab-138">Configúrelo también para utilizar el modo de compatibilidad de ASP.NET, si fuese necesario.</span><span class="sxs-lookup"><span data-stu-id="ffeab-138">Also configure it to use ASP.NET compatibility mode if necessary.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
     <system.web>  
      <compilation>  
      <buildProviders>  
       <remove extension=".asmx" />  
       <add extension=".asmx"   
        type=  
        "System.ServiceModel.Activation.ServiceBuildProvider,  
        T:System.ServiceModel, Version=2.0.0.0,   
       Culture=neutral,   
       PublicKeyToken=b77a5c561934e089" />  
      </buildProviders>  
      </compilation>  
     </system.web>  
     <system.serviceModel>  
      <services>  
      <service name="MyOrganization.Adder "  
        behaviorConfiguration="AdderBehavior">  
       <endpoint   
        address=""  
        binding="basicHttpBinding"  
        contract="AdderSoap "/>  
       </service>  
      </services>  
      <behaviors>  
      <behavior name="AdderBehavior">  
       <metadataPublishing   
        enableMetadataExchange="true"   
        enableGetWsdl="true"   
        enableHelpPage="true"   
        metadataLocation=  
        "http://MyHost.com/AdderService/Service.WSDL"/>  
      </behavior>  
      </behaviors>  
      <serviceHostingEnvironment   
       aspNetCompatibilityEnabled ="true"/>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
17. <span data-ttu-id="ffeab-139">Guarde la configuración.</span><span class="sxs-lookup"><span data-stu-id="ffeab-139">Save the configuration.</span></span>  
  
18. <span data-ttu-id="ffeab-140">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ffeab-140">Compile the project.</span></span>  
  
19. <span data-ttu-id="ffeab-141">Ejecute el conjunto de pruebas para asegurarse de que todos los cambios funcionan.</span><span class="sxs-lookup"><span data-stu-id="ffeab-141">Run the set of tests to make sure all the changes work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffeab-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="ffeab-142">See Also</span></span>  
 [<span data-ttu-id="ffeab-143">Cómo: migrar código de cliente de servicio Web ASP.NET a Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="ffeab-143">How to: Migrate ASP.NET Web Service Client Code to the Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
