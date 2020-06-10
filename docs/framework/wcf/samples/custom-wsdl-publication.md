---
title: Publicación de WSDL personalizada
ms.date: 03/30/2017
ms.assetid: 3b3e8103-2c95-4db3-a05b-46aa8e9d4d29
ms.openlocfilehash: b18ac2f72d58c768b3784e1c414a71cdaec50c01
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596700"
---
# <a name="custom-wsdl-publication"></a><span data-ttu-id="feb71-102">Publicación de WSDL personalizada</span><span class="sxs-lookup"><span data-stu-id="feb71-102">Custom WSDL Publication</span></span>
<span data-ttu-id="feb71-103">En este ejemplo se muestra cómo:</span><span class="sxs-lookup"><span data-stu-id="feb71-103">This sample demonstrates how to:</span></span>  
  
- <span data-ttu-id="feb71-104">Implementar <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> en un atributo <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> personalizado para exportar las propiedades de atributo como anotaciones de WSDL.</span><span class="sxs-lookup"><span data-stu-id="feb71-104">Implement a <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> on a custom <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> attribute to export attribute properties as WSDL annotations.</span></span>  
  
- <span data-ttu-id="feb71-105">Implementar <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> para importar las anotaciones de WSDL personalizadas.</span><span class="sxs-lookup"><span data-stu-id="feb71-105">Implement <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> to import the custom WSDL annotations.</span></span>  
  
- <span data-ttu-id="feb71-106">Implementar <xref:System.ServiceModel.Description.IServiceContractGenerationExtension?displayProperty=nameWithType> y <xref:System.ServiceModel.Description.IOperationContractGenerationExtension?displayProperty=nameWithType> en un comportamiento de contrato personalizado y un comportamiento de operación personalizado, respectivamente, para escribir las anotaciones importadas como comentarios en CodeDom para el contrato y operación importados.</span><span class="sxs-lookup"><span data-stu-id="feb71-106">Implement <xref:System.ServiceModel.Description.IServiceContractGenerationExtension?displayProperty=nameWithType> and <xref:System.ServiceModel.Description.IOperationContractGenerationExtension?displayProperty=nameWithType> on a custom contract behavior and a custom operation behavior, respectively, to write imported annotations as comments in the CodeDom for the imported contract and operation.</span></span>  
  
- <span data-ttu-id="feb71-107">Utilice <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> para descargar WSDL, <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> para importar el WSDL mediante el importador de WSDL personalizado y <xref:System.ServiceModel.Description.ServiceContractGenerator?displayProperty=nameWithType> para generar el código de cliente de Windows Communication Foundation (WCF) con las anotaciones de WSDL como comentarios de///y ' ' ' en C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="feb71-107">Use the <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> to download the WSDL, a <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> to import the WSDL using the custom WSDL importer, and the <xref:System.ServiceModel.Description.ServiceContractGenerator?displayProperty=nameWithType> to generate Windows Communication Foundation (WCF) client code with the WSDL annotations as /// and ''' comments in C# and Visual Basic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="feb71-108">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="feb71-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="service"></a><span data-ttu-id="feb71-109">web de Office</span><span class="sxs-lookup"><span data-stu-id="feb71-109">Service</span></span>  
 <span data-ttu-id="feb71-110">El servicio en este ejemplo se marca con dos atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="feb71-110">The service in this sample is marked with two custom attributes.</span></span> <span data-ttu-id="feb71-111">El primero, `WsdlDocumentationAttribute`, acepta una cadena en el constructor y se aplica para proporcionar una interfaz u operación de contrato con una cadena que describe su uso.</span><span class="sxs-lookup"><span data-stu-id="feb71-111">The first, the `WsdlDocumentationAttribute`, accepts a string in the constructor and can be applied to provide a contract interface or operation with a string that describes its usage.</span></span> <span data-ttu-id="feb71-112">El segundo, `WsdlParamOrReturnDocumentationAttribute`, se puede aplicar para devolver valores o parámetros a fin de describir esos valores en la operación.</span><span class="sxs-lookup"><span data-stu-id="feb71-112">The second, `WsdlParamOrReturnDocumentationAttribute`, can be applied to return values or parameters to describe those values in the operation.</span></span> <span data-ttu-id="feb71-113">El ejemplo siguiente muestra un contrato de servicios, `ICalculator`, descrito utilizando estos atributos.</span><span class="sxs-lookup"><span data-stu-id="feb71-113">The following example shows a service contract, `ICalculator`, described using these attributes.</span></span>  
  
```csharp  
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
// Document it.  
[WsdlDocumentation("The ICalculator contract performs basic calculation services.")]  
public interface ICalculator  
{  
    [OperationContract]  
    [WsdlDocumentation("The Add operation adds two numbers and returns the result.")]  
    [return:WsdlParamOrReturnDocumentation("The result of adding the two arguments together.")]  
    double Add(  
      [WsdlParamOrReturnDocumentation("The first value to add.")]double n1,
      [WsdlParamOrReturnDocumentation("The second value to add.")]double n2  
    );  
  
    [OperationContract]  
    [WsdlDocumentation("The Subtract operation subtracts the second argument from the first.")]  
    [return:WsdlParamOrReturnDocumentation("The result of the second argument subtracted from the first.")]  
    double Subtract(  
      [WsdlParamOrReturnDocumentation("The value from which the second is subtracted.")]double n1,
      [WsdlParamOrReturnDocumentation("The value that is subtracted from the first.")]double n2  
    );  
  
    [OperationContract]  
    [WsdlDocumentation("The Multiply operation multiplies two values.")]  
    [return:WsdlParamOrReturnDocumentation("The result of multiplying the first and second arguments.")]  
    double Multiply(  
      [WsdlParamOrReturnDocumentation("The first value to multiply.")]double n1,
      [WsdlParamOrReturnDocumentation("The second value to multiply.")]double n2  
    );  
  
    [OperationContract]  
    [WsdlDocumentation("The Divide operation returns the value of the first argument divided by the second argument.")]  
    [return:WsdlParamOrReturnDocumentation("The result of dividing the first argument by the second.")]  
    double Divide(  
      [WsdlParamOrReturnDocumentation("The numerator.")]double n1,
      [WsdlParamOrReturnDocumentation("The denominator.")]double n2  
    );  
}  
```  
  
 <span data-ttu-id="feb71-114">`WsdlDocumentationAttribute` implementa <xref:System.ServiceModel.Description.IContractBehavior> y <xref:System.ServiceModel.Description.IOperationBehavior>, por lo que las instancias de atributo se agregan al <xref:System.ServiceModel.Description.ContractDescription> correspondiente o a <xref:System.ServiceModel.Description.OperationDescription> cuando se abre el servicio.</span><span class="sxs-lookup"><span data-stu-id="feb71-114">The `WsdlDocumentationAttribute` implements <xref:System.ServiceModel.Description.IContractBehavior> and <xref:System.ServiceModel.Description.IOperationBehavior>, so the attribute instances are added to the corresponding <xref:System.ServiceModel.Description.ContractDescription> or <xref:System.ServiceModel.Description.OperationDescription> when the service is opened.</span></span> <span data-ttu-id="feb71-115">El atributo también implementa <xref:System.ServiceModel.Description.IWsdlExportExtension>.</span><span class="sxs-lookup"><span data-stu-id="feb71-115">The attribute also implements <xref:System.ServiceModel.Description.IWsdlExportExtension>.</span></span> <span data-ttu-id="feb71-116">Cuando se llama a <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%28System.ServiceModel.Description.WsdlExporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29>, <xref:System.ServiceModel.Description.WsdlExporter> que se utiliza para exportar los metadatos y <xref:System.ServiceModel.Description.WsdlContractConversionContext> que contiene los objetos de descripción de servicio se pasan como parámetros que habilitan la modificación de metadatos exportados.</span><span class="sxs-lookup"><span data-stu-id="feb71-116">When <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%28System.ServiceModel.Description.WsdlExporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> is called, the <xref:System.ServiceModel.Description.WsdlExporter> that is used to export the metadata and the <xref:System.ServiceModel.Description.WsdlContractConversionContext> that contains the service description objects are passed in as parameters enabling the modification of the exported metadata.</span></span>  
  
 <span data-ttu-id="feb71-117">En este ejemplo y en función de si el objeto de contexto de la exportación tiene <xref:System.ServiceModel.Description.ContractDescription> o <xref:System.ServiceModel.Description.OperationDescription>, se extrae un comentario del atributo utilizando la propiedad del texto y se agrega al elemento de anotación de WSDL en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="feb71-117">In this sample, depending upon whether the export context object has a <xref:System.ServiceModel.Description.ContractDescription> or an <xref:System.ServiceModel.Description.OperationDescription>, a comment is extracted from the attribute using the text property and is added to the WSDL annotation element as shown in the following code.</span></span>  
  
```csharp
public void ExportContract(WsdlExporter exporter, WsdlContractConversionContext context)
{
    if (contractDescription != null)
    {
        // Inside this block it is the contract-level comment attribute.
        // This.Text returns the string for the contract attribute.
        // Set the doc element; if this isn't done first, there is no XmlElement in the
        // DocumentElement property.
        context.WsdlPortType.Documentation = string.Empty;
        // Contract comments.
        XmlDocument owner = context.WsdlPortType.DocumentationElement.OwnerDocument;
        XmlElement summaryElement = owner.CreateElement("summary");
        summaryElement.InnerText = this.Text;
        context.WsdlPortType.DocumentationElement.AppendChild(summaryElement);
    }
    else
    {
        Operation operation = context.GetOperation(operationDescription);
        if (operation != null)
        {
            // We are dealing strictly with the operation here.
            // This.Text returns the string for the operation-level attributes.
            // Set the doc element; if this isn't done first, there is no XmlElement in the
            // DocumentElement property.
            operation.Documentation = String.Empty;

            // Operation C# triple comments.
            XmlDocument owner = operation.DocumentationElement.OwnerDocument;
            XmlElement newSummaryElement = owner.CreateElement("summary");
            newSummaryElement.InnerText = this.Text;
            operation.DocumentationElement.AppendChild(newSummaryElement);
        }
    }
}
```  
  
 <span data-ttu-id="feb71-118">Si se exporta una operación, el ejemplo utiliza la reflexión para obtener cualquier valor `WsdlParamOrReturnDocumentationAttribute` para los parámetros y valores devueltos y los agrega a los elementos de anotación de WSDL para esa operación de la manera que se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="feb71-118">If an operation is being exported, the sample uses reflection to obtain any `WsdlParamOrReturnDocumentationAttribute` values for parameters and return values and adds them to the WSDL annotation elements for that operation as follows.</span></span>  
  
```csharp
// Get returns information  
ParameterInfo returnValue = operationDescription.SyncMethod.ReturnParameter;  
object[] returnAttrs = returnValue.GetCustomAttributes(typeof(WsdlParamOrReturnDocumentationAttribute), false);  
if (returnAttrs.Length != 0)  
{  
    // <returns>text.</returns>  
    XmlElement returnsElement = owner.CreateElement("returns");  
    returnsElement.InnerText = ((WsdlParamOrReturnDocumentationAttribute)returnAttrs[0]).ParamComment;  
    operation.DocumentationElement.AppendChild(returnsElement);  
}  
  
// Get parameter information.  
ParameterInfo[] args = operationDescription.SyncMethod.GetParameters();  
for (int i = 0; i < args.Length; i++)  
{  
    object[] docAttrs = args[i].GetCustomAttributes(typeof(WsdlParamOrReturnDocumentationAttribute), false);  
    if (docAttrs.Length == 1)  
    {  
        // <param name="Int1">Text.</param>  
        XmlElement newParamElement = owner.CreateElement("param");  
        XmlAttribute paramName = owner.CreateAttribute("name");  
        paramName.Value = args[i].Name;  
        newParamElement.InnerText = ((WsdlParamOrReturnDocumentationAttribute)docAttrs[0]).ParamComment;  
        newParamElement.Attributes.Append(paramName);  
        operation.DocumentationElement.AppendChild(newParamElement);  
    }  
}  
```  
  
 <span data-ttu-id="feb71-119">El ejemplo publica a continuación los metadatos de manera estándar, utilizando el archivo de configuración siguiente.</span><span class="sxs-lookup"><span data-stu-id="feb71-119">The sample then publishes metadata in the standard way, using the following configuration file.</span></span>  
  
```xml  
<services>  
  <service
      name="Microsoft.ServiceModel.Samples.CalculatorService"  
      behaviorConfiguration="CalculatorServiceBehavior">  
    <!-- ICalculator is exposed at the base address provided by host: http://localhost/servicemodelsamples/service.svc  -->  
    <endpoint address=""  
              binding="wsHttpBinding"  
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    <!-- the mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex -->  
    <endpoint address="mex"  
              binding="mexHttpBinding"  
              contract="IMetadataExchange" />  
  </service>  
</services>  
  
<!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="svcutil-client"></a><span data-ttu-id="feb71-120">Cliente de Svcutil</span><span class="sxs-lookup"><span data-stu-id="feb71-120">Svcutil client</span></span>  
 <span data-ttu-id="feb71-121">Este ejemplo no utiliza Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="feb71-121">This sample does not use Svcutil.exe.</span></span> <span data-ttu-id="feb71-122">El contrato se proporciona en el archivo generatedClient.cs para que después de que el ejemplo muestre la importación de WSDL y la generación de código personalizadas, se pueda invocar el servicio.</span><span class="sxs-lookup"><span data-stu-id="feb71-122">The contract is provided in the generatedClient.cs file so that after the sample demonstrates custom WSDL import and code generation, the service can be invoked.</span></span> <span data-ttu-id="feb71-123">Para utilizar al importador del WSDL personalizado siguiente para obtener este ejemplo, puede ejecutar Svcutil.exe y especificar la opción `/svcutilConfig`, dando la ruta de acceso al archivo de configuración del cliente utilizado en este ejemplo, que hace referencia a la biblioteca `WsdlDocumentation.dll`.</span><span class="sxs-lookup"><span data-stu-id="feb71-123">To use the following custom WSDL importer for this example, you can run Svcutil.exe and specify the `/svcutilConfig` option, giving the path to the client configuration file used in this sample, which references the `WsdlDocumentation.dll` library.</span></span> <span data-ttu-id="feb71-124">Para cargar `WsdlDocumentationImporter`, sin embargo, Svuctil.exe debe poder buscar y cargar la biblioteca `WsdlDocumentation.dll`, que significa que se registra en la memoria caché global de ensamblados, en la ruta de acceso o está en el mismo directorio que Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="feb71-124">To load the `WsdlDocumentationImporter`, however, Svuctil.exe must be able to locate and load the `WsdlDocumentation.dll` library, which means either that it is registered in the global assembly cache, in the path, or is in the same directory as Svcutil.exe.</span></span> <span data-ttu-id="feb71-125">Para obtener un ejemplo básico como este, lo más fácil es copiar Svcutil.exe y el archivo de configuración del cliente en el mismo directorio que `WsdlDocumentation.dll` y ejecutarlo desde allí.</span><span class="sxs-lookup"><span data-stu-id="feb71-125">For a basic sample such as this, the easiest thing to do is to copy Svcutil.exe and the client configuration file into the same directory as `WsdlDocumentation.dll` and run it from there.</span></span>  
  
## <a name="the-custom-wsdl-importer"></a><span data-ttu-id="feb71-126">Importador de WSDL personalizado</span><span class="sxs-lookup"><span data-stu-id="feb71-126">The Custom WSDL Importer</span></span>  
 <span data-ttu-id="feb71-127">El objeto <xref:System.ServiceModel.Description.IWsdlImportExtension> personalizado `WsdlDocumentationImporter` también implementa <xref:System.ServiceModel.Description.IContractBehavior> y <xref:System.ServiceModel.Description.IOperationBehavior> para que se agreguen al ServiceEndpoints importado y <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> y <xref:System.ServiceModel.Description.IOperationContractGenerationExtension> para que se invoquen con objeto de modificar la generación de código cuando se cree el contrato o el código de operación.</span><span class="sxs-lookup"><span data-stu-id="feb71-127">The custom <xref:System.ServiceModel.Description.IWsdlImportExtension> object `WsdlDocumentationImporter` also implements <xref:System.ServiceModel.Description.IContractBehavior> and <xref:System.ServiceModel.Description.IOperationBehavior> to be added to the imported ServiceEndpoints and <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> and <xref:System.ServiceModel.Description.IOperationContractGenerationExtension> to be invoked to modify the code generation when the contract or operation code is being created.</span></span>  
  
 <span data-ttu-id="feb71-128">Primero, en el método <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29>, el ejemplo determina si la anotación de WSDL está en el contrato o nivel de la operación, y se agrega como un comportamiento en el ámbito adecuado, pasando el texto de la anotación importado a su constructor.</span><span class="sxs-lookup"><span data-stu-id="feb71-128">First, in the <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> method, the sample determines whether the WSDL annotation is at the contract or operation level, and adds itself as a behavior at the appropriate scope, passing the imported annotation text to its constructor.</span></span>  
  
```csharp
public void ImportContract(WsdlImporter importer, WsdlContractConversionContext context)  
{  
    // Contract Documentation  
    if (context.WsdlPortType.Documentation != null)  
    {  
        // System examines the contract behaviors to see whether any implement IWsdlImportExtension.  
        context.Contract.Behaviors.Add(new WsdlDocumentationImporter(context.WsdlPortType.Documentation));  
    }  
    // Operation Documentation  
    foreach (Operation operation in context.WsdlPortType.Operations)  
    {  
        if (operation.Documentation != null)  
        {  
            OperationDescription operationDescription = context.Contract.Operations.Find(operation.Name);  
            if (operationDescription != null)  
            {  
                // System examines the operation behaviors to see whether any implement IWsdlImportExtension.  
                operationDescription.Behaviors.Add(new WsdlDocumentationImporter(operation.Documentation));  
            }  
        }  
    }  
}  
```  
  
 <span data-ttu-id="feb71-129">A continuación, cuando se genera el código, el sistema invoca los métodos <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> y <xref:System.ServiceModel.Description.IOperationContractGenerationExtension.GenerateOperation%28System.ServiceModel.Description.OperationContractGenerationContext%29>, pasando la información de contexto adecuada.</span><span class="sxs-lookup"><span data-stu-id="feb71-129">Then, when the code is generated, the system invokes the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> and <xref:System.ServiceModel.Description.IOperationContractGenerationExtension.GenerateOperation%28System.ServiceModel.Description.OperationContractGenerationContext%29> methods, passing the appropriate context information.</span></span> <span data-ttu-id="feb71-130">El ejemplo da formato a las anotaciones de WSDL personalizadas y las inserta como comentarios en CodeDom.</span><span class="sxs-lookup"><span data-stu-id="feb71-130">The sample formats the custom WSDL annotations and inserts them as comments into the CodeDom.</span></span>  
  
```csharp
public void GenerateContract(ServiceContractGenerationContext context)  
{  
    Debug.WriteLine("In generate contract.");  
    context.ContractType.Comments.AddRange(FormatComments(text));  
}  
  
public void GenerateOperation(OperationContractGenerationContext context)  
{  
    context.SyncMethod.Comments.AddRange(FormatComments(text));  
    Debug.WriteLine("In generate operation.");  
}  
```  
  
## <a name="the-client-application"></a><span data-ttu-id="feb71-131">Aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="feb71-131">The Client Application</span></span>  
 <span data-ttu-id="feb71-132">La aplicación cliente carga al importador de WSDL personalizado especificándolo en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="feb71-132">The client application loads the custom WSDL importer by specifying it in the application configuration file.</span></span>  
  
```xml  
<client>  
  <endpoint address="http://localhost/servicemodelsamples/service.svc"
  binding="wsHttpBinding"
  contract="ICalculator" />  
  <metadata>  
    <wsdlImporters>  
      <extension type="Microsoft.ServiceModel.Samples.WsdlDocumentationImporter, WsdlDocumentation"/>  
    </wsdlImporters>  
  </metadata>  
</client>  
```  
  
 <span data-ttu-id="feb71-133">Una vez que se ha especificado el importador personalizado, el sistema de metadatos de WCF carga el importador personalizado en cualquier <xref:System.ServiceModel.Description.WsdlImporter> creado para ese propósito.</span><span class="sxs-lookup"><span data-stu-id="feb71-133">Once the custom importer has been specified, the WCF metadata system loads the custom importer into any <xref:System.ServiceModel.Description.WsdlImporter> created for that purpose.</span></span> <span data-ttu-id="feb71-134">Este ejemplo utiliza <xref:System.ServiceModel.Description.MetadataExchangeClient> para descargar los metadatos, el <xref:System.ServiceModel.Description.WsdlImporter> configurado correctamente para importar los metadatos mediante el importador personalizado que el ejemplo crea y <xref:System.ServiceModel.Description.ServiceContractGenerator> para compilar la información del contrato modificada en el código de cliente de Visual Basic y C# que se puede utilizar en Visual Studio para admitir Intellisense o que se puede compilar en la documentación de XML.</span><span class="sxs-lookup"><span data-stu-id="feb71-134">This sample uses the <xref:System.ServiceModel.Description.MetadataExchangeClient> to download the metadata, the <xref:System.ServiceModel.Description.WsdlImporter> properly configured to import the metadata using the custom importer the sample creates, and the <xref:System.ServiceModel.Description.ServiceContractGenerator> to compile the modified contract information into both Visual Basic and C# client code that can be used in Visual Studio to support Intellisense or compiled into XML documentation.</span></span>  
  
```csharp
/// From WSDL Documentation:  
///
/// <summary>The ICalculator contract performs basic calculation
/// services.</summary>
///
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://Microsoft.ServiceModel.Samples", ConfigurationName="ICalculator")]  
public interface ICalculator  
{  
  
    /// From WSDL Documentation:  
    ///
    /// <summary>The Add operation adds two numbers and returns the
    /// result.</summary><returns>The result of adding the two arguments
    /// together.</returns><param name="n1">The first value to add.</param><param
    /// name="n2">The second value to add.</param>
    ///
    [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.ServiceModel.Samples/ICalculator/Add", ReplyAction="http://Microsoft.ServiceModel.Samples/ICalculator/AddResponse")]  
    double Add(double n1, double n2);  
  
    /// From WSDL Documentation:  
    ///
    /// <summary>The Subtract operation subtracts the second argument from the
    /// first.</summary><returns>The result of the second argument subtracted from the
    /// first.</returns><param name="n1">The value from which the second is
    /// subtracted.</param><param name="n2">The value that is subtracted from the
    /// first.</param>
    ///
    [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.ServiceModel.Samples/ICalculator/Subtract", ReplyAction="http://Microsoft.ServiceModel.Samples/ICalculator/SubtractResponse")]  
    double Subtract(double n1, double n2);  
  
    /// From WSDL Documentation:  
    ///
    /// <summary>The Multiply operation multiplies two values.</summary><returns>The
    /// result of multiplying the first and second arguments.</returns><param
    /// name="n1">The first value to multiply.</param><param name="n2">The second value
    /// to multiply.</param>
    ///
    [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.ServiceModel.Samples/ICalculator/Multiply", ReplyAction="http://Microsoft.ServiceModel.Samples/ICalculator/MultiplyResponse")]  
    double Multiply(double n1, double n2);  
  
    /// From WSDL Documentation:  
    ///
    /// <summary>The Divide operation returns the value of the first argument divided
    /// by the second argument.</summary><returns>The result of dividing the first
    /// argument by the second.</returns><param name="n1">The numerator.</param><param
    /// name="n2">The denominator.</param>
    ///
    [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.ServiceModel.Samples/ICalculator/Divide", ReplyAction="http://Microsoft.ServiceModel.Samples/ICalculator/DivideResponse")]  
    double Divide(double n1, double n2);  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="feb71-135">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="feb71-135">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="feb71-136">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="feb71-136">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="feb71-137">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="feb71-137">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="feb71-138">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="feb71-138">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="feb71-139">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="feb71-139">The samples may already be installed on your machine.</span></span> <span data-ttu-id="feb71-140">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="feb71-140">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="feb71-141">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="feb71-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="feb71-142">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="feb71-142">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Metadata\WsdlDocumentation`  
