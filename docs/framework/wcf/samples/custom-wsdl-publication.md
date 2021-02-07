---
description: 'Más información acerca de: publicación de WSDL personalizada'
title: Publicación de WSDL personalizada
ms.date: 03/30/2017
ms.assetid: 3b3e8103-2c95-4db3-a05b-46aa8e9d4d29
ms.openlocfilehash: 39bb884a6c89d24fc38b89db09c848c87e663870
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752423"
---
# <a name="custom-wsdl-publication"></a>Publicación de WSDL personalizada

En este ejemplo se muestra cómo:  
  
- Implementar <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> en un atributo <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> personalizado para exportar las propiedades de atributo como anotaciones de WSDL.  
  
- Implementar <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> para importar las anotaciones de WSDL personalizadas.  
  
- Implementar <xref:System.ServiceModel.Description.IServiceContractGenerationExtension?displayProperty=nameWithType> y <xref:System.ServiceModel.Description.IOperationContractGenerationExtension?displayProperty=nameWithType> en un comportamiento de contrato personalizado y un comportamiento de operación personalizado, respectivamente, para escribir las anotaciones importadas como comentarios en CodeDom para el contrato y operación importados.  
  
- Utilice <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> para descargar WSDL, <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> para importar el WSDL mediante el importador de WSDL personalizado y <xref:System.ServiceModel.Description.ServiceContractGenerator?displayProperty=nameWithType> para generar el código de cliente de Windows Communication Foundation (WCF) con las anotaciones de WSDL como comentarios de///y ' ' ' en C# y Visual Basic.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
## <a name="service"></a>Servicio  

 El servicio en este ejemplo se marca con dos atributos personalizados. El primero, `WsdlDocumentationAttribute`, acepta una cadena en el constructor y se aplica para proporcionar una interfaz u operación de contrato con una cadena que describe su uso. El segundo, `WsdlParamOrReturnDocumentationAttribute`, se puede aplicar para devolver valores o parámetros a fin de describir esos valores en la operación. El ejemplo siguiente muestra un contrato de servicios, `ICalculator`, descrito utilizando estos atributos.  
  
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
  
 `WsdlDocumentationAttribute` implementa <xref:System.ServiceModel.Description.IContractBehavior> y <xref:System.ServiceModel.Description.IOperationBehavior>, por lo que las instancias de atributo se agregan al <xref:System.ServiceModel.Description.ContractDescription> correspondiente o a <xref:System.ServiceModel.Description.OperationDescription> cuando se abre el servicio. El atributo también implementa <xref:System.ServiceModel.Description.IWsdlExportExtension>. Cuando se llama a <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%28System.ServiceModel.Description.WsdlExporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29>, <xref:System.ServiceModel.Description.WsdlExporter> que se utiliza para exportar los metadatos y <xref:System.ServiceModel.Description.WsdlContractConversionContext> que contiene los objetos de descripción de servicio se pasan como parámetros que habilitan la modificación de metadatos exportados.  
  
 En este ejemplo y en función de si el objeto de contexto de la exportación tiene <xref:System.ServiceModel.Description.ContractDescription> o <xref:System.ServiceModel.Description.OperationDescription>, se extrae un comentario del atributo utilizando la propiedad del texto y se agrega al elemento de anotación de WSDL en el código siguiente.  
  
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
  
 Si se exporta una operación, el ejemplo utiliza la reflexión para obtener cualquier valor `WsdlParamOrReturnDocumentationAttribute` para los parámetros y valores devueltos y los agrega a los elementos de anotación de WSDL para esa operación de la manera que se indica a continuación.  
  
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
  
 El ejemplo publica a continuación los metadatos de manera estándar, utilizando el archivo de configuración siguiente.  
  
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
  
## <a name="svcutil-client"></a>Cliente de Svcutil  

 Este ejemplo no utiliza Svcutil.exe. El contrato se proporciona en el archivo generatedClient.cs para que después de que el ejemplo muestre la importación de WSDL y la generación de código personalizadas, se pueda invocar el servicio. Para utilizar al importador del WSDL personalizado siguiente para obtener este ejemplo, puede ejecutar Svcutil.exe y especificar la opción `/svcutilConfig`, dando la ruta de acceso al archivo de configuración del cliente utilizado en este ejemplo, que hace referencia a la biblioteca `WsdlDocumentation.dll`. Para cargar `WsdlDocumentationImporter`, sin embargo, Svuctil.exe debe poder buscar y cargar la biblioteca `WsdlDocumentation.dll`, que significa que se registra en la memoria caché global de ensamblados, en la ruta de acceso o está en el mismo directorio que Svcutil.exe. Para obtener un ejemplo básico como este, lo más fácil es copiar Svcutil.exe y el archivo de configuración del cliente en el mismo directorio que `WsdlDocumentation.dll` y ejecutarlo desde allí.  
  
## <a name="the-custom-wsdl-importer"></a>Importador de WSDL personalizado  

 El objeto <xref:System.ServiceModel.Description.IWsdlImportExtension> personalizado `WsdlDocumentationImporter` también implementa <xref:System.ServiceModel.Description.IContractBehavior> y <xref:System.ServiceModel.Description.IOperationBehavior> para que se agreguen al ServiceEndpoints importado y <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> y <xref:System.ServiceModel.Description.IOperationContractGenerationExtension> para que se invoquen con objeto de modificar la generación de código cuando se cree el contrato o el código de operación.  
  
 Primero, en el método <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29>, el ejemplo determina si la anotación de WSDL está en el contrato o nivel de la operación, y se agrega como un comportamiento en el ámbito adecuado, pasando el texto de la anotación importado a su constructor.  
  
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
  
 A continuación, cuando se genera el código, el sistema invoca los métodos <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> y <xref:System.ServiceModel.Description.IOperationContractGenerationExtension.GenerateOperation%28System.ServiceModel.Description.OperationContractGenerationContext%29>, pasando la información de contexto adecuada. El ejemplo da formato a las anotaciones de WSDL personalizadas y las inserta como comentarios en CodeDom.  
  
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
  
## <a name="the-client-application"></a>Aplicación cliente  

 La aplicación cliente carga al importador de WSDL personalizado especificándolo en el archivo de configuración de la aplicación.  
  
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
  
 Una vez que se ha especificado el importador personalizado, el sistema de metadatos de WCF carga el importador personalizado en cualquier <xref:System.ServiceModel.Description.WsdlImporter> creado para ese propósito. Este ejemplo utiliza <xref:System.ServiceModel.Description.MetadataExchangeClient> para descargar los metadatos, el <xref:System.ServiceModel.Description.WsdlImporter> configurado correctamente para importar los metadatos mediante el importador personalizado que el ejemplo crea y <xref:System.ServiceModel.Description.ServiceContractGenerator> para compilar la información del contrato modificada en el código de cliente de Visual Basic y C# que se puede utilizar en Visual Studio para admitir Intellisense o que se puede compilar en la documentación de XML.  
  
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
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Metadata\WsdlDocumentation`  
